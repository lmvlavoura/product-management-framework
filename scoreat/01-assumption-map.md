# Assumption Map — Scoreat

**Date**: 2026-04-07
**Status**: Vivo — atualizar após cada sprint
**Author**: Head of Product
**Related**: [Product Vision](./00-product-vision.md) · [30-Day Sprint](./04-30-day-sprint.md)

---

## Como Usar Este Documento

Cada assumption está classificada em duas dimensões (framework de `02-discovery-research.md`):

- **Risco**: se esta assumption estiver errada, qual é o impacto no negócio? (1–5)
- **Certeza**: quanta evidência temos de que está certa? (1–5, onde 1 = quase nenhuma)

**Prioridade de teste = Risco × (5 − Certeza)**

Começar sempre pelas assumptions com **maior prioridade** — são as que podem matar o negócio e que menos sabemos.

---

## Mapa de Assumptions

### Categoria 1 — Desejabilidade (o utilizador quer isto?)

| # | Assumption | Risco (1-5) | Certeza (1-5) | Prioridade | Status |
|---|-----------|------------|--------------|------------|--------|
| D1 | Utilizadores querem registar pratos específicos (não apenas restaurantes) | 5 | 2 | **15** | Por testar |
| D2 | O hábito de review de prato é sustentável — as pessoas voltam semanas depois | 5 | 1 | **20** | Por testar |
| D3 | O "ranking pessoal de pratos" é motivação suficiente para criar hábito | 4 | 1 | **16** | Por testar |
| D4 | Utilizadores acham relevante o score de outros utilizadores num prato específico | 4 | 2 | **12** | Por testar |
| D5 | Utilizadores tiram foto ao prato antes ou durante a refeição | 3 | 3 | **6** | Evidência anedótica |
| D6 | O utilizador português valoriza "o melhor prato" acima de "o melhor restaurante" | 4 | 2 | **12** | Por testar |

**Assumption mais crítica nesta categoria: D2 — o hábito.**
Tudo o resto pode ser iterado. Se as pessoas não voltam a registar pratos na semana 2, não há produto.

---

### Categoria 2 — Viabilidade (conseguimos construir e escalar?)

| # | Assumption | Risco (1-5) | Certeza (1-5) | Prioridade | Status |
|---|-----------|------------|--------------|------------|--------|
| V1 | AI consegue identificar o prato a partir de foto com >75% de precisão | 4 | 2 | **12** | Por testar |
| V2 | O dataset de pratos portugueses é suficientemente estruturado para começar | 3 | 2 | **9** | Por testar |
| V3 | GPS + nome de restaurante resolve a associação prato→restaurante sem fricção | 3 | 3 | **6** | Parcialmente testado |
| V4 | O cold start problem pode ser resolvido com abordagem concierge em Lisboa | 4 | 2 | **12** | Por testar |
| V5 | Uma equipa pequena consegue moderar qualidade do dataset à escala de Portugal | 3 | 3 | **6** | Por testar |

---

### Categoria 3 — Modelo de Negócio (alguém paga?)

| # | Assumption | Risco (1-5) | Certeza (1-5) | Prioridade | Status |
|---|-----------|------------|--------------|------------|--------|
| N1 | Restaurantes pagam por analytics de performance dos seus pratos | 5 | 1 | **20** | Por testar |
| N2 | Utilizadores pagam €7.99/mês por features premium de descoberta | 4 | 1 | **16** | Por testar |
| N3 | Apps de delivery/viagem pagam para licenciar o dish graph | 4 | 1 | **16** | Hipótese estratégica |
| N4 | O CAC via crescimento orgânico (boca-a-boca + conteúdo) é sustentável | 3 | 2 | **9** | Por testar |

---

### Categoria 4 — Mercado (Portugal como beachhead funciona?)

| # | Assumption | Risco (1-5) | Certeza (1-5) | Prioridade | Status |
|---|-----------|------------|--------------|------------|--------|
| M1 | Lisboa tem densidade de early adopters suficiente para validação | 3 | 3 | **6** | Razoavelmente certo |
| M2 | O comportamento alimentar português (jantar fora frequente, orgulho culinário) favorece adoção | 3 | 3 | **6** | Culturalmente plausível |
| M3 | Portugal é suficientemente diferente do Brasil/Espanha para validar globalmente | 3 | 2 | **9** | Por testar |
| M4 | O brand "Scoreat" não bloqueia adoção no mercado PT (pronúncia, memorabilidade) | 2 | 2 | **6** | Risco conhecido, aceitável a curto prazo |

---

## Top 5 Assumptions a Testar AGORA

Ordenadas por prioridade de teste no sprint de 30 dias:

### #1 — D2: O hábito é sustentável (Prioridade: 20)
> "Utilizadores voltam a registar pratos na semana 2 e 3 sem intervenção"

**Porque é a #1**: Se falhar, não há produto. Toda a estratégia de €1B assenta em utilizadores que voltam.

**Como testar**: Onboarding de 20 utilizadores, zero push notifications nas semanas 2-3, medir quantos voltam espontaneamente.

**Critério de pass**: ≥ 40% dos utilizadores que chegaram a 5 reviews voltam na semana seguinte.

**Critério de fail**: < 20% de retorno. Pivot: perceber se o problema é o hábito ou o valor que estamos a mostrar.

---

### #2 — N1: Restaurantes pagam por analytics (Prioridade: 20)
> "Um restaurante paga €200-500/mês para saber como os seus pratos são avaliados vs. concorrência"

**Porque é a #2**: Sem B2B, o caminho para €1B é muito mais lento. E se não houver WTP aqui, a estratégia de receita muda completamente.

**Como testar**: 5 conversas com donos de restaurantes em Lisboa. Mostrar mockup do dashboard. Perguntar diretamente: "Pagavas €200/mês por isto?"

**Critério de pass**: 3/5 dizem "sim" ou "talvez" e conseguem articular o valor.

**Critério de fail**: Resposta dominante é "não" ou "o Google já me dá isso de graça."

---

### #3 — D1: Utilizadores querem registar pratos (não restaurantes) (Prioridade: 15)
> "A proposta dish-centric ressoa — utilizadores entendem e valorizam registar o prato específico"

**Porque é a #3**: Se as pessoas só querem avaliar restaurantes, somos uma versão pior do TripAdvisor.

**Como testar**: 10 entrevistas com early adopters. Mostrar dois flows: dish-first vs. restaurant-first. Observar qual provoca mais entusiasmo e melhor retenção de 1 semana.

**Critério de pass**: 7/10 preferem o flow dish-first e conseguem articular porquê.

**Critério de fail**: Indiferença ou confusão. Sinal de que o conceito não ressoa naturalmente.

---

### #4 — D3: Ranking pessoal cria hábito (Prioridade: 16)
> "Ver o teu ranking pessoal de 'melhores bacalhaus que já comi' é motivação para continuar a usar"

**Porque é a #4**: O aha moment que desenhamos no review workflow depende disto. Se não cria emoção, o loop não fecha.

**Como testar**: No onboarding de utilizadores do sprint, registar reação qualitativa ao ver o primeiro ranking. Net Promoter Score no D7.

**Critério de pass**: Reação espontânea positiva + NPS > 30 no D7.

**Critério de fail**: Indiferença ao ver o ranking. Requer repensar o aha moment.

---

### #5 — V4: Cold start resolve-se com concierge (Prioridade: 12)
> "Conseguimos construir dataset suficiente em Lisboa manualmente para que a descoberta tenha valor"

**Porque é a #5**: Sem dados, a discovery feature não funciona, e sem discovery o produto fica limitado ao registo pessoal.

**Como testar**: Em 30 dias, mapear manualmente os top 50 pratos de Lisboa (com score, foto, restaurante). Testar se utilizadores sentem que há "suficiente" para descobrir.

**Critério de pass**: Utilizadores conseguem encontrar 3+ pratos relevantes na sua cidade que não conheciam.

**Critério de fail**: "Não há nada aqui" — dataset percebido como vazio.

---

## Assumptions Validadas

*(preencher após testes)*

| # | Assumption | Resultado | Data | Evidência |
|---|-----------|-----------|------|-----------|
| — | — | — | — | — |

---

## Assumptions Invalidadas

*(preencher após testes — estas são as mais valiosas)*

| # | Assumption | O que descobrimos | Impacto | Decisão |
|---|-----------|------------------|---------|---------|
| — | — | — | — | — |

---

## Próxima Revisão

Este documento deve ser atualizado no **fim de cada semana do sprint**.  
Cada assumption testada move-se para "Validadas" ou "Invalidadas" — nunca fica em "Por testar" indefinidamente.
