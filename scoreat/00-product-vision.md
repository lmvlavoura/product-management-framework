# Product Vision — Scoreat

**Date**: 2026-04-07
**Status**: Approved — foundation document
**Author**: Head of Product
**Review**: Quarterly

---

## The One-Line Vision

> **Scoreat é a infraestrutura de inteligência de pratos do mundo** — o grafo que transforma cada refeição numa decisão melhor.

---

## O Insight Fundamental

O mundo come mil milhões de refeições em restaurantes por dia. E ainda não existe uma base de dados estruturada, pesquisável e confiável de **pratos**.

O Google tem restaurantes. O TripAdvisor tem restaurantes. O Yelp tem restaurantes. O Instagram tem fotos de comida sem estrutura. Ninguém tem pratos como entidade de primeira classe — com score, identidade, história, comparação geográfica.

Isto não é um gap de features. É um gap estrutural de 20 anos que nenhum player resolveu porque todos construíram produto de fora para dentro: **o restaurante como protagonista, o prato como detalhe.**

Scoreat inverte isto. **O prato é o protagonista. O restaurante é contexto.**

Esta inversão cria um produto diferente, um dataset diferente, e um moat diferente.

---

## O Produto

### Hoje (Fase de Validação — Portugal)
Uma app que permite registar e avaliar pratos específicos que comeste, construindo um ranking pessoal por categoria de culinária.

O valor imediato: "Qual é o melhor Bacalhau à Brás que já comi? E onde posso encontrar um melhor?"

### Amanhã (Fase de Crescimento — Europa + Brasil)
Uma plataforma de descoberta dish-centric. Antes de sair para jantar, pesquisas o prato — não o restaurante. O Scoreat mostra onde está a melhor versão desse prato perto de ti, com scores reais de utilizadores reais.

### Em 5 Anos (Escala Global)
O Global Dish Graph como infraestrutura. Uma camada de inteligência alimentar que serve consumidores, restaurantes, e parceiros B2B. O equivalente ao que o Google Maps é para localização — mas para pratos.

---

## O Global Dish Graph

O produto de consumo é a superfície. O asset real é o grafo.

```
Nó: Prato
├── nome (normalizado + variantes regionais)
├── categoria (pasta, peixe, carne, sobremesa...)
├── cozinha (portuguesa, italiana, japonesa...)
├── score médio global
├── score médio por cidade
├── score médio por restaurante
├── ingredientes principais (estruturado)
├── alergénios
├── faixa de preço
└── fotos verificadas

Edge: Prato → Restaurante
├── score médio neste restaurante
├── número de reviews
├── tendência (a melhorar / piorar)
├── "prato de destaque" (flag)
└── preço neste restaurante

Edge: Prato → Prato (relações)
├── "versão regional de"
├── "ingrediente partilhado com"
└── "frequentemente pedido com"
```

Quando este grafo tiver escala — 10M+ reviews verificadas em centenas de cidades — torna-se impossível de replicar. Não porque a tecnologia é difícil. Porque os dados demoram anos a acumular com qualidade.

**Este é o moat. Não a app. O grafo.**

---

## O Negócio a 5 Anos

### Quatro Alavancas de Receita

**1. Consumer Premium** (Year 2+)
€7.99/mês para poder users: modo viagem ("melhores pratos em Barcelona para mim"), filtros de dieta, histórico ilimitado, listas partilháveis.

**2. Restaurant Intelligence** (Year 3+)
B2B SaaS para restaurantes: dashboard com performance dos seus pratos vs. categoria, benchmark competitivo, alertas de queda de score. €200-500/restaurante/mês.

**3. Data API + Licensing** (Year 4+)
Licenciamento do dish graph a apps de delivery, plataformas de viagem, cadeias hoteleiras, seguradoras de saúde. Contratos enterprise €50K-500K/ano.

**4. Dish-Level Discovery Ads** (Year 3+)
Promoted dishes no feed de descoberta. Não anúncios de restaurante — anúncios de prato específico. CPM 3-5x superior ao digital tradicional por ser contextualmente relevante.

### O Caminho para €1B de Valuation

```
Ano 1 — Portugal (Prova de conceito)
├── 10.000 utilizadores ativos
├── 100.000 reviews verificadas
├── 5.000 pratos únicos mapeados em Lisboa + Porto
└── PMF confirmado: NSM cresce semana a semana

Ano 2 — Brasil + Espanha (Expansão de língua)
├── 200.000 utilizadores ativos
├── 2M reviews
├── Lançamento B2C premium (5% conversão)
└── MRR: €80K

Ano 3 — Europa (Escala)
├── 2M utilizadores ativos
├── 20M reviews
├── Lançamento Restaurant Intelligence (B2B)
├── Primeiros contratos de data licensing
└── ARR: €5M

Ano 4 — Global Push
├── 10M utilizadores ativos
├── 100M reviews
├── Dish graph como API pública (freemium + enterprise)
└── ARR: €30M

Ano 5 — Infraestrutura
├── 50M utilizadores ativos
├── 500M reviews
├── Scoreat como camada de dados alimentar global
└── ARR: €100M+ → Valuation €500M–€1.5B (10x revenue múltiplo)
```

### A Lógica do €1B

A referência mais próxima: Foursquare vendeu a sua divisão de dados de localização por $775M em 2024 — com muito menos reviews que o Scoreat precisará de ter. O dish graph é mais estruturado, mais difícil de replicar, e mais próximo de uma decisão de compra do que dados de check-in.

A segunda referência: TheFork (adquirida pela TripAdvisor por €900M) — sem dish graph, apenas reservas. Com dish intelligence, o TAM é superior.

O múltiplo de €100M ARR a 10x (razoável para um data platform com network effects) dá €1B. O caminho é agressivo mas não irrealista — exige execução disciplinada a partir de hoje.

---

## O Que Pode Correr Mal (e Como Defender)

| Risco | Probabilidade | Mitigation |
|-------|--------------|------------|
| Google lança dish-centric Maps | Média | Velocidade de execução + dataset depth que Google não tem incentivo a construir |
| TripAdvisor pivota dish-first | Baixa | Legado de 20 anos de UX restaurant-centric é difícil de desmantelar internamente |
| Cold start problem bloqueia discovery | Alta | Concierge approach em Portugal: construir dataset manualmente antes de escalar |
| Brand "Scoreat" limita expansão global | Média | Decisão de rename avaliada antes da Série A (antes de Ano 2) |
| Utilizadores não desenvolvem hábito de review | Alta | O risco mais crítico — é o que os 30 dias de validação vão testar |

---

## O que NÃO Somos

- Não somos um agregador de restaurantes (TripAdvisor, Zomato)
- Não somos uma plataforma de delivery (Uber Eats, Glovo)
- Não somos uma rede social de comida (Instagram Food)
- Não somos um guia de restaurantes (Michelin, Time Out)

Somos a **camada de inteligência de pratos** que falta a todos eles — e que qualquer um deles um dia vai querer comprar ou licenciar.

---

## Princípios de Produto (Não Negociáveis)

1. **Dish-first, sempre.** Qualquer feature que coloque o restaurante à frente do prato está errada.
2. **Dataset quality over quantity.** 100.000 reviews verificadas valem mais que 1M reviews de baixa qualidade.
3. **Português natural, sem jargão.** O utilizador não sabe o que é "curadoria". Sabe o que é "os melhores pratos perto de ti."
4. **O grafo é o produto.** A app é apenas a interface mais óbvia para o construir.
5. **Velocidade de aprendizagem acima de velocidade de construção.** Aprender rápido e barato é mais valioso que construir rápido e errado.
