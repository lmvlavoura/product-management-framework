# Jobs-to-be-Done Map — Scoreat

**Date**: 2026-04-07
**Status**: Hipótese — validar com entrevistas
**Author**: Head of Product
**Related**: [Personas](./02-personas.md) · [Review Workflow](./review-workflow.md)

---

## Os 5 Jobs Core do Scoreat

### Job 1 — Não desperdiçar uma refeição

```
QUANDO estou a escolher onde jantar (ou o que pedir)
QUERO saber qual o prato que vale mesmo a pena naquele lugar
PARA NÃO sair de lá com a sensação de ter desperdiçado dinheiro e tempo
```

**Persona**: Tomás (Explorador), Filipa (Habitué)
**Frequência**: Alta — acontece 2-5x por semana para quem come fora regularmente
**Intensidade da dor**: Alta — refeições medíocres custam €15-50 e 1-2 horas
**Solução atual**: Google Maps (inadequada — avalia restaurante, não prato) ⚠️ validar

---

### Job 2 — Guardar o que foi excepcional

```
QUANDO como algo que me surpreende positivamente
QUERO registar o prato, onde foi, e como me senti
PARA conseguir repetir a experiência e recomendar a outros
```

**Persona**: Todos, mas especialmente Filipa e Tomás
**Frequência**: Média — acontece quando há surpresa positiva (1-2x/semana para quem come muito fora)
**Intensidade da dor**: Média — a memória falha, os sítios fecham, os chefs mudam
**Solução atual**: Foto no telemóvel (sem estrutura, sem score, sem contexto) ⚠️ validar

---

### Job 3 — Descobrir o melhor de uma categoria

```
QUANDO quero comer um prato específico (Francesinha, Sushi, Croissant)
QUERO saber qual é a melhor versão disponível perto de mim agora
PARA maximizar o prazer da refeição sem fazer research de horas
```

**Persona**: Lars (Viajante), Tomás (Explorador)
**Frequência**: Média — especialmente antes de jantares especiais ou em viagem
**Intensidade da dor**: Alta em viagem (informação dispersa, pouco confiável, desatualizada)
**Solução atual**: Blogs, Reddit, Google Search — inconsistente e com dados velhos ⚠️ validar

---

### Job 4 — Não ser enganado pela reputação do restaurante

```
QUANDO um restaurante tem boa reputação geral mas menu variado
QUERO saber quais os pratos em que são realmente bons
PARA não pedir algo medíocre num lugar que "toda a gente" recomenda
```

**Persona**: Filipa (Habitué), Lars (Viajante)
**Frequência**: Alta — cada jantar em lugar novo tem este job implícito
**Intensidade da dor**: Alta — a frustração de um "4.7 estrelas" que decepciona é real
**Solução atual**: Ler reviews individualmente no Google/TripAdvisor (demorado, impreciso) ⚠️ validar

---

### Job 5 — Construir identidade gastronómica

```
QUANDO como algo extraordinário
QUERO ter um registo que mostre o meu percurso gastronómico
PARA ter uma identidade culinária que posso partilhar e comparar com outros
```

**Persona**: Tomás (Explorador), utilizadores power
**Frequência**: Baixa — job emocional/social, não funcional
**Intensidade da dor**: Baixa individualmente, mas é o que cria **viral loops**
**Solução atual**: Instagram (sem estrutura de dados), nada para a maioria ⚠️ validar

---

## Jobs Secundários (Não Core nesta Fase)

| Job | Relevância actual | Quando priorizar |
|-----|------------------|-----------------|
| "Planear refeições em viagem" | Baixa (falta de dataset) | Quando Lisboa tiver 1K+ reviews |
| "Descobrir pratos para dietas específicas" | Média | Após MVP validado |
| "Acompanhar tendências culinárias" | Baixa | Escala (10M+ reviews) |
| "Gerir o menu do meu restaurante" | Baixa (B2B) | Após validação consumer |

---

## JTBD Canvas — Job Prioritário para o MVP

O Job #1 ("não desperdiçar uma refeição") é o job com maior frequência + intensidade. É o job que o MVP deve resolver primeiro.

```
┌──────────────────────────────────────────────────────────┐
│ JOB STATEMENT                                            │
│                                                          │
│ Quando estou a escolher o que pedir num restaurante      │
│ (ou a decidir para onde ir)                              │
│ Quero saber qual o prato que realmente vale a pena       │
│ Para não me arrepender da escolha                        │
├──────────────────────────────────────────────────────────┤
│ FUNCTIONAL JOB                                           │
│ Identificar o melhor prato disponível no contexto atual  │
├──────────────────────────────────────────────────────────┤
│ SOCIAL JOB                                               │
│ Ser a pessoa que sabe onde comer — e o quê              │
├──────────────────────────────────────────────────────────┤
│ EMOTIONAL JOB                                            │
│ Sentir que tomou uma boa decisão (não desperdiçou)       │
├──────────────────────────────────────────────────────────┤
│ SUCCESS CRITERIA                                         │
│ 1. A refeição superou expectativas                       │
│ 2. Tomou a decisão em < 2 minutos                        │
│ 3. Quer repetir / recomendar                             │
├──────────────────────────────────────────────────────────┤
│ OBSTACLES ACTUAIS                                        │
│ - Informação existe mas está no sítio errado (reviews   │
│   de restaurante, não de prato)                          │
│ - Reviews são antigas ou irrelevantes                    │
│ - Não sabe em quem confiar                              │
└──────────────────────────────────────────────────────────┘
```

---

## Competing Solutions — Como Resolvem Hoje

| Solução | Job resolvido? | Porque é inadequada |
|---------|---------------|---------------------|
| Google Maps | Parcialmente (#4) | Score é do restaurante, não do prato. Sem filtro por prato. |
| TripAdvisor | Parcialmente (#4) | Idem — orientado a restaurante e experiência geral |
| Instagram | Parcialmente (#2, #5) | Fotos sem estrutura, sem score, sem pesquisa por prato |
| TheFork / OpenTable | Não | Focado em reservas, não em descoberta de prato |
| Blogs / Influencers | Parcialmente (#3) | Dados velhos, subjetivos, não pesquisáveis |
| Amigos | Parcialmente (todos) | Não escalável, depende de quem conheces |
| **Scoreat** | **Todos os 5 jobs** | Prato como entidade de primeira classe + scores estruturados + grafo |

**A janela de oportunidade**: Nenhuma solução atual resolve o Job #1 de forma direta e confiável. O Scoreat é o primeiro produto construído especificamente para este job.
