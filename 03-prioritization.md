# 3. Prioritization Frameworks

## 📋 Índice
1. [Porquê Priorizar](#porquê-priorizar)
2. [RICE Framework](#rice-framework)
3. [Value vs Effort Matrix](#value-vs-effort-matrix)
4. [Kano Model](#kano-model)
5. [MoSCoW Method](#moscow-method)
6. [ICE Score](#ice-score)
7. [Opportunity Scoring](#opportunity-scoring)
8. [Cost of Delay](#cost-of-delay)

---

## 🎯 Porquê Priorizar

### O Problema
- Recursos limitados (team, tempo, budget)
- Ideias ilimitadas
- Stakeholders com agendas diferentes
- Pressure para entregar tudo
- Risco de construir features que ninguém usa

### Os Princípios

**1. Say No is as important as Say Yes**
Todo "yes" é um "no" implícito a outra coisa.

**2. Focus Wins**
Fazer 3 coisas excepcionalmente > 10 coisas mediocre.

**3. Data-Informed, Not Data-Driven**
Números informam, contexto e julgamento decidem.

**4. Transparent Criteria**
Todos devem entender porque X foi priorizado sobre Y.

---

## 🎲 RICE Framework

### O que é?
Framework criado por Intercom para pontuar features baseado em 4 fatores.

### A Fórmula

```
RICE Score = (Reach × Impact × Confidence) / Effort

Quanto MAIOR o score, maior a prioridade
```

### Os Componentes

#### 1. Reach (Alcance)
**"Quantas pessoas isto impacta num período?"**

Medido em: Pessoas/usuários por período (trimestre típico)

```
Exemplos:
- "500 users/quarter"
- "2000 page views/month"
- "100 customers/quarter"

Como estimar:
- Analytics históricos
- % da user base
- Funnel data
- Customer requests
```

#### 2. Impact (Impacto)
**"Quanto impacta cada pessoa?"**

Escala típica:
- **3** = Massive impact
- **2** = High impact  
- **1** = Medium impact
- **0.5** = Low impact
- **0.25** = Minimal impact

```
Perguntas para avaliar:
- Move the North Star Metric significativamente?
- Resolve um pain point crítico?
- Habilita um novo use case importante?
- Diferenciação competitiva?
```

#### 3. Confidence (Confiança)
**"Quão certos estamos das estimativas?"**

Escala:
- **100%** = High confidence (dados sólidos)
- **80%** = Medium confidence (alguns dados)
- **50%** = Low confidence (mostly assumptions)

```
Sinais de high confidence:
✓ Validado com users
✓ Dados históricos similares
✓ A/B test prévio
✓ Customer research

Sinais de low confidence:
✗ "Eu acho que..."
✗ Hipóteses não testadas
✗ Novos mercados
✗ Features complexas
```

#### 4. Effort (Esforço)
**"Quanto trabalho isto requer?"**

Medido em: Person-months

```
1 person-month = 1 pessoa trabalhando 1 mês full-time

Considerar:
- Design
- Frontend dev
- Backend dev
- QA testing
- DevOps
- Documentation

Exemplo:
2 developers × 0.5 month + 1 designer × 0.25 month = 1.25 person-months
```

### Exemplo Completo

| Feature | Reach | Impact | Confidence | Effort | RICE Score |
|---------|-------|--------|------------|--------|------------|
| Mobile push notifications | 1000 users/Q | 2 | 80% | 2 months | **800** |
| Advanced filters | 500 users/Q | 1 | 100% | 1 month | **500** |
| AI-powered insights | 300 users/Q | 3 | 50% | 4 months | **113** |
| Dashboard templates | 800 users/Q | 1 | 80% | 0.5 months | **1280** |

**Prioridade**: Dashboard templates → Push notifications → Advanced filters → AI insights

### RICE Scorecard Template

```
Feature: [Nome da feature]
───────────────────────────

REACH
Quantas pessoas/trimestre? [      ]
Source: [Como calculaste]

IMPACT  
0.25 | 0.5 | 1 | 2 | 3 = [  ]
Reasoning: [Porquê este score]

CONFIDENCE
50% | 80% | 100% = [    ]
Evidence: [O que suporta este nível]

EFFORT
Person-months = [    ]
Breakdown:
- Design: [X] weeks
- Dev: [X] weeks  
- QA: [X] weeks
Total: [X] person-months

──────────────────────────
RICE SCORE: [        ]
Rank: [#X] of [Y] features
```

---

## 📊 Value vs Effort Matrix

### O que é?
Matriz 2×2 para plotting rápido de ideias.

### Os Quadrantes

```
      High Value
          │
    ②    │    ①
  Quick  │  Big
  Wins   │  Bets
─────────┼─────────  Effort
  ④      │    ③
  Maybe  │  Money
  Later  │  Pit
         │
     Low Value
```

#### Quadrante ① - Big Bets
- **High Value + High Effort**
- Strategic initiatives
- Requires buy-in
- Plan carefully
- **Action**: Roadmap para próximo trimestre

#### Quadrante ② - Quick Wins  
- **High Value + Low Effort**
- Absolute priority
- Do ASAP
- **Action**: Sprint planning agora

#### Quadrante ③ - Money Pit
- **Low Value + High Effort**
- Avoid
- Question strongly
- **Action**: Deprioritize

#### Quadrante ④ - Maybe Later
- **Low Value + Low Effort**
- Fill-in work
- Delegate
- **Action**: Backlog

### Como Plotar

**Eixo Effort (X):**
- Low: < 2 weeks
- Medium: 2-6 weeks  
- High: > 6 weeks

**Eixo Value (Y):**
- Low: Nice to have
- Medium: Melhora experiência
- High: Game changer

### Template

```
Plot each initiative:

      │
   10 │  [E]    [A]
    9 │
    8 │        [B]
    7 │
    6 │  [D]
    5 │              [C]
    4 │
    3 │
    2 │
    1 │
      └─────────────────────
       1  2  3  4  5  6  7  8  9  10
                Effort →

Legend:
[A] = Feature A
[B] = Feature B
...
```

### Value Scoring Rubric

| Score | Business Impact | User Impact | Strategic Fit |
|-------|----------------|-------------|---------------|
| 10 | Massive revenue | Solves critical pain | Core to vision |
| 7-9 | Significant revenue | Important improvement | Supports strategy |
| 4-6 | Moderate revenue | Nice enhancement | Somewhat aligned |
| 1-3 | Minimal revenue | Minor benefit | Tangential |

---

## 💡 Kano Model

### O que é?
Framework para classificar features baseado em satisfação do customer.

### As 5 Categorias

#### 1. Basic Needs (Threshold)
**Must-haves. Se não tem, customers insatisfeitos.**
- Ausência → Muito insatisfeito
- Presença → Neutro

```
Exemplos:
- App não crasha
- Load time < 3s
- Dados estão corretos
- Login funciona
```

#### 2. Performance Needs (Linear)
**More is better. Satisfação proporcional à qualidade.**
- Mais/melhor → Mais satisfeito
- Menos/pior → Menos satisfeito

```
Exemplos:
- Velocidade de search
- Número de integrações
- Uptime %
- Customer support response time
```

#### 3. Excitement Needs (Delighters)
**Unexpected features que encantam.**
- Ausência → Neutro (não esperavam)
- Presença → Muito satisfeito

```
Exemplos:
- Dark mode (quando não esperado)
- Undo send email
- AI suggestions
- Easter eggs
```

#### 4. Indifferent
**Não impacta satisfação.**
- Customers don't care

```
Exemplos:
- Features que só tu achas fixes
- Over-engineering
- Gold-plating
```

#### 5. Reverse
**Quanto mais, MENOS satisfeito.**
- Alguns customers preferem sem

```
Exemplos:
- Demasiadas features (overwhelm)
- Notificações excessivas
- Steps extra no processo
```

### O Gráfico Kano

```
Satisfação
    ↑
    │     ╱ Excitement
    │    ╱
    │   ╱────────── Performance
    │  ╱
    │ ╱
────┼──────────── Basic
    │          Implementation Quality →
```

### Como Usar Kano

1. **Survey users com perguntas pares:**

```
Para cada feature, perguntar:

Functional: "Como te sentirias se tivesses [feature]?"
[ ] I like it
[ ] I expect it  
[ ] I'm neutral
[ ] I can tolerate it
[ ] I dislike it

Dysfunctional: "Como te sentirias se NÃO tivesses [feature]?"
[ ] I like it
[ ] I expect it
[ ] I'm neutral
[ ] I can tolerate it
[ ] I dislike it
```

2. **Mapear respostas para categorias:**

| Functional → Dysfunctional | Like | Expect | Neutral | Tolerate | Dislike |
|----------------------------|------|--------|---------|----------|---------|
| Like | Q | E | E | E | P |
| Expect | R | I | I | I | B |
| Neutral | R | I | I | I | B |
| Tolerate | R | I | I | I | B |
| Dislike | R | R | R | R | Q |

Legend: E=Excitement, P=Performance, B=Basic, I=Indifferent, R=Reverse, Q=Questionable

3. **Priorizar:**
- **Primeiro**: Basic needs
- **Segundo**: Performance needs
- **Terceiro**: Excitement features
- **Ignorar**: Indifferent/Reverse

### Time Decay no Kano

⚠️ **Excitement features → Performance → Basic over time**

```
2020: Dark mode = Excitement
2023: Dark mode = Performance
2026: Dark mode = Basic (expected)

Strategy: Continuous innovation necessária
```

---

## 🎯 MoSCoW Method

### O que é?
Framework simples de 4 categorias para priorização.

### As Categorias

#### **M** - Must Have
**Non-negotiable. Sem isto, falha.**
- Mission critical
- Legal requirement
- Blocker para launch

```
Teste: "O que acontece se não fizermos?"
Se resposta = "Não podemos lançar", é Must Have
```

#### **S** - Should Have
**Importante mas não crítico.**
- High priority
- Can work around if needed
- Adds significant value

```
Pode ser adiado 1 sprint se necessário
```

#### **C** - Could Have  
**Nice to have.**
- Enhances experience
- Low impact se não incluído
- First to drop if constraints

```
Faz se tiver tempo/budget sobrando
```

#### **W** - Won't Have (this time)
**Out of scope.**
- Explicitly deferred
- Manage expectations
- Maybe future release

```
Importante comunicar claramente
```

### MoSCoW Distribution Guidelines

```
Recomendação:
┌──────────────────────┐
│ Must:    60%        │ ████████████
│ Should:  20%        │ ████
│ Could:   20%        │ ████
│ Won't:   --         │
└──────────────────────┘

⚠️ Se mais de 70% é "Must", rever scope
```

### Template

```
FEATURE: [Nome]
━━━━━━━━━━━━━━━━━━━━━

CLASSIFICATION: [ M / S / C / W ]

REASONING:
[Porquê esta classificação]

USER VALUE:
[Como impacta o utilizador]

BUSINESS VALUE:
[Como impacta o negócio]

EFFORT:
[Low / Medium / High]

DEPENDENCIES:
[O que precisa estar pronto primeiro]

RISKS:
[O que pode correr mal]
```

---

## 🧊 ICE Score

### O que é?
Framework simplificado. Bom para brainstorming rápido.

### A Fórmula

```
ICE = (Impact + Confidence + Ease) / 3

Scale: 1-10 para cada fator
```

### Os Componentes

#### Impact (1-10)
How much will this move the needle?

```
10 = Game changer
7-9 = Significant impact
4-6 = Moderate impact  
1-3 = Minor impact
```

#### Confidence (1-10)
How sure are we this will work?

```
10 = Highly confident (proven)
7-9 = Confident (strong signals)
4-6 = Moderate confidence
1-3 = Low confidence (guessing)
```

#### Ease (1-10)
How easy is it to implement?

```
10 = Very easy (hours/days)
7-9 = Easy (1-2 weeks)
4-6 = Moderate (2-4 weeks)
1-3 = Hard (months)
```

### Scorecard Example

| Initiative | Impact | Confidence | Ease | ICE Score | Rank |
|------------|--------|------------|------|-----------|------|
| Add dark mode | 7 | 9 | 8 | **8.0** | 1 |
| Mobile app | 9 | 6 | 3 | **6.0** | 3 |
| AI recommendations | 8 | 4 | 4 | **5.3** | 4 |
| Quick filters | 6 | 8 | 9 | **7.7** | 2 |

### Quando Usar ICE vs RICE

**ICE:**
- ✅ Brainstorming inicial
- ✅ Muitas ideias para avaliar rapidamente
- ✅ Early stage
- ❌ Não considera reach

**RICE:**
- ✅ Features bem definidas
- ✅ Dados disponíveis para estimar
- ✅ Planning de roadmap
- ✅ Considera quantas pessoas impacta

---

## 🎪 Opportunity Scoring

### O que é?
Framework baseado em identificar GAPS entre importância e satisfação.

### A Metodologia

1. **Listar Outcomes/Jobs desejados**
2. **Survey users em 2 dimensões:**

```
Para cada outcome:

Importância: "Quão importante é [outcome]?"
1 = Not important
...
10 = Extremely important

Satisfação: "Quão satisfeito estás com solução atual?"
1 = Very dissatisfied
...
10 = Very satisfied
```

3. **Calcular Opportunity Score:**

```
Opportunity Score = Importance + (Importance - Satisfaction)

Quanto MAIOR, mais oportunidade
```

### Exemplo

| Outcome | Importance | Satisfaction | Opportunity | Priority |
|---------|-----------|--------------|-------------|----------|
| Analyze data quickly | 9 | 4 | **14** | 🔴 High |
| Share dashboards | 8 | 7 | **9** | 🟡 Med |
| Export reports | 6 | 8 | **4** | 🟢 Low |
| Customize views | 9 | 5 | **13** | 🔴 High |

**Interpretation:**
- **> 12**: Significant opportunity (underserved important need)
- **8-12**: Moderate opportunity
- **< 8**: Overserved or not important

### Opportunity Matrix

```
      High Importance
          │
Overserved│ Appropriately
          │ Served
──────────┼──────────── Satisfaction
  Under-  │  Table
  served  │  Stakes
          │
      Low Importance
```

**Focus**: Underserved + High Importance (top left)

---

## ⏱️ Cost of Delay

### O que é?
Framework que quantifica o custo de NÃO fazer algo.

### A Lógica

```
Toda decisão de priorização tem um custo:
= O valor perdido por não fazer X agora

Cost of Delay ajuda a tomar decisões economicamente racionais
```

### Como Calcular

#### 1. Estimar Value/Time

```
Feature X gera €10K/mês de revenue
Cost of Delay de 1 mês = €10K

Feature Y gera €5K/mês mas urgente
Cost of Delay de 1 mês = €15K (penalidades + churn)
```

#### 2. CD3 (Cost of Delay Divided by Duration)

```
CD3 = Cost of Delay / Duration

Priorizar por HIGHEST CD3
```

### Exemplo

| Feature | CoD (€/month) | Duration (months) | CD3 | Priority |
|---------|---------------|-------------------|-----|----------|
| Feature A | 50K | 5 | **10K** | 3 |
| Feature B | 30K | 2 | **15K** | 1 |
| Feature C | 40K | 3 | **13.3K** | 2 |

**Action**: Fazer B → C → A

### Cost of Delay Profile Types

#### 1. Standard (Linear)
```
Value lost increases steadily over time
Example: General feature improvements
```

#### 2. Fixed Date (Step Function)
```
Value drops to zero after deadline
Example: Regulatory compliance, seasonal feature
```

#### 3. Intangible
```
Hard to quantify but real cost
Example: Technical debt, team morale
```

---

## 🎯 Prioritization Workshop Format

### Agenda (2 horas)

```
0:00-0:10  Context Setting
           - Business goals
           - Constraints
           - Criteria

0:10-0:30  Individual Scoring
           - Cada pessoa score independentemente
           - Usar framework escolhido

0:30-1:00  Group Discussion
           - Share scores
           - Debate discrepancies
           - Build consensus

1:00-1:30  Ranking
           - Order final
           - Identify quick wins
           - Plan next actions

1:30-2:00  Documentation
           - Capture decisions
           - Assign DRIs
           - Communication plan
```

### Participants

**Core:**
- Product Manager (facilitator)
- Engineering Lead
- Design Lead

**Optional:**
- Customer Success
- Sales
- Data Analyst
- CEO/Founder

⚠️ Manter grupo pequeno (5-7 pessoas máx)

---

## 📋 Prioritization Decision Log

### Template

```markdown
# Feature: [Nome]

**Date**: 2026-03-XX
**Decision**: [Prioritized / Deprioritized / Deferred]
**DRI**: [Nome]

## Context
[Porque considerámos isto]

## Scoring
| Framework | Score | Reasoning |
|-----------|-------|-----------|
| RICE | 450 | High reach, medium impact |
| Value/Effort | Quick Win | Low effort, high value |
| MoSCoW | Should Have | Important but not critical |

## Decision Rationale
[Porque decidimos assim]

## Tradeoffs
**Choosing this means NOT doing:**
- [Alternative 1]
- [Alternative 2]

## Next Steps
- [ ] Action 1
- [ ] Action 2
- [ ] Action 3

## Stakeholder Communication
- Engineering: [Status]
- Design: [Status]
- Sales: [Status]
```

---

## ✅ Prioritization Checklist

**Pre-Prioritization:**
- [ ] Business goals claramente definidos
- [ ] User research completed
- [ ] Technical constraints understood
- [ ] Todas features têm owner
- [ ] Effort estimado

**During Prioritization:**
- [ ] Framework escolhido e comunicado
- [ ] Todos os stakeholders representados
- [ ] Scoring independente antes de discussão
- [ ] Assumptions documented
- [ ] Decisions captured

**Post-Prioritization:**
- [ ] Roadmap atualizado
- [ ] Team comunicado
- [ ] Stakeholders alinhados
- [ ] Next sprint planned
- [ ] Backlog refinado

---

**Próximos passos**: Com prioridades definidas, criar [Product Roadmap](../04-roadmapping/) para comunicar o plano.
