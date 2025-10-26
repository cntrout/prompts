# A/B Test Design Prompt — README

**What this is**  
A reusable prompt that walks you from **hypothesis → metrics → sample size → rollout → analysis → decision** so your experiments are reliable and ship-ready. The original prompt is preserved **verbatim** in this package for traceability.

> Original file (unchanged): `prompts/ab-test-design-ORIGINAL.md`

---

## When to use this
- Any time you want to validate a product change with **evidence**, not vibes—pricing pages, onboarding flows, checkout tweaks, ranking/relevance changes, etc.  
- When you need a **complete test plan** your design/eng/analytics partners can align on before launch.

---

## How the prompt is organized

1. **`<test_inputs>`** — _The only section you edit._ You provide context and constraints (what, why, product facts, limits).  
2. **`<test_framework>`** — The method the model follows (hypothesis, metrics, guardrails, sample size, design, rollout, decision rules, instrumentation).  
3. **`A/B TEST DESIGN DOC`** — A structured, copy‑pasteable spec the model produces for your test.

Keep the wording of the framework intact. Change only the bracketed fields in **`<test_inputs>`**.

fileciteturn7file0

---

## Quick start
1. Open `prompts/ab-test-design-ORIGINAL.md`.  
2. Fill in **every** `[]` field inside **`<test_inputs>`** using the examples below.  
3. Run the prompt to generate a ready-to-share test plan.  
4. Sense‑check the numbers with your analyst (power, MDE, runtime) and attach the PRD/design mocks.

---

## Input cheat‑sheet — realistic PM examples for **every `[]`** in `<test_inputs>`

Below are **three totally different PM scenarios**. Each shows concrete answers for _all_ fields so you can copy/edit quickly.

### Scenario A — Pricing page social proof (free → paid conversion)

**WHAT YOU WANT TO TEST:**  
`[Add three customer logos + a 1‑line testimonial carousel to the pricing page above the fold]`

**WHY YOU'RE TESTING IT:**  
- Hypothesis: `[Social proof reduces purchase anxiety and increases free→paid conversion]`  
- Expected impact: `[Free→paid conversion rate]`  
- Risk: `[If testimonials feel inauthentic or slow the page, conversion may drop; potential CLS/Layout shift issues]`

**YOUR PRODUCT CONTEXT:**  
- Daily/monthly active users: `[DAU ~42k; MAU ~610k]`  
- Current baseline metric: `[Free→paid conversion = 12.0% over 7‑day attribution]`  
- Existing conversion/engagement rate: `[Pricing page → checkout start = 28.5%]`  
- How users are assigned: `[User ID]`

**CONSTRAINTS:**  
- Timeline: `[Run for 14 days minimum to cover weekday/weekend mix]`  
- Traffic: `[50/50 split OK; start canary at 10% for 24h]`  
- Technical: `[Static assets only; no third‑party scripts; maintain LCP <2.5s]`

---

### Scenario B — Mobile checkout: express pay button (Shop Pay/Apple Pay)

**WHAT YOU WANT TO TEST:**  
`[Add an express pay button on cart and first step of checkout for eligible devices]`

**WHY YOU'RE TESTING IT:**  
- Hypothesis: `[Reducing form friction increases completed orders, especially on mobile]`  
- Expected impact: `[Checkout completion rate / Orders per visitor]`  
- Risk: `[Payment mix shift increases fees; edge cases on subscription items]`

**YOUR PRODUCT CONTEXT:**  
- Daily/monthly active users: `[Mobile DAU ~19k; Desktop DAU ~11k]`  
- Current baseline metric: `[Checkout completion = 5.2% site‑wide; mobile = 4.1%]`  
- Existing conversion/engagement rate: `[Cart→checkout start = 61%; checkout start→payment success = 43%]`  
- How users are assigned: `[Session]`

**CONSTRAINTS:**  
- Timeline: `[Minimum 21 days to hit MDE on mobile]`  
- Traffic: `[Target 60% of traffic in test due to eligibility filters; allocation 50/50 within eligible]`  
- Technical: `[SDK requires TLS 1.2+; cannot run on IE/legacy Android]`

---

### Scenario C — Onboarding nudge: checklist vs. blank dashboard (B2B SaaS)

**WHAT YOU WANT TO TEST:**  
`[Replace blank dashboard for new workspaces with a 4‑step “Getting Started” checklist + progress bar]`

**WHY YOU'RE TESTING IT:**  
- Hypothesis: `[Explicit activation path drives more users to an aha moment, increasing D7 retained_active_users]`  
- Expected impact: `[Day‑7 retained_active_users; Activation rate (% completing Setup 3/4 steps)]`  
- Risk: `[Too much nudge could annoy advanced users; potential support load from confused admins]`

**YOUR PRODUCT CONTEXT:**  
- Daily/monthly active users: `[New workspaces per week ~2,300; WAU ~38k]`  
- Current baseline metric: `[D7 retained_active_users = 32% for new workspaces]`  
- Existing conversion/engagement rate: `[Setup wizard completion = 41% within 72h]`  
- How users are assigned: `[User ID]`

**CONSTRAINTS:**  
- Timeline: `[28–35 days to capture D7 retention signal with cohorting]`  
- Traffic: `[50/50 split; exclude legacy plan users]`  
- Technical: `[Event tracking must include step completions; feature flag per workspace]`

---

## What the framework enforces (and why it works)

- **Crisp hypothesis:** “If we change X, then metric Y will move by Z% because ….”  
- **Right primary metric & guardrails:** Measures real outcomes while protecting performance, errors, and critical flows.  
- **Power & MDE:** Sample size math and runtime estimate so you don’t stop early or over‑read noise.  
- **Clean variant design:** One meaningful change, everything else constant.  
- **Rollout plan + decision rules:** Canary → ramp; clear ship/don’t ship criteria; no cherry‑picking.  
- **Instrumentation:** Events and validation checks to trust the data.

---

## Tips from the trenches
- Aim for **one** primary metric. Use secondary metrics to explain _why_ something moved.  
- Pick an **MDE you actually care about** (business‑relevant). Smaller MDEs drive long tests with marginal value.  
- Guardrails matter: performance regressions can silently erase conversion gains.  
- Pre‑register your decisions (ship/no‑ship rules) to avoid bias once you see data.

---

## Repository layout

```
prompt-library-ab_test_design/
├─ prompts/
│  └─ ab-test-design-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-ab_test_design.zip  ← packaged artifact
```

---

## FAQ
**Can I add more variants (A/B/n)?**  
Yes. Extend the allocation section (e.g., 33/33/33) but keep a single primary metric.

**What if daily traffic is low?**  
Increase allocation, accept a larger MDE, or run longer. Consider a higher‑sensitivity metric (e.g., “start checkout” vs. “payment success”) for early reads—just don’t optimize to a proxy forever.

**How do I avoid test collisions?**  
Maintain an experiment registry; block overlapping tests in the same funnel stage.

