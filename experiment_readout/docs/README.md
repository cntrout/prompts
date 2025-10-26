# Experiment Readout Prompt — README

**What this is**  
A reusable prompt that turns raw experiment results into a clear, decision-ready **readout**. It enforces a rigorous flow: **validate → analyze → guardrails → segments → surprises → impact → recommendation**. The original prompt is preserved **verbatim** for traceability.

> Original file: `prompts/experiment-readout-ORIGINAL.md`

---

## When to use this
- After any A/B (or A/B/n) test where you need an **executive-ready** decision.  
- When you want to avoid common pitfalls (stopping early, over-reading p-values, ignoring guardrails).  
- When stakeholders expect a concise **recommendation** with business impact and next steps.

---

## How the prompt is organized
1. **`<experiment_inputs>`** — The _only_ section you edit. You paste raw data and context and set the decision criteria.  
2. **`<readout_framework>`** — The step-by-step analysis method (don’t change this).  
3. **Example template** — A canonical **Experiment Readout** structure the model will produce.

Keep the framework text stable; iterate by improving **inputs** only. fileciteturn8file0

---

## Quick start
1) Open `prompts/experiment-readout-ORIGINAL.md`.  
2) Fill every `[]` inside **`<experiment_inputs>`** (see examples below).  
3) Run the prompt. You’ll get a fully structured readout with decision, stats, guardrails, segments, impact, and next steps.  
4) Attach charts/tables from your analytics tool and ship the decision doc.

---

## Input cheat sheet — realistic PM examples for **every `[]`** field

Below are **three distinct PM scenarios** with concrete entries for all input fields.

### Scenario A — Pricing Page Social Proof (Free→Paid Conversion)

**PASTE YOUR DATA:**  
`Control: 12.0% free→paid (n=24,850); Treatment: 12.8% (n=24,910); p=0.018; 95% CI [+0.1, +1.5] pp. Page LCP stable at 2.2s; CLS < 0.02.`

**THE TEST:**  
- What you tested: `[Added 3 logos + 1-line testimonial carousel above the fold on pricing page]`  
- Hypothesis: `[Social proof reduces anxiety and increases free→paid conversion]`  
- Primary metric: `[Free→paid conversion over 7-day attribution]`  
- Duration: `[2025-10-06 → 2025-10-20]`  
- Sample size: `[~25k users/variant]`

**YOUR DECISION CRITERIA:**  
`[Ship if lift ≥ +0.5 pp and guardrails (LCP < 2.5s, refund rate ≤ baseline) are stable; otherwise iterate.]`

---

### Scenario B — Mobile Checkout Express Pay (Checkout Completion)

**PASTE YOUR DATA:**  
`Eligibility-filtered traffic only. Control completion 4.1% (n=180k sessions); Treatment 4.7% (n=182k); p=0.061; CI [-0.02, +1.2] pp. Payment fees +0.06 pp.`

**THE TEST:**  
- What you tested: `[Added express pay button (Apple/Shop Pay) on cart and first checkout step for eligible devices]`  
- Hypothesis: `[Reducing form friction improves completed orders, especially on mobile]`  
- Primary metric: `[Checkout completion rate]`  
- Duration: `[2025-09-29 → 2025-10-20]`  
- Sample size: `[~180k sessions/variant]`

**YOUR DECISION CRITERIA:**  
`[Ship if lift ≥ +0.6 pp and guardrails (LCP, error rate, customer support contacts) are neutral; if not statistically significant, ship to winning segments only if segment CIs exclude 0.]`

---

### Scenario C — Onboarding Checklist (D7 Retention, B2B SaaS)

**PASTE YOUR DATA:**  
`New workspaces cohort. Control D7 retained_active_users 32.0% (n=1,160); Treatment 35.1% (n=1,148); p=0.041; CI [+0.1, +6.2] pp. Setup step 3 completion +11 pp.`

**THE TEST:**  
- What you tested: `[Replaced blank dashboard with 4-step “Getting Started” checklist + progress bar]`  
- Hypothesis: `[Explicit activation path increases D7 retention via higher setup completion]`  
- Primary metric: `[D7 retained_active_users among new workspaces]`  
- Duration: `[2025-10-01 → 2025-10-22]`  
- Sample size: `[~1.1k workspaces/variant]`

**YOUR DECISION CRITERIA:**  
`[Ship if D7 lift ≥ +2.0 pp, guardrails (NPS, error rate, time-to-first-value) stable, and qualitative feedback neutral/positive.]`

---

## What the framework enforces (and why it works)

- **Validity first**: duration, sample size, split, bugs, and external events.  
- **Primary metric focus**: statistical _and_ practical significance (MDE-aware).  
- **Guardrails**: ensure performance and UX didn’t degrade.  
- **Segmentation**: detect “works here, not there” patterns for smarter rollouts.  
- **Surprises & qual**: reconcile data with user feedback.  
- **Business impact math**: percent → dollars/users → ROI.  
- **Clear recommendation**: **Ship / Don’t Ship / Iterate / Re-test** with confidence level.

---

## Practical tips
- Pre-register decision criteria to avoid bias.  
- Prefer one primary metric; treat the rest as explanatory.  
- If overall is marginal but a segment’s CI excludes 0, consider **segment-only** rollout.  
- Convert percent lifts into annualized impact and weigh against cost/complexity.

---

## Repository layout

```
prompt-library-experiment_readout/
├─ prompts/
│  └─ experiment-readout-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-experiment_readout.zip  ← export artifact
```

---

## FAQ
**What if the test is invalid?**  
Don’t ship. Document why and re-run with fixes (allocation, duration, instrumentation).

**How do we pick segments?**  
Start with device, new/returning, country, and plan tier. Expand only if you have power.

**How do we estimate impact?**  
`[Metric lift %] × [baseline volume] × [value per conversion]` → annualized $ impact, then compare to build/maintenance cost.

