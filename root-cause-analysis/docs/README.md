# Root Cause Analysis (RCA) Prompt — README

**What this is**  
A reusable prompt that helps teams run clear, blame‑free Root Cause Analyses. It gives you a lightweight input block to capture facts, a structured framework (Problem → 5 Whys → Contributing Factors → Corrective Actions → Lessons → Follow‑Up), and a set of common patterns and principles so issues actually stay fixed. The original file is preserved verbatim.

> Original prompt kept intact at: `prompts/root-cause-analysis-ORIGINAL.md`

---

## When to use it
- Any production incident, customer‑facing defect, or risky process miss
- Slower‑burn failures (e.g., data drift, rising error budgets, churn spike)
- Post‑mortems for launches that underperform

The goal is to find **systemic** causes (process, tooling, tests, ownership) rather than blaming individuals.

---

## How it’s organized

1. **`<rca_inputs>`** — A quick form to capture **what happened** before analysis.
2. **`<rca_framework>`** — The structured write‑up (Problem, 5 Whys, etc.).
3. **`<rca_patterns>`** — Common failure patterns with fixes.
4. **`<meta_guidance>`** — Principles: don’t stop at symptoms, avoid blame, favor prevention.

You only edit the bracketed fields in **`<rca_inputs>`** (see examples below). The rest guides the output and should stay unchanged.

---

## Quick start
1. Open `prompts/root-cause-analysis-ORIGINAL.md`.
2. Fill out **every** `[]` inside **`<rca_inputs>`** (examples below).
3. Use the **Framework** section to complete the 5 Whys, actions, and lessons.
4. Share the RCA broadly and schedule the follow‑up review.

> Tip: If it feels like “human error,” go one level deeper. What in the system allowed the error?

---

## Input cheat‑sheet (examples for every `[]` in `<rca_inputs>`)

Below are **three distinct real‑world PM scenarios**. Pick the one closest to your incident as a reference for how to fill the fields.

### Scenario A — Mobile app crash after release (auth SDK upgrade)
**WHAT HAPPENED:**  
`Android app v6.3 crashed on launch for users with devices running Android 10 due to an auth SDK initialization bug.`

**WHEN:**  
`2025‑10‑12 13:05–15:42 ET. Crash rate spiked within 10 minutes of rollout to 25% of users; rollback completed at 15:42.`

**IMPACT:**  
- Users affected: `~18% DAU (Android)`  
- Business impact: `Elevated support tickets (+240%), drop in daily orders (‑6.1%) during the window`  
- Duration: `~2h37m`

**IMMEDIATE FIX:**  
`Rolled back to v6.2 and paused staged rollout; hotfixed feature flag to bypass SDK init path.`

**CONTEXT:**  
`Auth provider SDK upgraded from 4.8→5.0; QA covered Android 12/14 but not Android 10; crash not reproducible on emulators.`

---

### Scenario B — Billing overcharge after tax rules change
**WHAT HAPPENED:**  
`Recurring invoices for EU customers applied VAT twice after a config change to the tax rules engine.`

**WHEN:**  
`First incorrect invoices generated 2025‑09‑30 00:15 UTC; detected 2025‑10‑01 08:20 CET via support escalation; fix at 12:10 CET.`

**IMPACT:**  
- Users affected: `412 EU subscribers (9.4% of MRR)`  
- Business impact: `~$14,600 in overcharges; risk of churn, refunds issued, potential reputation hit`  
- Duration: `~36 hours`

**IMMEDIATE FIX:**  
`Patched tax rule to remove duplicate VAT application; issued automated credits/refunds; sent apology email.`

**CONTEXT:**  
`New “Digital Services” VAT category added; missing parity tests between rating service and invoicing service; change shipped Friday evening.`

---

### Scenario C — Data pipeline delay breaks product analytics
**WHAT HAPPENED:**  
`Nightly ETL job stalled on schema mismatch; dashboards showed stale data and experiments paused automatically.`

**WHEN:**  
`Delay started 2025‑10‑07 02:00 UTC; discovered at 09:10 UTC by growth analyst; resolved by 16:30 UTC after reprocessing.`

**IMPACT:**  
- Users affected: `Product/Growth analysts; feature teams (7 experiment owners)`  
- Business impact: `Blocked decisions for daily standups; one launch gate delayed 24h`  
- Duration: `~14.5 hours`

**IMMEDIATE FIX:**  
`Replayed job with corrected schema mapping; backfilled missing partitions; restarted dependent Airflow DAGs.`

**CONTEXT:**  
`Upstream app added new nullable column without versioned contract; schema enforcement rule too strict (fail-fast).`

---

## What the framework enforces (and why it works)

- **The Problem**: describes the **observable** symptom and impact in concrete terms.
- **The 5 Whys**: digs from symptom → proximate cause → systemic root cause.
- **Contributing Factors**: captures architecture, process, human, and org-level contributors.
- **Corrective Actions**: time‑bounded tasks (week/month/quarter) with **owners** and a measurable “how we’ll know it’s fixed.”
- **Lessons Learned**: institutionalize improvements beyond the incident.
- **Follow‑Up**: keeps momentum so fixes don’t quietly die on the vine.

---

## Good practices (from the prompt’s meta‑guidance)
- **Blame the system, not the person.** Replace “Alex shipped bad code” with “No pre‑prod performance tests for service X.”
- **Don’t stop at the first answer.** The first “why” is a symptom.
- **Multiple causes can be true.** Capture all contributors you can act on.
- **Prevention > description.** The RCA is only as good as the permanent fixes it drives.
- **Document and share.** RCAs are training material for new teammates.

---

## Repository layout

```
prompt-library-root-cause-analysis/
├─ prompts/
│  └─ root-cause-analysis-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-root-cause-analysis.zip  ← export artifact
```

---

## FAQs
**Q: Can I tweak sections?**  
A: Keep the `-ORIGINAL` file unchanged. If you need variants, duplicate it and edit the copy.

**Q: Who fills this out?**  
A: Incident owner (PM/EM/SRE) collaborates with affected teams; PM ensures business impact and follow‑ups are captured.

**Q: How do we make sure actions stick?**  
A: Add actions to your backlog with owners, use a label like `rca`, and schedule the **Review date** in the RCA itself.
