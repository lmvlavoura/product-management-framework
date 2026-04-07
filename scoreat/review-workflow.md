# Review Workflow — Scoreat

**Date**: 2026-04-07
**Status**: Draft — awaiting validation
**Author**: Product (Claude)
**Related**: [Prioritization framework](../03-prioritization.md) · [Metrics](../06-metrics-analytics.md)

---

## Contexto e Princípio Guia

O workflow de review é o **ponto de input mais crítico do Global Dish Graph**. Cada review é um nó de dados estruturado sobre um prato específico. A qualidade, completude e friccão deste fluxo determinam diretamente a qualidade do dataset — que é o moat do Scoreat.

Princípio absoluto: **o prato é o protagonista, o restaurante é contexto.**  
Este princípio deve ser visível em cada passo do workflow — na linguagem, na ordem das perguntas, na hierarquia visual.

---

## Os Três Momentos de Review

Antes de desenhar o flow, precisamos entender *quando* o utilizador faz review:

| Momento | Contexto | Frequência estimada | Estado de espírito |
|---------|----------|--------------------|--------------------|
| **In-the-moment** | Está à mesa, acabou de receber o prato | Alto | Entusiasmado, tempo limitado |
| **À saída** | Acabou de sair do restaurante | Médio | Satisfeito/insatisfeito, quer partilhar |
| **Depois (em casa)** | Recorda uma refeição, pode não ter foto | Baixo | Reflexivo, mais detalhado |

O workflow **deve otimizar para o momento in-the-moment** — é o de maior volume e menor fricção psicológica. Os outros momentos devem funcionar sem degradação.

---

## Análise dos Entry Points

### Opção A — Foto Primeiro
```
[Câmara / Upload] → [Identificação do prato] → [Restaurante] → [Score] → [Done]
```
**Pro**: Mínima fricção. Toda a gente já tira foto à comida.  
**Pro**: A foto ancora o utilizador no prato, não no restaurante.  
**Pro**: AI pode pré-preencher nome do prato e categoria de cozinha.  
**Contra**: Utilizador sem foto fica bloqueado no primeiro passo se não for claro que pode saltar.  
**Contra**: Qualidade da foto varia — implicações para o dataset visual.

### Opção B — Nome do Prato Primeiro
```
[Search "o que comeste?"] → [Selecionar/criar prato] → [Restaurante] → [Score] → [Done]
```
**Pro**: Imediato para quem não quer tirar foto.  
**Pro**: Força categorização desde o início.  
**Contra**: Fricção de escrita in-the-moment.  
**Contra**: Search de prato é difícil sem um dataset maduro — cold start problem.

### Opção C — Restaurante Primeiro ❌
```
[Search restaurante] → [Selecionar prato do menu] → [Score]
```
**Rejeitar.** Isto é o modelo Zomato/TripAdvisor. Coloca o restaurante como protagonista. Não fazer.

### Decisão

**Recomendação: Foto-primeiro com skip opcional.**

É o único entry point que:
1. É natural no momento de consumo (já estão a tirar foto)
2. Coloca visualmente o prato em primeiro plano
3. Permite AI assistance para reduzir fricção nos passos seguintes
4. Cria diferenciação imediata vs. concorrentes texto-primeiro

---

## Workflow Recomendado — Passo a Passo

### Trigger
Botão "+ Registar prato" no tab central da app (posição de destaque, não enterrado em menus).  
CTA em português natural: **"O que comeste?"**

---

### Passo 1 — Foto (ou skip)

```
┌─────────────────────────────────────┐
│                                     │
│          [câmara ao vivo]           │
│                                     │
│      [ Tirar foto ]                 │
│                                     │
│  [Escolher da galeria]  [Sem foto]  │
└─────────────────────────────────────┘
```

- Default: câmara abre diretamente
- "Sem foto" é visível mas secundário — não deve ser o caminho óbvio
- Se tiver foto: AI tenta identificar o prato em background enquanto utilizador avança
- Sem foto: segue para Passo 2 com campo de texto vazio

**Dados capturados**: `photo_url`, `photo_taken_at`, `photo_source` (camera/gallery/none)

---

### Passo 2 — Identificação do Prato

```
┌─────────────────────────────────────┐
│  [thumbnail da foto, se existir]    │
│                                     │
│  Que prato é este?                  │
│                                     │
│  [ Bacalhau à Brás            ▼ ]   │
│                                     │
│  Sugestões:                         │
│  ○ Bacalhau à Brás                  │
│  ○ Bacalhau com Natas               │
│  ○ Outro prato de bacalhau          │
│  ○ Outro (escreve)                  │
└─────────────────────────────────────┘
```

- Se houve foto: AI pré-preenche sugestão com % confiança (não mostrar o % ao utilizador — só mostrar a melhor sugestão)
- Se sem foto: campo de busca vazio com teclado aberto
- "Outro (escreve)" permite criar novo prato — passa para micro-form de criação
- **Nota crítica**: a busca deve ser tolerante a erros ortográficos e variações regionais (ex: "bacalhau à brás" = "bacalhau brás" = "bacalhau à brasileira" em alguns sítios — não são o mesmo prato, mas o utilizador pode confundir)

**Dados capturados**: `dish_id` (se match), `dish_name_raw` (o que o utilizador escreveu), `ai_suggestion`, `ai_confidence`, `user_confirmed`

---

### Passo 3 — Restaurante (Contexto)

```
┌─────────────────────────────────────┐
│  Bacalhau à Brás                    │
│                                     │
│  Onde comeste?                      │
│                                     │
│  [Baseado na tua localização]       │
│  ○ Tasca do Chico · 200m           │
│  ○ Solar dos Presuntos · 500m      │
│  ○ A Cevicheria · 1.2km            │
│                                     │
│  [Procurar outro restaurante]       │
│  [Em casa / não sei]                │
└─────────────────────────────────────┘
```

- Location-based suggestions são a melhor UX aqui — não exige digitação
- Se localização não disponível: campo de busca
- "Em casa / não sei" é válido — um prato pode ser caseiro ou o utilizador pode não querer associar a um restaurante específico
- O restaurante **não tem nome de destaque** — é uma linha de contexto, não um heading

**Dados capturados**: `restaurant_id`, `restaurant_name_raw`, `location_lat_lng`, `location_source` (gps/manual/none)

---

### Passo 4 — Score do Prato

Este é o passo mais importante. É onde "Scoreat" ganha significado.

```
┌─────────────────────────────────────┐
│  Bacalhau à Brás                    │
│  Tasca do Chico                     │
│                                     │
│  Como foi?                          │
│                                     │
│      1  2  3  4  5  6  7  8  9 10  │
│                 ◉                   │
│               7/10                  │
│                                     │
│  Voltavas a pedir?  [Sim] [Não]     │
│                                     │
└─────────────────────────────────────┘
```

- Score único 1-10 (não estrelas — estrelas têm conotação de restaurante, não de prato)
- **"Voltavas a pedir?"** é a pergunta mais honesta que existe. Binary. Sem ambiguidade. É o equivalente do "would you recommend" para pratos.
- Não pedir mais do que isto neste passo — fricção mata completion rate

**Dados capturados**: `dish_score` (1-10), `would_order_again` (boolean)

---

### Passo 5 — Enriquecimento Opcional (Quick Tags)

```
┌─────────────────────────────────────┐
│  Mais alguma coisa? (opcional)      │
│                                     │
│  [Picante] [Para partilhar]         │
│  [Porção generosa] [Boa apresentação│
│  [Relação qualidade-preço]          │
│  [Imperdível]                       │
│                                     │
│  Nota rápida:                       │
│  [ O bacalhau estava no ponto... ] │
│                                     │
│           [ Guardar ]               │
└─────────────────────────────────────┘
```

- Tags pré-definidas = dados estruturados para o Graph
- Nota livre = dados qualitativos para contexto
- Tudo opcional — o utilizador pode guardar diretamente do Passo 4
- "Guardar" nunca deve estar a mais de 1 tap de distância do Passo 4

**Dados capturados**: `tags[]`, `notes_text`, `review_timestamp`

---

### Passo 6 — Confirmação + "Aha Moment"

```
┌─────────────────────────────────────┐
│  Guardado!                          │
│                                     │
│  Bacalhau à Brás · 7/10             │
│  Tasca do Chico                     │
│                                     │
│  ─────────────────────────────────  │
│  Os teus melhores bacalhaus:        │
│  1. Casa de Pasto · 9/10           │
│  2. Zé da Mouraria · 8/10          │
│  3. Tasca do Chico · 7/10  ← este  │
│                                     │
│  [Ver todos] [Partilhar]            │
└─────────────────────────────────────┘
```

- Este é o momento que diferencia o Scoreat de qualquer outra app
- **O utilizador vê imediatamente o prato no seu ranking pessoal da categoria**
- Cria loop de retorno: "quero encontrar um bacalhau à brás melhor que 9/10"
- "Partilhar" pode ser entry point para crescimento orgânico

---

## Fluxo Completo (Happy Path)

```
Tap "+ O que comeste?"
        ↓
[1] Foto (2 seg — só apontar e tirar)
        ↓
[2] Confirmar prato (1 tap se AI acertou)
        ↓
[3] Confirmar restaurante (1 tap se GPS acertou)
        ↓
[4] Score + "voltavas a pedir?" (2 interações)
        ↓
[5] Skip tags (1 tap em "Guardar")
        ↓
[6] Ver ranking pessoal

Total: ~6 interações, < 30 segundos
```

**Benchmark**: o objetivo é < 30 segundos do primeiro tap ao "Guardado". Acima disso, o utilizador in-the-moment abandona.

---

## Dados Capturados por Review (Schema)

```json
{
  "review_id": "uuid",
  "user_id": "uuid",
  "created_at": "timestamp",

  "dish": {
    "id": "uuid | null",
    "name_raw": "Bacalhau à Brás",
    "name_confirmed": "Bacalhau à Brás",
    "category": "peixe",
    "cuisine": "portuguesa",
    "photo_url": "string | null"
  },

  "restaurant": {
    "id": "uuid | null",
    "name_raw": "Tasca do Chico",
    "lat": 38.7139,
    "lng": -9.1394
  },

  "score": {
    "overall": 7,
    "would_order_again": true
  },

  "enrichment": {
    "tags": ["para_partilhar", "boa_apresentacao"],
    "notes": "O bacalhau estava no ponto certo, não seco."
  },

  "meta": {
    "ai_used": true,
    "ai_dish_suggestion": "Bacalhau à Brás",
    "ai_confidence": 0.91,
    "entry_point": "camera",
    "completion_time_seconds": 24
  }
}
```

---

## O que Este Workflow Alimenta no Global Dish Graph

Cada review cria ou fortalece:

1. **Nó de prato** — "Bacalhau à Brás" como entidade única com score médio, distribuição de scores, tags frequentes
2. **Edge restaurante→prato** — "a Tasca do Chico serve Bacalhau à Brás com score médio de 7.3/10 (n=14)"
3. **Edge utilizador→prato** — ranking pessoal por categoria/cozinha
4. **Dataset de fotos** — imagens etiquetadas com nome do prato, restaurante, score — dataset de treino para melhorar AI de identificação

---

## Métricas de Sucesso do Workflow

Alinhado com o framework em [`06-metrics-analytics.md`](../06-metrics-analytics.md):

| Métrica | Baseline (a medir) | Target 30 dias |
|---------|--------------------|----------------|
| Review completion rate (Passo 1 → "Guardado") | — | > 70% |
| Tempo médio de completion | — | < 30s |
| % reviews com foto | — | > 65% |
| % reviews com restaurante identificado | — | > 80% |
| % utilizadores que fazem 2ª review em 7 dias | — | > 40% |
| AI dish identification accuracy | — | > 75% (com confirmação humana) |

---

## Assumptions Riskiest (a validar)

1. **"O utilizador tira foto antes de comer"** — se a maioria tira foto a meio ou não tira, o flow foto-primeiro cria fricção desnecessária
2. **"30 segundos é aceitável in-the-moment"** — pode ser que acima de 15 segundos a taxa de abandono dispare
3. **"Score 1-10 é intuitivo para pratos"** — pode ser que utilizadores portugueses se identifiquem mais com 1-5 estrelas por familiaridade
4. **"'Voltavas a pedir?' chega como sinal de qualidade"** — pode haver casos onde o utilizador diria não por razão externa (preço, distância) mas o prato foi excelente
5. **"GPS resolve o restaurante sem esforço"** — em centros urbanos densos (Baixa de Lisboa) pode haver 5 restaurantes no mesmo edifício

---

## Próximos Passos

- [ ] Validar tempo de completion com 5 utilizadores (teste de protótipo paper/Figma)
- [ ] Testar linguagem: "O que comeste?" vs "Que prato comeste?" vs "Adicionar prato"
- [ ] Definir "aha moment" exato no Passo 6 — requer dados mínimos (precisa de pelo menos 2 reviews na mesma categoria)
- [ ] Especificar cold start do Passo 6 para utilizadores sem histórico (primeiro review)
- [ ] Avaliar se tags devem ser pré-definidas ou emergentes (UGC)
