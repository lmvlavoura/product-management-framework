# Competitive Positioning — Scoreat

**Date**: 2026-04-07
**Status**: Revisto trimestralmente
**Author**: Head of Product
**Related**: [Product Vision](./00-product-vision.md) · [JTBD Map](./03-jtbd-map.md)

---

## A Verdade Inconfortável

Os nossos concorrentes são maiores, têm mais recursos, e têm dados que nós não temos ainda.

Mas todos cometeram o mesmo erro estrutural: **construíram para o restaurante, não para o prato.** Inverter isto depois de 10-20 anos de produto é extraordinariamente difícil — implica rearquitetar o modelo de dados, re-treinar utilizadores, e re-explicar o produto ao mercado. Nenhum deles vai fazer isso por nós.

Esta janela não dura para sempre. O objetivo é tornarmo-nos o *standard* de dish data antes que alguém grande decida que isto importa.

---

## Landscape Competitivo

### Competidores Diretos (resolvem discovery de comida)

| Player | Foco | Dish-centric? | Dataset qualidade | Moat |
|--------|------|--------------|------------------|------|
| **Google Maps** | Tudo | ❌ Restaurante | Imenso mas não estruturado por prato | Distribuição + SEO |
| **TripAdvisor** | Restaurantes + hotéis | ❌ Restaurante | Grande, envelhecido | Brand + SEO |
| **TheFork** | Reservas | ❌ Reservas | Pequeno, europeu | Integração restaurantes |
| **Zomato** | Restaurantes + delivery | ⚠️ Parcial (menu) | Grande, Índia/EM | App stickiness |
| **Yelp** | Restaurantes | ❌ Restaurante | EUA-centric | Comunidade local |
| **OpenTable** | Reservas | ❌ Reservas | EUA/UK | B2B restaurant network |

### Competidores Indiretos (satisfazem o mesmo job de outra forma)

| Player | Como satisfaz o job | Falha crítica |
|--------|--------------------|--------------| 
| **Instagram** | Inspiração visual de pratos | Sem score, sem pesquisa, sem estrutura |
| **Reddit** (r/food, grupos locais) | Recomendações peer-to-peer | Não escalável, não pesquisável, dados velhos |
| **Blogs / influencers** | Listicles "melhores X de Lisboa" | Não atualizados, subjetivos, não confiáveis |
| **Amigos / WhatsApp** | Recomendação pessoal | Não escalável, depende de rede |
| **Michelin / Time Out** | Curadoria editorial | Elitista, não democrático, não granular |

### Quem Poderia Ser Perigoso (mas ainda não é)

**Google** — o risco mais sério a longo prazo. Tem distribuição, dados, e AI. Se decidir que "best dish near me" é um use case relevante, pode construir isto em 12 meses. **A defesa: velocidade + dataset quality.** O Google não construirá reviews verificadas prato a prato — vai scraping e AI. Nós teremos dados humanos verificados com scores e contexto que AI não consegue fabricar.

**TikTok / Instagram** — já têm um produto de recomendação de comida emergente (lugares "virais"). O risco é que isto substitua a descoberta estruturada para uma geração mais nova. **A defesa: conteúdo viral ≠ informação confiável.** Ninguém toma decisões de refeição com base em um TikTok sem confirmar.

---

## Matriz de Comparação — Jobs-to-be-Done

| Job | Google Maps | TripAdvisor | Instagram | **Scoreat** |
|-----|------------|-------------|-----------|------------|
| Não desperdiçar uma refeição | ⚠️ Parcial | ⚠️ Parcial | ❌ | ✅ |
| Guardar o que foi excepcional | ❌ | ❌ | ⚠️ Parcial | ✅ |
| Descobrir o melhor de uma categoria | ⚠️ Parcial | ⚠️ Parcial | ❌ | ✅ |
| Não ser enganado pela reputação | ❌ | ❌ | ❌ | ✅ |
| Construir identidade gastronómica | ❌ | ❌ | ⚠️ Parcial | ✅ |

---

## O Nosso Espaço — Positioning Map

```
                    DISH-CENTRIC
                         │
                         │
                   SCOREAT ●
                         │
                         │
DISCOVERY ───────────────┼─────────────── RESERVATIONS
                         │
         Instagram ●     │     TheFork ●   OpenTable ●
                         │
    TripAdvisor ●        │
      Google Maps ●      │         Zomato ●
                         │
                    RESTAURANT-CENTRIC
```

Estamos sozinhos no quadrante **dish-centric + discovery**. Esta é a posição que queremos defender.

---

## Posicionamento em Uma Frase

**Para utilizadores**:
> "O Scoreat é a única forma de saber qual o melhor prato específico perto de ti — não o melhor restaurante."

**Para restaurantes (B2B)**:
> "O Scoreat mostra como cada prato do teu menu está a ser avaliado — não a experiência geral."

**Para parceiros e investidores**:
> "O Scoreat está a construir o Global Dish Graph — o dataset estruturado de pratos que não existe em nenhum lugar do mundo."

---

## Como Defendemos o Moat

### Barreira 1 — Dataset (principal)
Um competidor que decida entrar dish-first hoje está 2-3 anos atrás de nós em dados verificados. Dados de qualidade não se fabricam com AI — precisam de utilizadores reais a submeter reviews reais.

**Ação**: maximizar velocidade de crescimento do dataset. Cada review é um tijolo do moat.

### Barreira 2 — Network effects
O Scoreat fica melhor à medida que mais pessoas usam: mais reviews → melhores scores → melhor descoberta → mais utilizadores → mais reviews. Plataformas com network effects são difíceis de deslocar mesmo por concorrentes com mais recursos.

**Ação**: atingir massa crítica em Lisboa antes de qualquer concorrente local ganhar tração dish-centric.

### Barreira 3 — Estrutura de dados
Não basta ter reviews — é preciso ter reviews estruturadas com o prato como entidade própria (não uma string de texto). A nossa arquitectura de dados é o que diferencia um "review com nome de prato" de um "nó do dish graph". Esta estrutura é o que torna o dataset licenciável a terceiros.

**Ação**: investir em qualidade de dados desde o início. Não aceitar shortcuts que degradem a estrutura.

---

## Mensagem Anti-Competitiva (O que Dizemos Quando nos Comparam)

**"O Google Maps já tem reviews de comida."**
> "Sim, mas avalia o restaurante — não o prato. Se quiseres saber se o Bacalhau à Brás de um restaurante específico é bom, o Google não te diz. O Scoreat diz."

**"O TripAdvisor tem fotos de comida."**
> "Fotos sem score, sem estrutura, não pesquisáveis por prato. É como ter uma biblioteca sem índice."

**"O Instagram tem muita comida."**
> "Inspiração visual não é informação confiável. Não tomas a decisão de onde jantar com base num vídeo viral."

**"Um restaurante já me pode dar o menu."**
> "O menu diz o que existe. O Scoreat diz o que vale a pena."
