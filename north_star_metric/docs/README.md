# North Star Metric (NSM) Prompt — README

**What this is**  
A reusable prompt that helps a company identify, test, and operationalize its **North Star Metric**—the single metric that best captures delivered customer value and predicts business success. The original prompt is preserved **verbatim** for traceability.

> Original file: `prompts/north-star-metric-ORIGINAL.md`

---

## When to use this
- You’re aligning the org around one metric for **focus** and **consistent decision-making**.  
- Your current KPIs are a mix of vanity and lagging indicators (e.g., revenue only).  
- You’re entering a new stage (early → growth, product/market fit to scaling) and need a **leading indicator** for success.  
- You want a pragmatic, data-informed way to pick and defend an NSM.

---

## How the prompt is organized

1. **`<metric_inputs>`** — A short intake to capture **business context** and **customer context**.  
2. **`<metric_process>`** — The 5-phase methodology (Map value → Identify candidates → Evaluate → Test → Recommend + operationalize).  
3. **`<output_format>`** — A standardized way to present the final recommendation.  
4. **`<meta_guidance>`** — Good vs bad NSM traits and anti-patterns.

**You only fill the bracketed `[]` placeholders throughout the process.** Do **not** edit the prompt’s wording.

---

## Quick start
1. Open `prompts/north-star-metric-ORIGINAL.md`.  
2. Fill out **every** `[]` where applicable using the examples below as a guide.  
3. Run the prompt to generate candidates, scoring, and a draft recommendation.  
4. Validate with data and user interviews, then finalize and socialize.

---

## Input cheat sheet — real PM examples for **every** `[]`

Below are **three distinct product contexts**. Use whichever is closest to your business. Each provides example entries for **all bracketed fields** across the process: value mapping, candidate list, evaluation notes, testing, recommendation, supporting metrics, dashboard, and operationalization.

---

### Scenario A — B2B Collaboration SaaS (project management tool)

**PHASE 1 — MAP THE VALUE CHAIN**  
- *What value do you deliver?* → `[Teams finish projects faster with fewer handoffs and better visibility]`  
- *When do customers experience that value?* → `[When a cross‑functional project completes on time with all tasks closed]`  
- *What actions lead to value?* → `[Creating projects, assigning tasks, completing tasks, posting status updates, resolving blockers]`  
- *How does customer value drive revenue?* → `[Accounts with more completed projects expand seats and retain longer; completions correlate with upsell]`

**PHASE 1 — CANDIDATE LIST**  
`[Projects completed per account per month, Active projects with weekly status updates, Tasks completed per active user per week, % projects with all stakeholders active, Time to first project completion, Feature adoption: dependencies used, WAU, Cross-team projects created, % projects completed on time, % tasks completed on time]`

**PHASE 2 — EVALUATION (notes embedded as you score High/Med/Low)**  
- *Does it capture VALUE DELIVERY?* → `[Projects completed per account per month rises when customers get value; hard to game without real work]`  
- *Does it PREDICT REVENUE?* → `[Accounts in top quartile of project completions have +18% retention and +12% seat expansion]`  
- *Is it a LEADING INDICATOR?* → `[Completions lead renewals by ~2–3 months]`  
- *Can the WHOLE COMPANY influence it?* → `[PM improves workflows, Sales onboards to first project, CS coaches on templates, Marketing educates]`  
- *Is it EASY TO UNDERSTAND?* → `[Yes—finished projects are intuitive]`  
- *Measurable?* → `[Yes—events + project status table; consistent across web/mobile]`  
**Top 3 finalists:** `[Projects completed per account per month, % projects completed on time, Tasks completed per active user per week]`

**PHASE 3 — TEST CANDIDATES**  
- Historical: `[High project‑completion cohorts retain +15 pts vs. low cohorts; r=0.62 with N=1,240 accounts]`  
- Interviews: `[Power users obsess over “closing”; churned admins cite stuck projects]`  
- So‑What Test: `If “projects completed per account per month” ↑20% → Customers get more value [yes]; Business healthier [yes]; Teams know what to build [yes: templates, automations, approvals]`

**PHASE 4 — RECOMMENDATION**  
- **Your North Star Metric:** `[Projects completed per account per month]`  
  - *Definition:* `[Count of projects moved to “completed” per paying account in a calendar month; excludes archived/abandoned]`  
  - *Why:*  
    - `Captures customer value because: [Work truly gets finished]`  
    - `Predicts business success because: [Completions correlate with retention/expansion]`  
    - `Whole company can influence because: [Templates, onboarding, education, support]`  
  - *Current baseline:* `[2.1]`  
  - *Targets:* `This month: [2.4] · This quarter: [3.0] · This year: [4.0]`  
  - *How to move it:* `[Launch project templates, auto-reminders for blockers, executive status digest]`  
  - *What NOT to do:* `[Avoid inflating with tiny “micro‑projects”; enforce min scope in definition]`

**PHASE 4 — SUPPORTING METRICS**  
- Inputs: `[Time to first project completion — faster onboarding drives habit]`, `[% projects with weekly status updates — cadence prevents stalls]`  
- Outputs: `[Gross revenue retention, NRR]`, `[NPS for admins]`

**PHASE 4 — DASHBOARD**  
- NSM: `[Projects completed / account / month]`  
- Trend: `[↑ +9% vs last month]`  
- Inputs: `[TTFP, % with weekly updates]`  
- Outputs: `[GRR, NRR, Admin NPS]`

**PHASE 5 — OPERATIONALIZING**  
- Roadmap: `“Will this feature increase [Projects completed / account / month]?”`  
- Experiments: `Primary: [Projects completed / account / month]` with success `[+10%]`  
- Team goals: `Company OKR: [Increase NSM from 2.1 → 3.0]`  
- Reviews: `Daily [anomaly checks], Weekly [deep dive drivers], Quarterly [re‑validate correlation]`

---

### Scenario B — Fintech Payments API (developer platform)

**PHASE 1 — MAP THE VALUE CHAIN**  
- Value: `[Merchants get higher payment success with fewer integration headaches]`  
- When value happens: `[When a live merchant processes successful payments in production]`  
- Actions: `[Create API keys, configure webhooks, process successful charges, handle webhooks, enable retries]`  
- Value → Revenue: `[More successful transactions → higher take‑rate revenue and merchant retention]`

**CANDIDATES**  
`[Successful transactions per active merchant, Merchant go‑live rate, % merchants with retries enabled, Time to first live charge, Authorization rate, Webhook delivery success rate, Docs task completion rate, WAU (dashboard), Error rate per 1k charges, % merchants with 3+ features enabled]`

**EVALUATION H/L**  
- Value delivery: `[Successful transactions per active merchant is directly value]`  
- Predicts revenue: `[Strong correlation with processing volume and churn reduction]`  
- Leading: `[Leads MRR by 1–2 months]`  
- Whole company: `[DevRel/docs, CS, Product, Sales all impact adoption]`  
- Understandable: `[Yes]`  
- Measurable: `[Yes—events + billing]`  
**Top 3:** `[Successful transactions per active merchant, Authorization rate, Merchant go‑live rate]`

**TEST**  
- Historical: `[Top quartile STP merchants → +22 pts NRR]`  
- Interviews: `[Power users optimize retries; churned cite integration friction]`  
- So‑What: `[If STP ↑20%, both value and revenue improve; clear build levers: retries, tokenization, alerts]`

**RECOMMENDATION**  
- NSM: `[Successful transactions per active merchant per month]`  
- Definition: `[Count of charges with status='succeeded' for merchants with ≥1 live charge in the period]`  
- Baseline/Targets: `[Baseline 4,800] · [Q target 5,500] · [Yr target 7,000]`  
- How to move: `[One‑click retries, BIN alerts, SDK quick‑starts]`  
- Not to do: `[Discourage $0 auth spam to fake success]`

**SUPPORTING**  
- Inputs: `[Time to first live charge]`, `[Retry adoption rate]`  
- Outputs: `[Processing volume, NRR]`, `[Dispute rate]`

**DASHBOARD**  
- NSM: `[STP / active merchant]` · Trend: `[↑]` · Inputs: `[TTFLC, Retry %]` · Outputs: `[Volume, NRR, Disputes]`

**OPERATIONALIZING**  
- Roadmap filter: `“Will this increase [STP / active merchant]?”`  
- Experiments: `Primary: [STP / active merchant], lift [+8%]`  
- Goals: `[Increase STP/merchant from 4,800 → 5,500]`

---

### Scenario C — Two‑sided Marketplace (local services)

**PHASE 1 — MAP THE VALUE CHAIN**  
- Value: `[Homeowners get vetted pros quickly; pros get steady jobs]`  
- When value happens: `[A completed, paid job with 4★+ rating]`  
- Actions: `[Request job, match, accept, complete, rate]`  
- Value → Revenue: `[Completed jobs → take rate; ratings drive repeat use]`

**CANDIDATES**  
`[Completed jobs per active city per week, % requests matched within 2 hours, Time to first completed job, Repeat jobs per customer per quarter, % 4★+ jobs, Active pros per city, Job acceptance rate, Cancellation rate, WAU]`

**EVALUATION & TOP 3**  
- Value delivery: `[Completed jobs per active city per week is direct value]`  
- Predicts revenue: `[More completed jobs → more take rate]`  
- Leading: `[Leads revenue by 1–3 weeks]`  
- Whole company: `[Supply growth, CX, Ops, Product]`  
**Top 3:** `[Completed jobs per active city per week, % requests matched <2h, Repeat jobs per customer/quarter]`

**TEST / SO‑WHAT**  
- Historical: `[Cities with top‑quartile completions grow revenue 1.6×]`  
- Interviews: `[Power users cite fast matching; churn cites cancellations]`  
- So‑What: `[If completions ↑20% → customers happier, pros busier, revenue ↑]`

**RECOMMENDATION**  
- NSM: `[Completed jobs per active city per week]`  
- Definition: `[Count of jobs with status='completed' and paid, grouped by city, among cities with ≥50 weekly requests]`  
- Baseline/Targets: `[Baseline 320] · `This quarter: [400]` · `This year: [600]`  
- Levers: `[Faster matching SLA, surge pricing to balance supply, auto‑rebook for cancellations]`  
- Anti‑gaming: `[Disallow test jobs; enforce payment-cleared flag]`

**SUPPORTING / DASHBOARD / OPS**  
- Inputs: `[Match‑under‑2h rate]`, `[Active pros per city]`  
- Outputs: `[Take rate revenue, Customer CSAT]`  
- Dashboard: `NSM [Completed jobs/city/week] · Trend [↑] · Inputs [Match<2h, Active pros] · Outputs [Revenue, CSAT]`  
- Ops: `OKR: [Increase NSM from 320 → 400]; Experiments: [Primary NSM or its inputs]`

---

## What the framework enforces (so your NSM actually works)
- **Value-first chain** from customer benefit → usage → revenue.  
- **Candidate diversity** (activation, engagement, value creation, retention, revenue).  
- **Objective scoring** with explicit tradeoffs (gaming risk, leading vs lagging, org influence).  
- **Validation loop** (historical, interviews, So‑What Test).  
- **Operationalization** (OKRs, experiments, dashboards, cadence).

---

## Practical tips
- Avoid picking **revenue** as the NSM; keep it as an output metric.  
- Define the metric precisely: **what’s in/out**, identity, and **aggregation window**.  
- Establish **anti‑gaming rules** early (e.g., minimum scope, exclude internal/test traffic).  
- Plan **ownership** of inputs and a **review cadence**.

---

## Repository layout

```
prompt-library-north_star_metric/
├─ prompts/
│  └─ north-star-metric-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-north_star_metric.zip  ← export artifact
```

---

## FAQ
**Can we have more than one NSM?**  
Keep **one** NSM for company focus; use **supporting metrics** per team/product.

**What if we’re very early?**  
Pick a **proxy for value delivery** (e.g., weekly active creators) and revisit quarterly until data matures.

**When should we change the NSM?**  
Only when your **business model changes** or the current NSM stops correlating with retention/revenue.

