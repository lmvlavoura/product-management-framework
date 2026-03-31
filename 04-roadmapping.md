# 4. Product Roadmapping

## 📋 Índice
1. [O que é um Roadmap](#o-que-é-um-roadmap)
2. [Types of Roadmaps](#types-of-roadmaps)
3. [Now-Next-Later Roadmap](#now-next-later-roadmap)
4. [Theme-Based Roadmap](#theme-based-roadmap)
5. [Outcome-Based Roadmap](#outcome-based-roadmap)
6. [Roadmap Communication](#roadmap-communication)
7. [Common Pitfalls](#common-pitfalls)

---

## 🗺️ O que é um Roadmap

### Definição
Um roadmap é uma **comunicação estratégica** que alinha a organização em torno de objetivos de produto.

### O que NÃO é
❌ Uma lista de features com datas
❌ Um compromisso fixo
❌ Um Gantt chart
❌ Um backlog glorificado
❌ Uma promessa a customers

### O que É
✅ Visão estratégica
✅ Prioridades claras
✅ Contexto e "porquê"
✅ Flexível e adaptável
✅ Ferramenta de comunicação

---

## 🎨 Types of Roadmaps

### Por Audiência

#### 1. Internal Roadmap (Team)
**Audiência**: Engineering, Design, Product team

**Inclui:**
- Technical details
- Dependencies
- Resource allocation
- Risks

**Update frequency**: Weekly/Bi-weekly

#### 2. Executive Roadmap
**Audiência**: CEO, Board, Executives

**Inclui:**
- Strategic themes
- Business outcomes
- KPIs
- Resource needs

**Update frequency**: Monthly/Quarterly

#### 3. Customer/Sales Roadmap
**Audiência**: Customers, Prospects, Sales team

**Inclui:**
- High-level capabilities
- Benefits
- Timelines (vague: Q1, H1)
- NO commitments firmes

**Update frequency**: Quarterly

### Por Horizonte de Tempo

```
NOW (0-3 months)
├─ Committed
├─ Clear requirements
└─ In execution

NEXT (3-6 months)
├─ Validated ideas
├─ Some definition
└─ Planning phase

LATER (6-12+ months)
├─ Exploration
├─ Vision
└─ Subject to change
```

---

## 📊 Now-Next-Later Roadmap

### O que é?
Formato simples e flexível. Foco em sequência, não datas.

### Estrutura

```
┌─────────────────────────────────────────────┐
│ NOW (This Quarter)                          │
├─────────────────────────────────────────────┤
│ • Initiative 1                              │
│   → Key result: [metric]                    │
│   → Why: [strategic reason]                 │
│                                             │
│ • Initiative 2                              │
│   → Key result: [metric]                    │
│   → Why: [strategic reason]                 │
├─────────────────────────────────────────────┤
│ NEXT (Next Quarter)                         │
├─────────────────────────────────────────────┤
│ • Initiative 3                              │
│   → Key result: [metric]                    │
│   → Why: [strategic reason]                 │
│                                             │
│ • Initiative 4                              │
│   → Key result: [metric]                    │
│   → Why: [strategic reason]                 │
├─────────────────────────────────────────────┤
│ LATER (Future)                              │
├─────────────────────────────────────────────┤
│ • Exploration area 1                        │
│ • Exploration area 2                        │
│ • Ideas under validation                    │
└─────────────────────────────────────────────┘
```

### Quando Usar
- ✅ Fast-moving environments
- ✅ High uncertainty
- ✅ Startup/scale-up
- ✅ Continuous discovery

### Template

```markdown
# Product Roadmap: [Product Name]
**Last Updated**: 2026-03-XX
**Owner**: [Product Manager]

## North Star Metric
[Primary metric we're optimizing for]

## Strategic Themes
1. [Theme 1]: [Description]
2. [Theme 2]: [Description]
3. [Theme 3]: [Description]

---

## NOW (Q1 2026)

### Initiative: [Name]
**Theme**: [Which strategic theme]
**Problem**: [User problem being solved]
**Solution Hypothesis**: [What we believe will work]
**Success Metrics**: 
- Primary: [KPI] from [X] to [Y]
- Secondary: [KPI] from [X] to [Y]
**Confidence**: [High/Med/Low]
**Team**: [Who's working on this]

### Initiative: [Name]
[Same structure]

---

## NEXT (Q2 2026)

### Initiative: [Name]
[Same structure but less detailed]

---

## LATER (H2 2026 & Beyond)

### Ideas Being Explored
- [Idea 1]: [Brief description]
- [Idea 2]: [Brief description]

### Research Themes
- [Research area 1]
- [Research area 2]

---

## What Changed Since Last Update
- [Change 1 and why]
- [Change 2 and why]
```

---

## 🎯 Theme-Based Roadmap

### O que é?
Organizado por temas estratégicos em vez de features.

### Exemplo de Themes

```
THEME 1: User Activation
Goal: Increase % of signups who reach "aha moment"
Current: 35% → Target: 50%

Initiatives:
├─ Onboarding redesign
├─ In-app tutorials
└─ Email nurture campaign

────────────────────────────

THEME 2: Enterprise Readiness
Goal: Win 3 enterprise deals (>100 seats)

Initiatives:
├─ SSO integration
├─ Advanced permissions
├─ Audit logs
└─ SLA guarantees

────────────────────────────

THEME 3: Product Expansion
Goal: Increase revenue per customer

Initiatives:
├─ New module X
├─ Advanced analytics
└─ API platform
```

### Benefits
- ✅ Strategic clarity
- ✅ Focuses on outcomes, not outputs
- ✅ Easier to communicate "why"
- ✅ Flexible na execução

### Structure

```
┌─────────────────────────────────────────┐
│ THEME: [Name]                           │
├─────────────────────────────────────────┤
│ WHY: [Strategic importance]             │
│                                         │
│ GOAL: [Measurable outcome]              │
│                                         │
│ TARGET: [Specific metric target]        │
│                                         │
│ TIMELINE: [Now/Next/Later]              │
├─────────────────────────────────────────┤
│ KEY INITIATIVES:                        │
│ • [Initiative 1]                        │
│ • [Initiative 2]                        │
│ • [Initiative 3]                        │
├─────────────────────────────────────────┤
│ SUCCESS CRITERIA:                       │
│ • [Criteria 1]                          │
│ • [Criteria 2]                          │
└─────────────────────────────────────────┘
```

---

## 🎪 Outcome-Based Roadmap

### O que é?
Foca em objetivos de negócio, não em features específicas.

### Estrutura

```
BUSINESS OBJECTIVE
    ↓
PRODUCT OUTCOME
    ↓
SOLUTIONS (multiple options)
```

### Exemplo

```
BUSINESS OBJECTIVE:
Increase Monthly Recurring Revenue by 20%

    ↓

PRODUCT OUTCOMES:
1. Reduce churn from 5% to 3%
2. Increase expansion revenue
3. Improve new customer acquisition

    ↓

FOR OUTCOME 1 (Reduce Churn):

Hypothesis: Users churn because they don't reach activation

Possible Solutions:
a) Improve onboarding experience
b) Add in-product guidance
c) Proactive customer success outreach
d) Better product education

Next Steps:
• Validate hypothesis with user research
• Test solution (a) first - highest impact/lowest effort
• Measure: % users reaching activation milestone
```

### Template

```markdown
## Business Objective: [Name]

**Why This Matters**: [Strategic importance]
**Target**: [Specific, measurable goal]
**Timeline**: [When we want to achieve this]

---

### Product Outcome 1: [Name]

**Current State**: [Baseline metric]
**Target State**: [Goal metric]
**Why We Believe This Helps**: [Logic]

#### Solution Options

**Option A: [Name]**
- Description: [What we'd build]
- Effort: [Low/Med/High]
- Confidence: [%]
- Expected Impact: [Estimate]
- Risks: [What could go wrong]

**Option B: [Name]**
[Same structure]

**Recommended Approach**: [Which and why]

#### Success Metrics
- Primary: [KPI]
- Secondary: [KPI]
- Leading indicators: [Early signs of success]

---

### Product Outcome 2: [Name]
[Same structure]
```

### Benefits
- ✅ Focuses on "what" and "why", not "how"
- ✅ Leaves solution space open
- ✅ Team autonomy
- ✅ Easier to pivot

---

## 📅 Timeline-Based Roadmap

### Quando Usar
- Compliance/regulatory requirements
- Fixed launch dates (events, partnerships)
- Commitments to large customers
- Hardware dependencies

### ⚠️ Warnings
- Dates slip (always plan buffer)
- Creates false certainty
- Reduces flexibility
- Can demoralize team if constantly adjusted

### Gantt Chart Alternative

```
Instead of:
┌─────────────────────────────────────┐
│ Feature A │████████│               │
│ Feature B │        │██████│        │
│ Feature C │            │████████│  │
└─────────────────────────────────────┘
   Jan    Feb    Mar    Apr    May

Use ranges:
Q1 2026: Feature A
Q2 2026: Feature B, Feature C
H2 2026: Feature D exploration
```

---

## 🗣️ Roadmap Communication

### Communication Framework

#### 1. Executive Summary (2 min read)
```
• What: [High-level themes]
• Why: [Strategic importance]
• When: [Rough timeline]
• Impact: [Expected business outcomes]
```

#### 2. Detailed Plan (15 min read)
```
• Problem statement
• Solution approach
• Success metrics
• Dependencies
• Risks
• Resource needs
```

#### 3. Working Document (Reference)
```
• User stories
• Technical specs
• Design mocks
• Sprint planning
```

### Different Formats

#### For Executives
```
Focus: Business impact
Format: Slides, 1-pager
Content:
- Strategic themes
- Revenue impact
- Resource asks
- Risk mitigation
```

#### For Engineering
```
Focus: Technical details
Format: Confluence, Notion, Jira
Content:
- Technical approach
- Dependencies
- Architecture decisions
- Effort estimation
```

#### For Customers
```
Focus: Benefits, value
Format: Blog post, email, in-app announcement
Content:
- What's coming
- How it helps them
- When (vague)
- How to get access (beta)

⚠️ NEVER commit to specific dates publicly
```

#### For Sales
```
Focus: Competitive positioning, deals
Format: Sales enablement doc, slide deck
Content:
- Capabilities timeline
- Competitive parity
- How to position
- FAQ for objections

Include:
✅ "In development"
✅ "Coming Q2"
❌ "March 15th"
❌ Detailed features
```

### Roadmap Presentation Template

```
SLIDE 1: Vision
───────────────
Where we're going and why

SLIDE 2: Strategy
─────────────────
How we'll get there (themes)

SLIDE 3: Current State
──────────────────────
Where we are today (metrics)

SLIDE 4: Priorities
───────────────────
What we're doing now

SLIDE 5: What's Next
────────────────────
What's coming (vague timeline)

SLIDE 6: Measuring Success
──────────────────────────
How we'll know it's working

SLIDE 7: Q&A
────────────
Open discussion
```

---

## 🚨 Common Pitfalls

### 1. Feature List Disguised as Roadmap

❌ **Bad**:
```
Q1: Add dark mode, new dashboard, API v2
Q2: Mobile app, integrations, reports
Q3: AI features, performance improvements
```

✅ **Good**:
```
Q1: Improve activation (onboarding redesign, in-app guidance)
    Goal: 35% → 50% activation rate
    
Q2: Enable enterprise sales (SSO, permissions, audit)
    Goal: Close 3 enterprise deals
```

### 2. Too Much Detail Too Far Out

❌ **Bad**:
```
Q4 2026: 
- Feature A (2 weeks, João)
- Feature B (3 weeks, Maria)
- Feature C (1 week, Pedro)
```

✅ **Good**:
```
H2 2026:
- Explore international expansion
- Research ML/AI opportunities
```

### 3. No "Why"

❌ **Bad**:
```
Next: Build mobile app
```

✅ **Good**:
```
Next: Mobile app
Why: 40% of users try to access on mobile, bounce rate 80%
Goal: Enable mobile-first workflows, reduce bounce to 30%
```

### 4. Never Updated

⚠️ **A stale roadmap is worse than no roadmap**

Update frequency:
- NOW section: Weekly
- NEXT section: Bi-weekly
- LATER section: Monthly

### 5. Too Many Priorities

❌ If everything is priority, nothing is

```
Guideline:
NOW: 2-3 initiatives máximo
NEXT: 3-5 initiatives
LATER: Themes, não lista exaustiva
```

### 6. Treating it as Contract

Roadmaps change. That's healthy.

**Always include disclaimer:**
```
"This roadmap represents our current thinking and priorities.
It will evolve based on learning, customer feedback, and market changes.
Nothing here should be considered a commitment or guarantee."
```

---

## 🔄 Roadmap Update Process

### Monthly Review

```
┌─ INPUTS ─────────────────────┐
│ • Customer feedback          │
│ • Usage data                 │
│ • Competitive intel          │
│ • Team capacity              │
│ • Strategic shifts           │
└──────────────────────────────┘
        ↓
┌─ REVIEW ─────────────────────┐
│ • What shipped?              │
│ • What learned?              │
│ • What changed?              │
│ • Still the right priorities?│
└──────────────────────────────┘
        ↓
┌─ UPDATE ─────────────────────┐
│ • Adjust NOW                 │
│ • Refine NEXT                │
│ • Explore LATER              │
└──────────────────────────────┘
        ↓
┌─ COMMUNICATE ────────────────┐
│ • Share update               │
│ • Explain changes            │
│ • Align stakeholders         │
└──────────────────────────────┘
```

### Changelog Template

```markdown
# Roadmap Update: March 2026

## What Changed

### Promoted (NOW)
- **[Feature X]**: Moved from NEXT to NOW
  - Reason: Customer demand exceeded expectations
  - Impact: Delays [Feature Y] by 2 weeks

### Deprioritized (LATER)
- **[Feature Z]**: Moved from NEXT to LATER
  - Reason: Low usage of similar existing feature
  - Learning: Users want simpler solution first

### New Addition
- **[Feature W]**: Added to NEXT
  - Reason: Competitive threat, table stakes
  - Trade-off: Using buffer capacity

## Shipped Last Month
- ✅ [Feature A]: Live, metrics tracking
- ✅ [Feature B]: 95% complete, launching next week

## Coming Next Month
- [Feature C]: Design complete, dev starts
- [Feature D]: User testing in progress
```

---

## 📊 Roadmap Metrics

### Health Indicators

```
Delivery Predictability:
Features shipped on time / Features planned
Target: >70%

Roadmap Stability:
% of changes month-to-month
Target: <20%

Strategic Alignment:
% of work tied to strategic themes
Target: >80%

Stakeholder Satisfaction:
Survey: "Roadmap helps me do my job"
Target: >4/5
```

---

## ✅ Roadmap Checklist

**Content Quality**:
- [ ] Clear strategic themes
- [ ] Outcome-focused
- [ ] Measurable success criteria
- [ ] "Why" explained for each initiative
- [ ] Right level of detail for horizon
- [ ] Dependencies identified
- [ ] Risks called out

**Communication**:
- [ ] Tailored for each audience
- [ ] Disclaimer included
- [ ] Last updated date visible
- [ ] Owner assigned
- [ ] Feedback mechanism

**Process**:
- [ ] Updated regularly
- [ ] Reviewed by stakeholders
- [ ] Changes communicated
- [ ] Learning incorporated
- [ ] Aligned with OKRs/strategy

---

## 📁 Roadmap Tools

### Simple (Start Here)
- **Google Slides/Powerpoint**: Free, flexible
- **Notion**: Great for living docs
- **Miro/Mural**: Collaborative, visual
- **Markdown + Git**: Version-controlled

### Specialized
- **Productboard**: Feature-rich, pricey
- **Aha!**: Enterprise-focused
- **Roadmunk**: Visual roadmaps
- **Productplan**: Simple, effective

### Integrated
- **Jira**: If already using for dev
- **Linear**: Modern, fast
- **Asana**: Good for non-tech teams

**Recommendation**: Start simple. Tool doesn't matter as much as process.

---

**Próximos passos**: Com roadmap definido, estabelecer [Metrics & Analytics](../06-metrics-analytics/) para medir sucesso.
