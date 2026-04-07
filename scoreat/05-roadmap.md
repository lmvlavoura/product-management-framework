# Product Roadmap — Scoreat

**Date**: 2026-04-07
**Status**: Vivo — revisto mensalmente
**Author**: Head of Product
**Related**: [Product Vision](./00-product-vision.md) · [30-Day Sprint](./04-30-day-sprint.md)

---

## Filosofia de Roadmap

Este roadmap é **orientado a outcomes**, não a features. Cada iniciativa responde à pergunta: "que comportamento de utilizador queremos mudar, e como sabemos que mudou?"

O roadmap está dividido em três horizontes:
- **NOW** (0–3 meses): o que estamos a construir agora, com alta certeza
- **NEXT** (3–9 meses): o que construímos depois, se NOW confirmar as hipóteses
- **LATER** (9–24 meses): apostas estratégicas, dependem de PMF confirmado

Tudo a partir de 24 meses está na visão, não no roadmap.

---

## NOW — Validação (Abril–Junho 2026)

**Objetivo**: provar que o core value loop sustenta. NSM > 15 reviews/semana por utilizadores ativados ao fim do sprint de 30 dias.

### Iniciativa 1 — Review Flow MVP
**Outcome**: utilizadores conseguem registar um prato em < 30 segundos, do zero ao "Guardado"
**Hipóteses validadas se**: completion rate > 70%, tempo médio < 30s
**Features incluídas**:
- Foto-first entry (câmara + galeria + skip)
- Identificação de prato (search + AI suggestion)
- Associação a restaurante (GPS-based)
- Score 1-10 + "voltavas a pedir?"
- Tags opcionais
- Ranking pessoal por categoria (passo 6 — o aha moment)

**Features fora de scope**:
- Edição de review depois de submetida (NEXT)
- Reviews de amigos / feed social (LATER)
- Notificações push (NEXT)

---

### Iniciativa 2 — Dataset Seed Lisboa
**Outcome**: Lisboa tem 50 pratos mapeados com scores editoriais antes do sprint começar
**Hipóteses validadas se**: utilizadores encontram 3+ pratos relevantes em Lisboa sem esforço
**Approach**: concierge — manual, não automatizado

---

### Iniciativa 3 — Analytics Mínimos
**Outcome**: conseguimos medir o NSM e as 3 input metrics em tempo real
**Tools**: Mixpanel (free tier)
**Events mínimos**: `dish_review_submitted`, `user_activated`, `session_start`

---

### O que NÃO está no NOW (e porquê)

| Feature | Porquê excluída |
|---------|-----------------|
| Feed social / ver reviews de amigos | Requer utilizadores suficientes. Prematuro. |
| Notificações push | Antes de provar hábito orgânico, push é ruído. |
| Pesquisa/descoberta pública | Requer dataset. Foco primeiro no registo. |
| Perfil público de utilizador | Vanity feature. Não move o NSM agora. |
| Multi-cidade | Foco em Lisboa. Um mercado de cada vez. |
| Web app | Mobile-first. 100% dos casos de uso são in-the-moment. |

---

## NEXT — Crescimento (Julho–Dezembro 2026)

**Gate de entrada**: NSM > 15 no sprint de 30 dias + activation rate > 30%

**Objetivo**: escalar de 20 para 500 utilizadores ativos em Lisboa. Lançar descoberta pública.

### Iniciativa 4 — Descoberta Pública
**Outcome**: utilizadores sem histórico conseguem encontrar o melhor prato de uma categoria em Lisboa
**Hipóteses**: utilizadores que descobrem via Scoreat têm D30 retention superior a utilizadores que chegam por word-of-mouth
**Features**:
- Search por prato (tolerante a variações, erros de ortografia)
- Ranking de pratos por categoria + cidade
- Filtros: distância, score mínimo, "ainda não experimentei"
- Página de prato: score agregado, distribuição, fotos, restaurantes onde encontrar

---

### Iniciativa 5 — Notificações Inteligentes
**Outcome**: utilizadores ativados têm reminder contextual para registar sem ser intrusivo
**Hipóteses**: notificação baseada em localização (perto de restaurante previamente visitado) aumenta D30 retention em 15%+
**Features**:
- "Voltaste ao [restaurante]. Pediste algo novo?"
- "Ainda não registaste o teu [prato favorito] esta semana"
- Opt-in explícito — nunca opt-out required

---

### Iniciativa 6 — Expansão Porto
**Outcome**: Porto tem 100+ pratos mapeados e 50+ utilizadores ativos
**Hipóteses**: o modelo Lisboa escala para segunda cidade sem mudanças no produto
**Approach**: community seeding (parceria com food bloggers do Porto)

---

### Iniciativa 7 — Perfil e Listas
**Outcome**: utilizadores partilham o seu "top 10 pratos em Lisboa" com amigos
**Hipóteses**: sharing de listas é o principal viral loop do Scoreat
**Features**:
- Perfil público (opt-in)
- Listas curadas: "Os meus top 5 Bacalhaus", "O que comer em Lisboa se só tiveres 1 dia"
- Link partilhável (sem obrigatoriedade de conta para ver)

---

## LATER — Escala (2027–2028)

**Gate de entrada**: PMF confirmado (D30 retention > 35%, NPS > 40, crescimento orgânico consistente)

### Iniciativa 8 — Restaurant Intelligence (B2B)
**Outcome**: 50 restaurantes em Lisboa pagam por analytics de pratos
**MRR target**: €10K (50 restaurantes × €200/mês)
**Features**:
- Dashboard de score dos pratos vs. categoria
- Alertas de queda de score
- Benchmark com concorrentes na mesma área
- Relatório mensal automático

---

### Iniciativa 9 — Expansão Internacional (Brasil + Espanha)
**Outcome**: 10.000 utilizadores ativos fora de Portugal
**Abordagem**: Brasil primeiro (língua + cultura alimentar forte + mercado grande), depois Espanha

---

### Iniciativa 10 — Consumer Premium
**Outcome**: 5% dos utilizadores ativos pagam €7.99/mês
**Features Premium**:
- Modo Viagem: "melhores pratos nas cidades que vou visitar"
- Filtros de dieta (vegetariano, sem glúten, halal)
- Histórico ilimitado (free tier = últimos 90 dias)
- Exportar lista de pratos para PDF/partilhar

---

### Iniciativa 11 — Dish Graph API (B2B2C)
**Outcome**: 3 parceiros a pagar pelo acesso ao dish graph via API
**Target**: apps de delivery, guias de viagem, plataformas hoteleiras
**Modelo**: pay-per-query ou flat fee mensal

---

## Matriz de Priorização das Iniciativas NEXT

Usando RICE (framework `03-prioritization.md`):

| Iniciativa | Reach | Impact | Confidence | Effort | RICE |
|-----------|-------|--------|------------|--------|------|
| Descoberta Pública | 500 | 3 | 60% | 2 | **450** |
| Perfil e Listas | 300 | 2 | 70% | 1 | **420** |
| Notificações Inteligentes | 200 | 2 | 80% | 0.5 | **640** |
| Expansão Porto | 100 | 2 | 70% | 1.5 | **93** |

**Ordem de execução NEXT**: Notificações → Descoberta Pública → Perfil e Listas → Porto

---

## Sinais de Alerta (Triggers de Revisão do Roadmap)

| Sinal | Ação |
|-------|------|
| NSM não cresce por 2 semanas consecutivas | Revisão urgente do core value loop |
| Activation rate cai abaixo de 20% | Revisão do onboarding e do aha moment |
| TripAdvisor ou Google lança dish-centric feature | Acelerar diferenciação + moat (dataset quality) |
| Oportunidade de parceria B2B inbound | Avaliar se antecipa LATER para NEXT |
| Brand "Scoreat" cria fricção mensurável | Trigger para decisão de rename antes de expansão |

---

## Versão Resumida (1 Slide)

```
NOW (0-3m)        NEXT (3-9m)          LATER (9-24m)
───────────────   ──────────────────   ──────────────────
Review Flow MVP   Descoberta pública   Restaurant B2B
Dataset Lisboa    Notificações         Consumer Premium
Analytics base    Perfil + Listas      Expansão global
                  Porto                Dish Graph API

NORTH STAR: Weekly reviews (activated users)
TARGET 30d: > 15/semana
TARGET 1 ano: > 200/semana
```
