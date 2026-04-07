# Plano de Validação — Sprint de 30 Dias

**Date**: 2026-04-07
**Status**: Pronto para execução
**Author**: Head of Product
**Related**: [Assumption Map](./01-assumption-map.md) · [NSM](./north-star-metric.md) · [Review Workflow](./review-workflow.md)

---

## Objetivo do Sprint

**Provar ou desprovar uma coisa**: o core value loop do Scoreat sustenta-se sem intervenção manual depois da primeira semana.

```
[Utilizador regista prato] → [Vê ranking pessoal] → [Volta a registar]
```

Se ao fim de 30 dias este loop não existir organicamente, há um problema no produto — não no marketing. A resposta é pivot, não mais crescimento.

---

## Critério de Go / No-Go (Fim do Dia 30)

| Métrica | No-Go | Inconclusivo | Go |
|---------|-------|-------------|-----|
| NSM: reviews/semana (activated users) | < 5 | 5–15 | > 15 |
| Activation rate (→ 5 reviews) | < 15% | 15–30% | > 30% |
| D30 retention (activated users) | < 20% | 20–35% | > 35% |
| Qualitative: utilizadores descrevem valor sem prompt | < 3/10 | 3–6/10 | > 6/10 |
| Willingness to recommend (1-10) | < 6 | 6–7 | > 7 |

**Se resultado = Go**: avançar para fase de crescimento controlado (50 utilizadores → 500)
**Se resultado = Inconclusivo**: estender sprint mais 2 semanas com hipótese específica a testar
**Se resultado = No-Go**: sessão de análise das assumptions falhadas → pivot

---

## Semana 1 — Seed (Dias 1–7)

### Objetivo
Recrutar 20 utilizadores, onboardar manualmente, e construir o dataset seed de Lisboa.

### Tarefas

**Dataset seed (concierge approach)**
- [ ] Mapear manualmente os top 50 pratos de Lisboa (10 categorias × 5 pratos cada)
- [ ] Categorias: Bacalhau, Pastel de Nata, Francesinha (Porto), Bifanas, Marisco, Sushi Lisboa, Hambúrgueres artesanais, Ovos Mexidos, Pizza, Gelado artesanal
- [ ] Para cada prato: nome, restaurante, foto, score editorial (1-10 interno), coordenadas
- [ ] Esta é a "isca" — sem dados, não há descoberta; sem descoberta, não há razão para o loop fechar

**Recrutamento de utilizadores**
- [ ] 20 utilizadores via rede pessoal + comunidades food em Lisboa (Facebook groups, Reddit PT, Discord)
- [ ] Perfil target: Persona Tomás (25-35, come fora frequentemente, smartphone nativo)
- [ ] Evitar: amigos próximos (enviesamento de simpatia), chefs, críticos gastronómicos (não são o target)
- [ ] Incentivo: acesso antecipado + "o teu feedback molda o produto"

**Onboarding manual (Concierge)**
- [ ] Sessão individual de 15 min com cada utilizador (presencial ou videochamada)
- [ ] Guiar no primeiro review ao vivo
- [ ] Deixar o utilizador usar sozinho a partir daí — sem mais assistência
- [ ] Documentar: tempo de completion do primeiro review, dúvidas, reações ao ranking pessoal

**Setup de tracking**
- [ ] Evento `dish_review_submitted` com propriedades: `user_id`, `user_total_reviews`, `entry_point`, `completion_time_seconds`
- [ ] Dashboard mínimo: NSM + activation rate + D7 retention
- [ ] Ferramenta: Mixpanel (free tier suficiente nesta fase)

---

## Semana 2 — Observação (Dias 8–14)

### Objetivo
Observar comportamento sem intervenção. Não enviar push notifications, não fazer follow-up.

### Tarefas

**Monitorização passiva**
- [ ] Dashboard review diária (10 min/dia): quantos utilizadores voltaram? Quantos reviews?
- [ ] Identificar utilizadores que chegaram a 5 reviews (ativados)
- [ ] Anotar padrões: que dia da semana? A que horas? Que tipo de prato?

**Entrevistas de meio-sprint (5 utilizadores)**
- [ ] Selecionar: 2 utilizadores muito ativos + 2 pouco ativos + 1 que não voltou
- [ ] Pergunta central: "Conta-me como foi a tua experiência esta semana"
- [ ] Não mostrar o produto durante a entrevista — deixar falar livremente
- [ ] Aplicar The Mom Test: focar em comportamento passado, não em intenções futuras

**Teste de hipótese D1 (dish-centric vs restaurant-centric)**
- [ ] Perguntar a 5 utilizadores: "O que é mais útil para ti — saber que um restaurante é bom, ou saber que um prato específico é bom?"
- [ ] Registar resposta espontânea antes de qualquer prompt

---

## Semana 3 — Iteração (Dias 15–21)

### Objetivo
Aplicar 1-2 melhorias baseadas nos dados das semanas 1-2. Não mais.

### Regra de Ouro
Só melhorar o que os dados mostram que está a bloquear o loop. Não melhorar por intuição.

### Tarefas

**Análise dos dados de Semana 2**
- [ ] Onde abandona o fluxo de review? (Passo 1, 2, 3, 4?)
- [ ] Utilizadores ativados: o que têm em comum?
- [ ] Utilizadores que não voltaram: o que faltou?

**Iteração (máximo 2 changes)**
- [ ] Escolher a change com maior impacto esperado no NSM
- [ ] Implementar e medir na semana 4
- [ ] Exemplos possíveis: mudar o "aha moment" do passo 6, simplificar passo de identificação de prato, adicionar notificação de "adicionamos novos pratos perto de ti"

**Teste da hipótese N1 (WTP restaurantes)**
- [ ] 5 conversas com donos ou gestores de restaurantes em Lisboa
- [ ] Script: "Temos X reviews do vosso restaurante no Scoreat, com scores por prato. Mostramos o vosso Bacalhau à Brás com 7.2/10 vs. média da categoria de 6.8/10. Pagavas €200/mês para ver isto em dashboard, com benchmark dos vossos concorrentes?"
- [ ] Registar: reação, objeções, WTP espontâneo

---

## Semana 4 — Medição Final (Dias 22–30)

### Objetivo
Medir resultados finais, tomar a decisão de Go/No-Go, documentar learnings.

### Tarefas

**Medição do NSM**
- [ ] Calcular NSM final: reviews/semana por utilizadores ativados
- [ ] Comparar com targets da tabela de Go/No-Go
- [ ] Calcular activation rate, D30 retention

**Entrevistas finais (10 utilizadores)**
- [ ] Pergunta 1: "Numa escala de 1-10, quanto recomendarias o Scoreat a um amigo?"
- [ ] Pergunta 2: "O que teria de mudar para seres um utilizador regular?"
- [ ] Pergunta 3: "Descreveste o Scoreat a alguém esta semana? O que disseste?"
- [ ] Pergunta 4: "O que é que o Scoreat faz que nenhuma outra app faz?"

**Documentar resultados**
- [ ] Atualizar [Assumption Map](./01-assumption-map.md) com resultados de cada assumption testada
- [ ] Redigir Sprint Retrospective (1 página)
- [ ] Decisão: Go / Inconclusivo / No-Go + rationale

---

## O que NÃO fazemos neste Sprint

- Não fazemos marketing ou paid acquisition
- Não otimizamos a UI para conversão — testamos o conceito, não o polimento
- Não construímos features novas que não estavam planeadas
- Não expandimos para fora de Lisboa
- Não fazemos PR ou press
- Não abrimos o produto ao público geral

**Porquê**: com 20 utilizadores, qualquer sinal de tração é demasiado frágil para escalar. Primeiro provamos o loop, depois abrimos a torneira.

---

## Budget do Sprint

| Item | Custo estimado |
|------|---------------|
| Recrutamento (incentivos, café com utilizadores) | €200 |
| Mixpanel free tier | €0 |
| Dataset seed (refeições para fotos + reviews editoriais) | €300 |
| Entrevistas com restaurantes (deslocações) | €50 |
| **Total** | **€550** |

---

## Responsabilidades

| Área | DRI |
|------|-----|
| Recrutamento e onboarding de utilizadores | Founder |
| Dataset seed (Lisboa top 50) | Founder + Head of Product |
| Tracking setup (Mixpanel) | Eng |
| Entrevistas de utilizadores | Head of Product |
| Entrevistas com restaurantes | Founder |
| Dashboard de métricas | Eng |
| Decisão Go/No-Go | Founder + Head of Product |
