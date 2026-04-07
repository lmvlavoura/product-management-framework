# User Personas — Scoreat

**Date**: 2026-04-07
**Status**: Hipótese — validar com entrevistas no sprint de 30 dias
**Author**: Head of Product
**Related**: [JTBD Map](./03-jtbd-map.md) · [Assumption Map](./01-assumption-map.md)

---

## Nota Metodológica

Estas personas são construídas com base em:
- Padrões de comportamento alimentar em Portugal (cultural + demográfico)
- Analogias com adoção de produtos similares (Untappd para cerveja, Letterboxd para filmes)
- Assumptions sobre quem se identifica com "o prato acima do restaurante"

São **hipóteses**, não factos. Cada claim marcado com ⚠️ precisa de validação no sprint de 30 dias.

---

## Persona 1 — "O Explorador"

```
┌──────────────────────────────────────────────────────────┐
│ TOMÁS · 28 anos · Product Designer                       │
│ "Cada refeição é uma decisão. Não quero desperdiçá-la."  │
├──────────────────────────────────────────────────────────┤
│ BACKGROUND                                               │
│ Lisboa (Mouraria / Príncipe Real)                        │
│ Come fora 4-5x por semana                                │
│ Viaja 6-8x por ano (Europa + Ásia)                       │
│ Segue conteúdo de comida no Instagram e YouTube          │
│ Já usou: Google Maps, TheFork, TripAdvisor               │
├──────────────────────────────────────────────────────────┤
│ GOALS                                                    │
│ 1. Não repetir uma refeição medíocre                     │
│ 2. Encontrar os pratos "secretos" das cidades que visita │
│ 3. Ter um registo do que comeu e onde — memória culinária│
│ 4. Recomendar pratos específicos (não restaurantes) ⚠️   │
├──────────────────────────────────────────────────────────┤
│ FRUSTRAÇÕES                                              │
│ 1. O Google Maps diz "bom restaurante" mas não          │
│    sabe se o prato que ele quer é bom lá                 │
│ 2. Reviews no TripAdvisor são sobre a experiência,      │
│    nunca sobre o prato específico                        │
│ 3. Instagram tem fotos bonitas mas zero informação útil  │
│ 4. Quando viaja, perde tempo a pesquisar o que comer    │
├──────────────────────────────────────────────────────────┤
│ MOTIVAÇÕES                                               │
│ - Status social: recomendar pratos aos amigos ⚠️         │
│ - Controlo: não ser surpreendido negativamente           │
│ - Descoberta: o prazer de encontrar algo excepcional     │
│ - Memória: guardar as melhores refeições da sua vida     │
├──────────────────────────────────────────────────────────┤
│ COMPORTAMENTOS                                           │
│ Tech savviness:  ██████████ 10/10                       │
│ Frequência fora: ████████░░ 8/10                        │
│ Disposição pay:  ████████░░ 8/10                        │
│                                                          │
│ Já tira fotos à comida: Sim, sempre ⚠️                  │
│ Partilha nas redes: Ocasionalmente                       │
│ Influência nos amigos: Alta — é o "go-to" para onde ir  │
├──────────────────────────────────────────────────────────┤
│ QUOTE ⚠️ (hipótese — validar com entrevistas)            │
│ "Eu não procuro restaurantes. Procuro o melhor ramen     │
│ de Lisboa. E depois vejo onde está."                     │
├──────────────────────────────────────────────────────────┤
│ CENÁRIO DE USO                                           │
│ Sexta à tarde. Tomás quer jantar com a namorada.         │
│ Pesquisa no Scoreat "ramen Lisboa" → vê ranking de       │
│ pratos com scores reais → escolhe o #1 → vai jantar     │
│ → regista o prato → fica #2 no seu ranking pessoal      │
│ de ramen. Partilha com o grupo de amigos.               │
└──────────────────────────────────────────────────────────┘
```

**Importância para o produto**: O Tomás é o early adopter perfeito. Adota cedo, usa intensamente, e tem efeito de rede (recomenda a amigos). O risco: pode ser demasiado tech-savvy para representar o utilizador médio a longo prazo.

---

## Persona 2 — "A Habitué"

```
┌──────────────────────────────────────────────────────────┐
│ FILIPA · 41 anos · Gestora de Projeto                    │
│ "Tenho os meus sítios. Mas quero perceber se estou       │
│  a deixar passar algo melhor."                           │
├──────────────────────────────────────────────────────────┤
│ BACKGROUND                                               │
│ Porto (Bonfim / Foz)                                     │
│ Come fora 2-3x por semana                                │
│ 2 filhos, janta fora com família e amigos                │
│ Tem restaurantes favoritos há anos                       │
│ Já usou: Google Maps reviews (lê, raramente escreve)     │
├──────────────────────────────────────────────────────────┤
│ GOALS                                                    │
│ 1. Confirmar que os seus lugares favoritos continuam bons│
│ 2. Ter algo novo para sugerir quando os amigos perguntam │
│ 3. Perceber se vale a pena ir a um restaurante novo ⚠️   │
│ 4. Guardar os pratos que os filhos adoram                │
├──────────────────────────────────────────────────────────┤
│ FRUSTRAÇÕES                                              │
│ 1. Restaurante "4.5 estrelas" mas o prato que pediu     │
│    foi dececionante — não há forma de saber antes        │
│ 2. Amigos recomendam restaurantes, ela quer saber       │
│    "mas o que é que lá pediste?"                         │
│ 3. Não tem onde guardar os pratos que quer repetir      │
├──────────────────────────────────────────────────────────┤
│ MOTIVAÇÕES                                               │
│ - Confiança: tomar boas decisões para a família          │
│ - Memória partilhada: guardar momentos com os filhos     │
│ - Pertença: fazer parte de uma comunidade que entende ⚠️ │
├──────────────────────────────────────────────────────────┤
│ COMPORTAMENTOS                                           │
│ Tech savviness:  ██████░░░░ 6/10                        │
│ Frequência fora: ██████░░░░ 6/10                        │
│ Disposição pay:  ██████░░░░ 6/10 (se valor for claro)   │
│                                                          │
│ Tira fotos à comida: Às vezes (dias especiais)           │
│ Partilha nas redes: Raramente                            │
│ Influência: Alta no círculo próximo (família, colegas)   │
├──────────────────────────────────────────────────────────┤
│ QUOTE ⚠️                                                 │
│ "Quero saber se o prato é bom — não se o restaurante    │
│  tem boa decoração."                                     │
├──────────────────────────────────────────────────────────┤
│ CENÁRIO DE USO                                           │
│ Filipa vai ao seu restaurante favorito do Porto.         │
│ Regista a Francesinha que come há 10 anos. Vê que o     │
│ score desceu nas últimas semanas (outros utilizadores    │
│ também notaram). Decide experimentar um novo lugar       │
│ que está a subir no ranking de Francesinhas do Porto.    │
└──────────────────────────────────────────────────────────┘
```

**Importância para o produto**: A Filipa representa o utilizador de massa — não é entusiasta tech, mas tem um caso de uso claro e frequente. É ela que determina se o produto tem vida além dos early adopters.

---

## Persona 3 — "O Viajante"

```
┌──────────────────────────────────────────────────────────┐
│ LARS · 34 anos · Engenheiro de Software (Berlim)         │
│ "Quando viajo, quero comer o que os locais comem.        │
│  Não o que os turistas comem."                           │
├──────────────────────────────────────────────────────────┤
│ BACKGROUND                                               │
│ Berlim (base) · viaja 10-12x por ano                    │
│ Portugal 2-3x por ano (surf + comida)                    │
│ Usa Google Maps, TripAdvisor, Reddit /r/travel           │
│ Já usou: Yelp, OpenTable                                 │
├──────────────────────────────────────────────────────────┤
│ GOALS                                                    │
│ 1. Comer o prato "certo" em cada cidade que visita      │
│ 2. Não cair em armadilhas turísticas                    │
│ 3. Descobrir pratos que não sabia que existiam           │
│ 4. Ter memória organizada das refeições de viagem ⚠️     │
├──────────────────────────────────────────────────────────┤
│ FRUSTRAÇÕES                                              │
│ 1. TripAdvisor em Lisboa está cheio de restaurantes     │
│    para turistas — não sabe distinguir                   │
│ 2. Pesquisa "best bacalhau Lisboa" e encontra           │
│    listas de 2018 em blogs sem credibilidade             │
│ 3. Não tem como saber se um prato é sazonal ou se       │
│    está disponível agora                                 │
├──────────────────────────────────────────────────────────┤
│ MOTIVAÇÕES                                               │
│ - Autenticidade: comer como local ⚠️                     │
│ - Eficiência: não desperdiçar uma refeição em viagem     │
│ - Storytelling: ter histórias de pratos para contar     │
├──────────────────────────────────────────────────────────┤
│ COMPORTAMENTOS                                           │
│ Tech savviness:  ██████████ 10/10                       │
│ Disposição pay:  ████████░░ 8/10                        │
│ Tira fotos à comida: Sempre em viagem                   │
│ Partilha: Muito (Instagram stories, grupos de amigos)   │
├──────────────────────────────────────────────────────────┤
│ QUOTE ⚠️                                                 │
│ "Diz-me qual é o melhor prato desta cidade e onde       │
│  posso comê-lo. O resto é secundário."                   │
├──────────────────────────────────────────────────────────┤
│ CENÁRIO DE USO                                           │
│ Lars chega a Lisboa na quinta-feira. Abre o Scoreat,    │
│ filtra por "Lisboa · pratos de destaque · alta pontuação"│
│ → vê top 10 pratos da cidade com scores verificados →   │
│ agenda jantar no restaurante com melhor Bacalhau à Brás  │
│ → regista a experiência → deixa review em inglês.       │
└──────────────────────────────────────────────────────────┘
```

**Importância para o produto**: O Lars é o utilizador que activa o loop de descoberta — a sua review alimenta o dataset e ajuda utilizadores locais. É também o que justifica internacionalização: se o produto funciona para turistas em PT, funciona para portugueses em Barcelona.

---

## Persona Negativa (Quem NÃO é o nosso utilizador)

**"O Gastronómico"** — critico de gastronomia, sommelier, chef. Quer profundidade técnica (terroir, técnica, harmonização). O Scoreat não é para ele. O nosso score é democrático — é o que o utilizador comum sente, não o que o especialista classifica.

**"O Delivery User"** — usa apps de delivery exclusivamente, nunca come fora. Não é o utilizador core desta fase. Pode ser relevante num futuro produto B2B com Uber Eats / Glovo.

---

## Hierarquia de Personas para o Sprint de 30 Dias

1. **Tomás (Explorador)** — target para early adopters e dataset seed
2. **Filipa (Habitué)** — target para validar retenção de massa
3. **Lars (Viajante)** — persona de longo prazo; irrelevante no sprint se não tiver dataset

**Decisão de produto**: o sprint de 30 dias foca em Tomás e Filipa. Lars só se torna relevante quando Lisboa tiver 1.000+ reviews verificadas — altura em que o produto tem valor para um turista.
