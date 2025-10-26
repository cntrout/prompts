# Success Metrics Prompt — README

**What this is**  
A practical prompt that helps teams define **clear, non‑vanity success metrics** before building or launching. It leads you from the *why* to a defensible **primary metric**, supporting metrics, **guardrails**, realistic **targets**, and a **measurement plan**. The original prompt is preserved verbatim.

> Original prompt: `prompts/success-metrics-ORIGINAL.md`

---

## When to use this
- You need to align on **what success looks like** for a feature.  
- You want metrics that measure **customer value** and **business outcomes**—not just what’s convenient to count.  
- You need a standard structure for PRDs, A/B tests, and post‑launch reviews.

---

## How it’s organized
1. **`<feature_inputs>`** — The only section you edit (feature, why, audience, baseline).  
2. **`<metrics_framework>`** — Guidance to pick metric types, primary metric, guardrails, targets, and measurement plan.  
3. **Example definition** — A ready‑to‑paste metrics spec template.

Keep the framework text stable; fill in only the bracketed `[]` fields. fileciteturn9file0

---

## Quick start
1) Open `prompts/success-metrics-ORIGINAL.md`.  
2) Complete **all** `[]` fields in **`<feature_inputs>`**.  
3) Choose a **primary** metric, 1–3 **secondary** metrics, and 2–4 **guardrails**.  
4) Set **Baseline → Target → Timeline** and write a **Measurement plan** (events, dashboard, cadence).

---

## Input cheat‑sheet — realistic PM examples for **every `[]`**

Below are **three diverse product scenarios**. Each includes entries for all bracketed fields in `<feature_inputs>` and shows how to set targets & guardrails.

### Scenario A — E‑commerce Checkout: One‑click Address Validation
**WHAT YOU'RE BUILDING:** `[One‑click address validation in checkout to prevent typos and failed deliveries]`  
**WHY YOU'RE BUILDING IT:**  
- Problem it solves: `[High drop‑off at address step; failed deliveries]`  
- Expected benefit: `[Higher checkout completion; fewer delivery exceptions/support tickets]`  
- Strategic goal: `[Increase revenue; cut post‑purchase costs]`  
**WHO IT'S FOR:** `[Mobile shoppers; high‑volume regions US/CA/UK]`  
**CURRENT STATE:** `[Checkout completion 5.2% site‑wide (mobile 4.1%); 35% of address step abandons show address errors]`  

**Success definition (users/business):**  
- Users: `[Faster, error‑free address entry]`  
- Business: `[More successful orders; fewer reships/refunds]`

**Primary metric:** `Checkout completion rate (orders / sessions reaching checkout)`  
**Targets:** Baseline `[5.2%]` → Target `[+0.8 – +1.5 pp]` → Timeline `[2–4 weeks]`  
**Guardrails:** `LCP < 2.5s; Refund rate ≤ baseline; Address error rate ↓`  
**Measurement plan:** Events `[address_autocomplete_shown, address_autocomplete_selected, checkout_completed]`; Dashboard `[Looker “Address Validation”]`; Cadence `W1 early, M1 decision, Q1 long‑term`

---

### Scenario B — B2B SaaS: Saved Views for Dashboards
**WHAT YOU'RE BUILDING:** `[Saved Views so users can pin filters and return instantly]`  
**WHY YOU'RE BUILDING IT:**  
- Problem it solves: `[Users rebuild the same filters repeatedly]`  
- Expected benefit: `[Higher engagement depth; faster time‑to‑insight]`  
- Strategic goal: `[Improve Pro/Enterprise retention]`  
**WHO IT'S FOR:** `[Analysts/admins in mid‑market accounts]`  
**CURRENT STATE:** `[D30 retained_active_users 32%; median sessions/week 1.3; 58% re‑apply same filters]`  

**Success definition:**  
- Users: `[Less repetition; saved time]`  
- Business: `[Higher D30 retention]`

**Primary metric:** `D30 retained_active_users (Pro/Enterprise)`  
**Targets:** Baseline `[32%]` → Target `[+2 – +4 pts]` → Timeline `[8–12 weeks]`  
**Guardrails:** `Query time p95 ≤ 1.0s; error rate ≤ baseline; support contacts neutral`  
**Measurement plan:** Events `[saved_view_created, saved_view_opened]`; Dashboard `[Mixpanel Retention + Saved Views Adoption]`; Cadence `W1 adoption, M1 leading indicators, Q1 D30`

---

### Scenario C — Fintech: Network‑level Smart Retries
**WHAT YOU'RE BUILDING:** `[Issuer‑aware smart retries with BIN‑specific windows]`  
**WHY YOU'RE BUILDING IT:**  
- Problem it solves: `[Soft declines on first attempt]`  
- Expected benefit: `[Higher authorization rate with minimal cost]`  
- Strategic goal: `[Increase processing volume & NRR]`  
**WHO IT'S FOR:** `[Recurring merchants; cross‑border issuers]`  
**CURRENT STATE:** `[Auth rate 88.7% blended; long‑tail BINs 83.2%]`  

**Success definition:**  
- Users: `[Fewer false declines; fewer manual follow‑ups]`  
- Business: `[More successful transactions per active merchant]`

**Primary metric:** `Authorization rate (%)`  
**Targets:** Baseline `[88.7%]` → Target `[+0.6 – +1.2 pts]` → Timeline `[4–6 weeks]`  
**Guardrails:** `Chargeback rate ≤ baseline; latency p95 within SLA; complaints neutral`  
**Measurement plan:** Events `[retry_attempted, retry_success, decline_code]`; Dashboard `[Looker “Retry Performance”]`; Cadence `W1 early, M1 decision, Q1 NRR`

---

## What this framework guarantees
- **Value‑aligned** metrics (start with users, then business).  
- Balanced **leading/lagging** coverage.  
- A single **primary** metric that is measurable and sensitive.  
- **Guardrails** so you don’t regress core experiences.  
- **Targets & timelines** that drive crisp decisions.  
- A simple **measurement plan** you can own.

---

## Repo layout
```
prompt-library-success_metrics/
├─ prompts/
│  └─ success-metrics-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-success_metrics.zip  ← packaged artifact
```

---

## FAQ
**Can I pick revenue as primary?**  
Only if the feature directly changes purchase behavior; otherwise keep revenue as an output metric.

**What if I don’t know baselines?**  
Run a quick baseline measurement first or mark baseline as provisional and set a plan/date to replace it.

**How do I avoid gaming?**  
Write “what’s in/out,” exclude internal/test traffic, and choose guardrails that would reveal gaming.

