# North Star Metric — Scoreat

**Date**: 2026-04-07
**Status**: Draft — para discussão e alinhamento
**Author**: Product (Claude)
**Related**: [Review Workflow](./review-workflow.md) · [Metrics framework](../06-metrics-analytics.md)

---

## O Problema de Definir o NSM Agora

O Scoreat tem um produto com **duas propostas de valor distintas** que coexistem:

| Modo | Utilizador | Job-to-be-done |
|------|-----------|----------------|
| **Registo** | Come, tira foto, avalia | "Quero guardar e rankear os pratos que já comi" |
| **Descoberta** | Pesquisa antes de sair | "Quero saber qual o melhor prato X perto de mim" |

Estes dois modos têm um problema de **cold start sequencial**: a descoberta só tem valor quando existe dataset. E o dataset só existe porque há registo. Estamos na fase de registo.

Escolher o NSM errado agora significa otimizar para a métrica errada — por exemplo, otimizar "total de reviews" pode encher a base de dados com reviews de utilizadores de uma única vez que nunca voltam, dando uma falsa sensação de tração.

---

## Candidatos Eliminados

### "Total de reviews submetidas"
Métrica de vaidade. Um utilizador pode submeter 20 reviews no dia de download e nunca mais voltar. O dataset cresce, o produto não.

### "Downloads / Registos"
Vaidade pura. Não mede se o utilizador encontrou valor.

### "DAU / MAU"
Genérico demais. Não captura o que é específico do Scoreat — um utilizador pode abrir a app sem fazer nada de relevante para o dish graph.

### "Pratos únicos no graph"
Métrica interna de dataset. Importante para a engenharia do moat, mas não reflete valor para o utilizador.

### "Tempo na app"
Irrelevante para o modelo de uso do Scoreat. Uma review demora 30 segundos. Mais tempo não significa mais valor — significa fricção.

---

## O Core Value Loop

Antes de decidir o NSM, precisamos de ter o core value loop claro:

```
                    ┌─────────────────────────┐
                    ↓                         │
[Utilizador come] → [Regista prato] → [Vê o seu ranking pessoal]
                                              │
                                              ↓
                               [Quer comer melhor versão do mesmo prato]
                                              │
                                              ↓
                               [Usa Scoreat para descobrir onde]
                                              │
                                              ↓
                               [Come, regista, loop fecha]
```

O loop só fecha — e só tem valor — quando o utilizador tem **histórico suficiente** para que o ranking pessoal seja significativo. Abaixo de ~5 reviews na mesma categoria de prato, não há ranking real para mostrar.

**O momento de valor ("aha moment") é:** ver o primeiro prato numa categoria rankeado contra outros que já comeu.

---

## A Decisão

### North Star Metric (fase de validação — primeiros 90 dias)

> **Pratos avaliados por semana por utilizadores com 5+ reviews totais**
>
> Em inglês: *Weekly dish reviews from activated users*

**"Utilizador ativado"** = utilizador que submeteu 5 ou mais reviews no total (independente do período).

### Porquê este NSM e não outro

| Critério (framework `06-metrics-analytics.md`) | Como este NSM cumpre |
|------------------------------------------------|---------------------|
| Expressa valor entregue | Sim — um utilizador ativado que continua a registar pratos encontrou valor no loop |
| Leading indicator de revenue | Sim — utilizadores que voltam são os que pagam (ou recomendam) |
| Reflete customer satisfaction | Sim — ninguém volta a uma app que não lhe dá valor |
| Simples de entender | Sim — "quantos pratos foram avaliados esta semana por quem já usa a app a sério?" |
| Mensurável desde dia 1 | Sim — tracked no review submission event + user review count |

### Porque o threshold é 5 reviews (e não 3, nem 10)

- Com **< 3 reviews**: não há ranking com significado. O utilizador ainda não viveu o aha moment.
- Com **5 reviews** (assumindo que distribui por 2-3 categorias diferentes): já tem comparações reais. "Este é o teu melhor Bacalhau à Brás. Este é o teu pior Frango Piri-Piri."
- Com **10+ reviews**: o threshold seria demasiado restritivo na fase inicial — teríamos um NSM com valor zero durante semanas.

5 é o mínimo para o loop ter significado. É o equivalente ao "7 friends in 10 days" do Facebook.

---

## Input Metrics (O que move o NSM)

```
NSM: Weekly dish reviews from activated users
              │
    ┌─────────┼──────────┐
    ↓         ↓          ↓
[Activation] [Frequency] [Retention]
    │         │          │
    │         │          └── D7, D30 retention rate
    │         └──────────── Avg reviews per activated user per week
    └────────────────────── % users who reach 5 reviews (activation rate)
```

### Input metric 1 — Activation Rate
`% de utilizadores registados que chegam às 5 reviews`

- Se este número for baixo: o problema está no onboarding ou no aha moment (utilizadores não percebem o valor a tempo)
- Target sprint 30 dias: > 25%

### Input metric 2 — Review Frequency (activated users)
`Média de reviews por semana por utilizador ativado`

- Captura se os utilizadores ativados mantêm o hábito
- Target sprint 30 dias: > 1.5 reviews/semana

### Input metric 3 — D30 Retention (activated users)
`% de utilizadores ativados que submetem pelo menos 1 review no mês 2`

- Mede se o loop sustenta ou se é apenas hype inicial
- Target sprint 30 dias: > 35%

---

## NSM no Contexto do Sprint de 30 Dias

Na fase de validação com utilizadores manuais (concierge / reviews assistidas), o NSM funciona assim:

| Semana | Meta NSM | O que monitorizar |
|--------|----------|-------------------|
| S1 | Baseline: 0 → primeiros reviews | Completion rate do flow de review |
| S2 | 5+ utilizadores ativados (chegaram a 5 reviews) | Activation rate |
| S3 | NSM > 10 reviews/semana | Frequency + qualidade dos dados |
| S4 | NSM estável ou crescente sem intervenção manual | Sinal de hábito orgânico |

**Critério de go/no-go ao fim dos 30 dias:**  
Se o NSM não estiver a crescer semana-a-semana nas semanas 3-4, o problema está no core value loop — não no marketing, não no design. É sinal de pivot.

---

## O NSM Muda com a Fase do Produto

Este NSM é **específico para a fase de validação**. Muda à medida que o produto evolui:

| Fase | NSM | Porquê muda |
|------|-----|-------------|
| **Validação** (agora) | Weekly reviews from activated users | Provar que o loop existe e é sustentável |
| **Crescimento** (pós-PMF) | Dishes discovered and eaten (via Scoreat) | Quando a descoberta está madura, medir se fecha o loop completo |
| **Escala** | Dish graph nodes with 5+ verified reviews | Quando o moat/dataset é o produto principal |

A transição de fase 1 para fase 2 acontece quando conseguirmos medir "o utilizador viu uma recomendação de prato → foi comer → registou". Isso requer feature de check-in ou deep linking. Não está no MVP.

---

## O que Este NSM NÃO captura (e precisa de métricas de suporte)

| O que falta | Métrica complementar |
|-------------|---------------------|
| Qualidade dos dados no graph | % reviews com foto + restaurante identificado |
| Crescimento do dataset (moat) | Pratos únicos com 3+ reviews independentes |
| Descoberta (quando lançar) | Click-through rate em recomendações de prato |
| Saúde do negócio | NPS + "voltavas a recomendar o Scoreat" |

---

## NSM Framework Preenchido

```
┌────────────────────────────────────────────────┐
│ NORTH STAR METRIC                              │
│                                                │
│ Weekly dish reviews from activated users       │
│ (utilizadores com 5+ reviews totais)           │
├────────────────────────────────────────────────┤
│ PORQUÊ ESTA MÉTRICA?                           │
│                                                │
│ • Captura utilizadores que viveram o aha moment│
│ • Mede hábito, não hype de instalação          │
│ • Leading indicator de retention e moat growth │
├────────────────────────────────────────────────┤
│ INPUT METRICS                                  │
│                                                │
│ 1. Activation rate (→ 5 reviews)               │
│ 2. Review frequency (activated users/week)     │
│ 3. D30 retention (activated users)             │
├────────────────────────────────────────────────┤
│ TARGETS — Sprint 30 dias                       │
│                                                │
│ Semana 1: baseline estabelecido                │
│ Semana 2: 5+ utilizadores ativados             │
│ Semana 4: NSM > 10 reviews/semana (orgânico)   │
├────────────────────────────────────────────────┤
│ TRACKING                                       │
│                                                │
│ Evento: dish_review_submitted                  │
│ Filtro: user.total_reviews >= 5                │
│ Agregação: count, weekly, por user             │
│ Review: semanal (segunda-feira)                │
│ Owner: Founder / Product                       │
└────────────────────────────────────────────────┘
```

---

## Próximos Passos

- [ ] Confirmar se 5 reviews é o threshold certo — testar com primeiros 10 utilizadores: em que review sentiram que a app "fazia sentido"?
- [ ] Implementar tracking do evento `dish_review_submitted` com propriedade `user_total_reviews`
- [ ] Criar dashboard mínimo com NSM + 3 input metrics antes do sprint começar
- [ ] Decidir tool de analytics (Mixpanel free tier recomendado para esta fase — ver `06-metrics-analytics.md`)
