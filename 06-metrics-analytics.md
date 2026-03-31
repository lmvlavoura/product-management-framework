# 6. Metrics & Analytics

## 📋 Índice
1. [Product Metrics Philosophy](#product-metrics-philosophy)
2. [North Star Metric](#north-star-metric)
3. [AARRR Framework (Pirate Metrics)](#aarrr-framework)
4. [Product KPIs by Stage](#product-kpis-by-stage)
5. [Cohort Analysis](#cohort-analysis)
6. [Funnel Analysis](#funnel-analysis)
7. [A/B Testing](#ab-testing)
8. [Analytics Best Practices](#analytics-best-practices)

---

## 🎯 Product Metrics Philosophy

### Os Princípios

**1. One Metric That Matters (OMTM)**
Focus em 1 métrica principal em cada momento.

**2. Leading vs Lagging Indicators**
- Leading: Predizem o futuro (signups, activation)
- Lagging: Confirmam o passado (revenue, churn)

**3. Vanity vs Actionable Metrics**
- Vanity: Make you feel good (total users, page views)
- Actionable: Drive decisions (retention rate, LTV/CAC)

**4. Avoid Metric Soup**
Demasiadas métricas = nenhuma importa

### Métricas por Tipo

#### Business Metrics
```
- MRR (Monthly Recurring Revenue)
- ARR (Annual Recurring Revenue)
- LTV (Lifetime Value)
- CAC (Customer Acquisition Cost)
- Churn Rate
- Net Revenue Retention
```

#### Product Metrics
```
- Daily/Monthly Active Users (DAU/MAU)
- Activation Rate
- Feature Adoption
- Time to Value
- Session Duration
- Stickiness (DAU/MAU)
```

#### Growth Metrics
```
- Viral Coefficient
- Conversion Rates
- Referral Rate
- Organic vs Paid Growth
- Payback Period
```

---

## ⭐ North Star Metric

### O que é?
**A ÚNICA métrica que melhor captura o core value do produto para utilizadores.**

### Características de um bom NSM

✅ **Expressa valor entregue**
Não é uma métrica de input, é de outcome

✅ **Liderante de revenue**
Quando sobe, revenue sobe

✅ **Reflete customer satisfaction**
Happy customers → Métrica sobe

✅ **Simples de entender**
Toda a empresa entende

✅ **Mensurável e influenciável**
Pode ser tracked e melhorado

### Exemplos de North Star Metrics

| Company | North Star Metric | Why |
|---------|------------------|-----|
| **Airbnb** | Nights booked | Value para host + guest |
| **Spotify** | Time spent listening | Engagement = value |
| **Slack** | Messages sent | Core value = communication |
| **Facebook** | Daily Active Users | Network effects |
| **Netflix** | Hours watched | Content value |
| **Uber** | Rides completed | Marketplace health |
| **Dropbox** | Files saved & shared | Core value prop |

### Para Analytics Platform

```
Possible NSM:

Option 1: Insights discovered per week
→ Measures value delivered

Option 2: Dashboard views per user per week
→ Measures engagement

Option 3: Data-driven decisions made
→ Hardest to measure but most meaningful

Recommendation: Insights discovered per week
- Tangible
- Measurable
- Leading indicator of value
```

### NSM Framework

```
┌────────────────────────────────────┐
│ NORTH STAR METRIC                  │
│ [Your primary metric]              │
├────────────────────────────────────┤
│ WHY THIS METRIC?                   │
│ • [Reason 1]                       │
│ • [Reason 2]                       │
│ • [Reason 3]                       │
├────────────────────────────────────┤
│ INPUT METRICS                      │
│ (What drives the NSM?)             │
│                                    │
│ 1. [Driver 1]                      │
│ 2. [Driver 2]                      │
│ 3. [Driver 3]                      │
├────────────────────────────────────┤
│ TARGET                             │
│ Current: [X]                       │
│ Target (3 months): [Y]             │
│ Target (12 months): [Z]            │
├────────────────────────────────────┤
│ TRACKING                           │
│ Dashboard: [Link]                  │
│ Review cadence: [Weekly/Monthly]   │
│ Owner: [Name]                      │
└────────────────────────────────────┘
```

---

## 🏴‍☠️ AARRR Framework (Pirate Metrics)

### O que é?
Framework de 5 estágios do customer journey, criado por Dave McClure.

```
ACQUISITION → ACTIVATION → RETENTION → REVENUE → REFERRAL
```

### 1. ACQUISITION
**"How do users find us?"**

**Key Metrics:**
- Traffic sources (Organic, Paid, Referral, Direct)
- Cost per Acquisition (CPA)
- Signup rate
- Landing page conversion

**Questions:**
- Which channels work best?
- What's our CAC by channel?
- Quality of traffic from each source?

**Example Goals:**
```
- 10,000 website visitors/month
- 5% signup rate
- <€50 CAC
- 30% from organic
```

### 2. ACTIVATION
**"Do users have a great first experience?"**

**Key Metrics:**
- Activation rate (% who reach "aha moment")
- Time to first value
- Onboarding completion rate
- Feature adoption in first session

**"Aha Moment" Examples:**
- Facebook: 7 friends in 10 days
- Slack: 2000 messages sent by team
- Dropbox: 1 file in 1 folder
- Twitter: Follow 30 accounts

**Questions:**
- What's the activation milestone?
- How many users reach it?
- Where do they drop off?
- How long does it take?

**Example Goals:**
```
- 50% activation rate
- 90% of activated users create 1st dashboard
- <5 minutes to first insight
```

### 3. RETENTION
**"Do users come back?"**

**Key Metrics:**
- Day 1, 7, 30 retention
- Monthly Active Users (MAU)
- Stickiness (DAU/MAU ratio)
- Churn rate
- Resurrection rate

**Retention Curves:**
```
Good retention:
100% │╲___
     │    ╲____
     │         ╲_____ (flattens)
     └──────────────────
      D1  D7  D30  D90

Bad retention:
100% │╲
     │ ╲
     │  ╲
     │   ╲_____ (keeps dropping)
     └──────────────────
```

**Questions:**
- What drives users to return?
- When do they churn?
- Can we re-engage churned users?

**Example Goals:**
```
- Day 7 retention: 40%
- Day 30 retention: 25%
- Monthly churn: <5%
- DAU/MAU: >20% (2-3x/week usage)
```

### 4. REVENUE
**"How do we monetize?"**

**Key Metrics:**
- MRR/ARR
- ARPU (Average Revenue Per User)
- LTV (Lifetime Value)
- LTV/CAC ratio
- Conversion to paid %
- Expansion MRR

**Questions:**
- When do users convert to paid?
- What's our pricing strategy?
- Can we increase ARPU?
- Expand or acquire?

**Example Goals:**
```
- €100K MRR
- 5% free-to-paid conversion
- €1000 LTV
- €200 CAC → LTV/CAC = 5:1
- 120% Net Revenue Retention
```

### 5. REFERRAL
**"Do users tell others?"**

**Key Metrics:**
- Viral coefficient (k-factor)
- Referral rate
- Net Promoter Score (NPS)
- Organic signups %

**Viral Coefficient:**
```
k = (% of users who refer) × (avg invites sent) × (conversion rate)

k > 1 = Viral growth (1 user → >1 new user)
k < 1 = Need other growth channels
```

**Questions:**
- Why would users share?
- Is sharing built into product?
- Quality of referred users?

**Example Goals:**
```
- NPS > 40
- 20% referral rate
- k = 0.5 (not viral but helpful)
- 30% of signups from referral
```

### AARRR Dashboard Template

```
┌──────────────────────────────────────────────┐
│ ACQUISITION                                  │
├──────────────────────────────────────────────┤
│ Weekly Signups: ▲ 532 (+12%)                │
│ Top Channel: Organic (45%)                   │
│ CAC: €42                                     │
├──────────────────────────────────────────────┤
│ ACTIVATION                                   │
├──────────────────────────────────────────────┤
│ Activation Rate: ▼ 48% (-2%)                │
│ Avg Time to Value: 8 min                    │
│ Drop-off Point: Dashboard creation           │
├──────────────────────────────────────────────┤
│ RETENTION                                    │
├──────────────────────────────────────────────┤
│ D7 Retention: 42%                            │
│ D30 Retention: ▲ 28% (+3%)                  │
│ Monthly Churn: 4.2%                          │
├──────────────────────────────────────────────┤
│ REVENUE                                      │
├──────────────────────────────────────────────┤
│ MRR: €87K ▲ (+15%)                          │
│ Free→Paid: 6.2%                              │
│ LTV/CAC: 6.2:1                               │
├──────────────────────────────────────────────┤
│ REFERRAL                                     │
├──────────────────────────────────────────────┤
│ NPS: 52                                      │
│ Referral Signups: 18%                        │
│ k-factor: 0.4                                │
└──────────────────────────────────────────────┘
```

---

## 📊 Product KPIs by Stage

### Early Stage (Pre-PMF)
**Focus: Learning & Validation**

```
Primary:
- Problem/Solution fit signals
- Activation rate
- Qualitative feedback

Secondary:
- Signup rate
- User interviews completed
- Feature usage

Avoid obsessing over:
- Total users (vanity)
- Revenue (too early)
```

### Growth Stage (Post-PMF)
**Focus: Scaling what works**

```
Primary:
- Activation rate
- Retention (D7, D30)
- CAC payback period

Secondary:
- Viral coefficient
- Feature adoption
- Customer satisfaction

Watch closely:
- Quality of growth
- Unit economics
```

### Scale Stage
**Focus: Efficiency & Profitability**

```
Primary:
- LTV/CAC ratio
- Net Revenue Retention
- Customer satisfaction (NPS)

Secondary:
- Gross margin
- Magic number (sales efficiency)
- Market share

Optimize:
- Operations
- Cost structure
- Team productivity
```

---

## 👥 Cohort Analysis

### O que é?
Agrupar users por quando começaram e comparar comportamento over time.

### Why It Matters
- Retention melhorou com product changes?
- Quality of users mudou?
- Seasonality effects?

### Cohort Types

#### 1. Time-Based Cohorts
```
Signup Month:
- January 2026 cohort
- February 2026 cohort
- March 2026 cohort
```

#### 2. Behavior-Based Cohorts
```
By Activation:
- Activated in Week 1
- Activated in Week 2-4
- Never activated

By Feature Usage:
- Used Feature X
- Didn't use Feature X
```

#### 3. Acquisition-Based Cohorts
```
By Channel:
- Organic cohort
- Paid ads cohort
- Referral cohort
```

### Retention Cohort Table

```
Cohort    | D0   | D1  | D7  | D14 | D30 | D60 | D90
----------|------|-----|-----|-----|-----|-----|-----
Jan 2026  | 100% | 65% | 45% | 38% | 30% | 28% | 25%
Feb 2026  | 100% | 68% | 50% | 42% | 35% | 32% | ?
Mar 2026  | 100% | 70% | 52% | ?   | ?   | ?   | ?

💡 Feb/Mar cohorts retaining better → Product improvements working
```

### Analysis Template

```markdown
# Cohort Analysis: [Metric Name]

**Date Range**: Jan-Mar 2026
**Cohort Type**: Time-based (monthly signups)
**Metric**: D30 Retention Rate

## Findings

### Trend
- Retention improving: Jan 25% → Mar 35%
- Improvement: +40% relative

### Likely Causes
1. Onboarding redesign (launched Feb 1)
2. Email nurture campaign (launched Feb 15)
3. In-app guidance (launched Mar 1)

### Cohort Differences
- Organic users: 40% D30 retention
- Paid users: 28% D30 retention
- Referral users: 55% D30 retention

## Recommendations
1. Double down on referral program
2. Improve paid acquisition targeting
3. Continue onboarding improvements

## Next Steps
- [ ] Track April cohort
- [ ] Deep dive on organic vs paid
- [ ] A/B test onboarding variations
```

---

## 🎯 Funnel Analysis

### O que é?
Tracking de users através de sequential steps para identificar drop-off.

### Example Funnel: Onboarding

```
100 Signups
    ↓ (80%)
 80 Email verified
    ↓ (60%)
 48 Created workspace
    ↓ (70%)
 34 Invited team member
    ↓ (85%)
 29 First dashboard created  ← ACTIVATION
    
Overall conversion: 29%
Biggest drop: Email → Workspace (60%)
```

### Funnel Optimization Framework

**Step 1: Identify**
Where are biggest drops?

**Step 2: Investigate**
Why are they dropping?
- User research
- Session recordings
- Surveys

**Step 3: Hypothesize**
What might help?

**Step 4: Experiment**
A/B test solutions

**Step 5: Measure**
Did it improve?

### Funnel Analysis Template

```markdown
## Funnel: [Name]

**Goal**: [End state]
**Time Period**: [Date range]
**Sample Size**: [N] users

### Steps & Conversion

| Step | Users | Conversion | Drop-off |
|------|-------|------------|----------|
| 1. [Step name] | 1000 | 100% | - |
| 2. [Step name] | 800 | 80% | 20% |
| 3. [Step name] | 640 | 64% | 16% |
| 4. [Step name] | 512 | 51.2% | 12.8% |

**Overall Conversion**: 51.2%

### Drop-off Analysis

**Biggest Drop**: Step 1 → Step 2 (20%)

**Hypotheses Why**:
1. [Hypothesis 1]
2. [Hypothesis 2]
3. [Hypothesis 3]

**Experiments to Run**:
- [ ] [Experiment 1]
- [ ] [Experiment 2]

### Segment Analysis

| Segment | Overall Conversion | vs Average |
|---------|-------------------|-----------|
| Mobile | 35% | -16% |
| Desktop | 58% | +7% |
| Organic | 60% | +9% |
| Paid | 45% | -6% |

**Insight**: Mobile experience needs work
```

---

## 🧪 A/B Testing

### O que é?
Experimental method para comparar duas versões e determinar qual performa melhor.

### When to A/B Test

✅ **Good for:**
- Optimization (improve existing)
- High-traffic areas
- Incremental changes
- Validating hypotheses

❌ **Not good for:**
- Discovery (use research)
- Low traffic (not statistical power)
- Revolutionary changes
- Long-term effects

### A/B Test Framework

#### 1. Hypothesis

```
Template:
"We believe that [change]
will result in [impact]
because [reasoning]"

Example:
"We believe that adding social proof on signup page
will increase signup rate by 15%
because users trust recommendations from peers"
```

#### 2. Variables

**Independent Variable**: What you're changing
**Dependent Variable**: What you're measuring

```
IV: Signup button color (blue vs green)
DV: Signup rate
```

#### 3. Sample Size

```
Use calculator: https://www.evanmiller.org/ab-testing/

Inputs:
- Baseline conversion rate: 5%
- Minimum detectable effect: 10% (relative)
- Statistical power: 80%
- Significance level: 95%

Output: Need ~15,000 visitors per variant
```

#### 4. Duration

```
Duration = (Sample size needed) / (Daily traffic) × 2 variants

Example:
30,000 needed / 1,000 daily traffic = 30 days

⚠️ Run minimum 1 full business cycle (1 week)
```

#### 5. Success Metrics

**Primary Metric**: Main thing you're optimizing
**Secondary Metrics**: Things to monitor
**Guardrail Metrics**: Things that shouldn't get worse

```
Primary: Signup rate
Secondary: Time to signup, form completion
Guardrails: Bounce rate, quality of signups
```

### A/B Test Template

```markdown
# A/B Test: [Name]

**Status**: [Planning/Running/Complete]
**Start Date**: 2026-03-XX
**End Date**: 2026-XX-XX
**Owner**: [Name]

## Hypothesis

We believe that [change]
will result in [impact]
for [users]
because [reasoning]

## Design

**Control (A)**: [Current version]
**Variant (B)**: [New version]
**Traffic Split**: 50/50

## Metrics

**Primary**: [Metric name]
- Baseline: [X%]
- Target: [Y%]
- MDE: [Z%]

**Secondary**:
- [Metric 1]
- [Metric 2]

**Guardrails**:
- [Metric 1] should not decrease >5%
- [Metric 2] should stay stable

## Sample Size

**Required**: 30,000 per variant
**Expected Duration**: 30 days
**Significance**: 95%
**Power**: 80%

## Results

**Status**: [Winner: A/B/No difference]

| Metric | Control (A) | Variant (B) | Change | Significant? |
|--------|-------------|-------------|--------|--------------|
| Primary | 5.2% | 6.1% | +17% | ✅ Yes (p=0.02) |
| Secondary 1 | 2.3min | 2.1min | -9% | ❌ No (p=0.15) |
| Guardrail | 45% | 44% | -2% | ❌ No (p=0.35) |

## Decision

**Ship Variant B**

Reasoning:
- Significant increase in primary metric
- No negative impact on guardrails
- Easy to implement

## Learnings

1. [Learning 1]
2. [Learning 2]

## Next Tests

- [ ] [Follow-up test 1]
- [ ] [Follow-up test 2]
```

### Common Pitfalls

❌ **Peeking**: Looking at results before test completes
❌ **Testing too many things**: Can't attribute results
❌ **Insufficient sample size**: False positives
❌ **Ignoring segments**: Overall win might hide segment losses
❌ **Stopping too early**: Need statistical significance
❌ **Testing the wrong thing**: Solve symptoms, not causes

---

## 📈 Analytics Best Practices

### 1. Start with Questions

```
❌ "Let's add analytics and see what we find"
✅ "What do we need to know to make decisions?"

Good questions:
- Are users getting value?
- Where do they struggle?
- What drives retention?
- Which features matter?
```

### 2. Define Events Clearly

```
Event naming convention:
[Object]_[Action]

Examples:
- dashboard_created
- report_exported
- user_invited
- filter_applied

Include context:
{
  "event": "dashboard_created",
  "properties": {
    "dashboard_type": "sales",
    "num_widgets": 5,
    "template_used": true,
    "user_role": "manager"
  }
}
```

### 3. Track User Properties

```
User properties:
- user_id (unique)
- signup_date
- account_type (free/paid)
- company_size
- industry
- activation_status
- last_active_date
```

### 4. Data Quality Checks

```
Weekly checks:
- [ ] Events firing correctly
- [ ] No duplicate events
- [ ] Properties populated
- [ ] No anomalies in volume
- [ ] Cross-platform consistent
```

### 5. Documentation

```
Maintain events dictionary:

Event: dashboard_created
When: User creates new dashboard
Where: Dashboard creation modal
Properties:
- dashboard_type: string (sales, marketing, custom)
- template_used: boolean
- num_widgets: integer
```

### 6. Privacy & Compliance

```
✅ Do:
- Anonymous by default
- Allow opt-out
- Comply with GDPR/CCPA
- Secure data storage
- Document data usage

❌ Don't:
- Track PII without consent
- Share data with third parties without disclosure
- Keep data longer than needed
```

---

## 🎯 Metrics Dashboard Structure

### Executive Dashboard

```
┌────────────────────────────────────┐
│ KEY METRICS (Last 30 days)         │
├────────────────────────────────────┤
│ MRR: €87K ▲ (+15%)                │
│ Customers: 523 ▲ (+8%)            │
│ Churn: 4.2% ▼ (-0.5%)             │
│ NPS: 52 ▲ (+3)                    │
└────────────────────────────────────┘

Business health at a glance
Update: Daily
Audience: CEO, Board
```

### Product Dashboard

```
┌────────────────────────────────────┐
│ ENGAGEMENT (Last 7 days)           │
├────────────────────────────────────┤
│ DAU: 1,247 ▲ (+5%)                │
│ WAU: 3,891 ▲ (+12%)               │
│ Stickiness: 32% (DAU/MAU)         │
│ Avg Session: 12min                 │
├────────────────────────────────────┤
│ ACTIVATION                         │
├────────────────────────────────────┤
│ This Week: 48% ▼ (-2%)            │
│ Time to Value: 8min                │
└────────────────────────────────────┘

Product health
Update: Daily
Audience: Product, Eng, Design
```

### Growth Dashboard

```
┌────────────────────────────────────┐
│ ACQUISITION (This Week)            │
├────────────────────────────────────┤
│ Signups: 532 ▲ (+12%)             │
│ Organic: 45%                       │
│ Paid: 35%                          │
│ Referral: 20%                      │
├────────────────────────────────────┤
│ CONVERSION                         │
├────────────────────────────────────┤
│ Free→Paid: 6.2%                    │
│ CAC: €42                           │
│ LTV/CAC: 6.2:1                     │
└────────────────────────────────────┘

Growth performance
Update: Weekly
Audience: Marketing, Growth, Sales
```

---

## ✅ Analytics Checklist

**Setup**:
- [ ] Analytics tool chosen (Mixpanel, Amplitude, etc)
- [ ] North Star Metric defined
- [ ] Key events identified
- [ ] Tracking implemented
- [ ] Data validation done
- [ ] Documentation created

**Process**:
- [ ] Weekly metrics review scheduled
- [ ] Dashboard accessible to team
- [ ] Anomaly detection setup
- [ ] Data quality checks automated
- [ ] Experiment framework defined

**Culture**:
- [ ] Team trained on analytics
- [ ] Data-informed decisions normalized
- [ ] Metrics tied to OKRs
- [ ] Regular sharing of insights
- [ ] Celebrate learning, not just wins

---

**Próximos passos**: Com métricas definidas, criar [PRD Templates](../05-requirements/) para especificar features.
