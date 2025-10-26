# User Research Synthesizer — README

**What this is**  
A reusable prompt that takes messy research inputs (interviews, surveys, tickets, analytics) and turns them into a **decision-ready synthesis** with clear priorities and next steps. The original prompt is preserved **verbatim**.

> Original file: `prompts/user-research-synthesizer-ORIGINAL.md`

---

## When to use it
- You’ve gathered interviews, surveys, usability tests, support tickets, or analytics and need a coherent story.  
- You want **prioritized insights** (not a wall of quotes) tied to product and business outcomes.  
- You need an **executive-ready** summary plus a **full synthesis** and **appendix**.

---

## How the prompt is organized

1. **`<research_inputs>`** — The _only_ place you edit before running. You upload materials and answer short context questions.  
2. **`<synthesis_process>`** — Four phases the model follows: **Immersion & Inventory → Thematic Analysis → Prioritization → Synthesis Output**.  
3. **`<quality_checks>`** — Five tests (Quotes, Frequency, Actionability, Honesty, Segments) to keep the bar high.  
4. **`<output_format>`** — What the model will produce: **Executive Summary**, full synthesis, **Appendix**, and a **one-pager**.  
5. **`<meta_guidance>`** — Style rules (prioritize, use exact quotes, separate symptoms from root causes).

Keep the wording of the prompt itself unchanged; only supply inputs in the spots indicated. fileciteturn10file0

---

## Quick start
1) Open `prompts/user-research-synthesizer-ORIGINAL.md`.  
2) Upload all research files (transcripts, survey CSV, support export, analytics screenshots).  
3) Fill the **Context Questions** inside `<research_inputs>`.  
4) Run once to get a draft; tighten by adding missing materials or clarifying audience/decision criteria.  
5) Use the **quality checks** to self-critique before sharing.

---

## Input cheat‑sheet — realistic PM examples for every field in `<research_inputs>`

Below are **three very different PM scenarios**. Each shows concrete, copy‑pasteable answers for the inputs. (Where the synthesis uses square‑brackets like `[X out of Y]` or `[exact words]`, the examples below illustrate realistic values you’ll later see in the output.)

### Scenario A — E‑commerce Checkout: Address Validation

**RESEARCH MATERIALS (upload examples):**  
- `Interviews`: 12 recent purchasers + 8 abandoners (transcripts)  
- `Survey`: 1,960 responses (Sep 2025 NPS follow‑up)  
- `Support`: 340 tickets tagged `address_issue` (CSV)  
- `Analytics`: Checkout funnel (Looker screenshots), device mix  
- `Notes`: 3 moderated usability sessions on mobile checkout

**CONTEXT QUESTIONS**  
1) **What are you trying to learn?** → `Why users abandon at the address step and which changes would most reduce drop‑off.`  
2) **Who are these users?** → `US/CA/UK mobile shoppers, repeat buyers vs first‑timers.`  
3) **What decisions will this inform?** → `Address autocomplete + validation scope for Q4; SLA for latency.`  
4) **Any hypotheses?** → `Typos and format confusion drive errors; auto‑suggest would cut friction on mobile.`  
5) **Timeline?** → `Initial synthesis in 1 week; design decisions in 2 weeks.`  
6) **Audience?** → `PM, Design, Checkout Eng, VP Growth.`  
7) **Format needed?** → `Slide‑style executive summary + full doc; one‑pager for execs.`

---

### Scenario B — B2B SaaS Analytics: Saved Views

**RESEARCH MATERIALS (upload):**  
- `Interviews`: 15 admins/analysts (enterprise + mid‑market)  
- `Survey`: 420 responses on dashboard usage  
- `Support`: 110 tickets tagged `saved_filters`  
- `Analytics`: Retention curves, query time p95, feature usage by segment  
- `Existing docs`: Prior “Starred Dashboards” study

**CONTEXT QUESTIONS**  
1) `Which workflows keep users coming back to dashboards, and where do they get stuck recreating filters?`  
2) `Analysts/admins in Pro & Enterprise; heavy vs light users.`  
3) `Prioritize Saved Views MVP scope and adoption plan.`  
4) `Saving state reduces friction; adoption → higher D30.`  
5) `Draft in 5 days; roadmap decision this quarter.`  
6) `PM, Design, Eng Lead, Sales Enablement.`  
7) `Full insights doc + personas appendix for enablement.`

---

### Scenario C — Fintech Payments: Smart Retries (Issuer Optimization)

**RESEARCH MATERIALS (upload):**  
- `Interviews`: 10 enterprise merchants (payments ops leads)  
- `Survey`: 75 responses from merchant council  
- `Support`: 68 tickets tagged `decline_rate`  
- `Analytics`: Authorization by BIN/country, decline codes, retry outcomes  
- `Notes`: Merchant council roundtable minutes

**CONTEXT QUESTIONS**  
1) `Which retry strategies increase auth rates without raising chargebacks?`  
2) `Recurring subscription merchants; cross‑border issuers; risk analysts.`  
3) `Decide on default‑on vs opt‑in, and which retry windows to ship.`  
4) `Network‑aware retries lift long‑tail BIN success.`  
5) `Recommendation needed before billing cycle change (3 weeks).`  
6) `PM, Risk Eng, BD, Finance.`  
7) `Executive summary + full synthesis; one‑pager for legal review.`

> **Tip:** If some materials are missing, still run the prompt. It will call out gaps during **Immersion & Inventory** so you can add them later.

---

## What the process enforces (and why it works)

- **Immersion & Inventory** — counts participants, methods, segments, and flags bias/data gaps.  
- **Thematic Analysis** — open‑codes quotes and behaviors, then quantifies **frequency**, **intensity**, and **segment spread**.  
- **Prioritization** — ranks insights by **Impact × Evidence Strength** and **Actionability** (2×2).  
- **Synthesis Output** — ships an **Executive Summary**, 8–10 **Key Insights** with quotes and numbers, segment callouts, contradictions, and **Recommended Next Steps**.

---

## How to get great outputs
- Upload **verbatim** transcripts and **raw** survey data; avoid only summaries.  
- Include a quick **analytics slice** (funnel, retention, p95 latency) to strengthen evidence.  
- Provide your **decision window** and **target audience** so tone/format fit.  
- Use the **quality checks** to tighten: ensure 2–3 quotes per major insight and explicit `X of Y` frequencies. fileciteturn10file0

---

## Repository layout

```
prompt-library-user_research_synthesizer/
├─ prompts/
│  └─ user-research-synthesizer-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-user_research_synthesizer.zip  ← packaged artifact
```

---

## FAQ
**Do I need perfect data to start?**  
No. The **Immersion** phase highlights gaps; you can iterate.

**Can it create personas?**  
Yes—choose “user personas” as the **format** and upload enough interviews/surveys spanning segments.

**How does it prioritize?**  
By **Impact**, **Evidence strength**, and **Actionability** using a 2×2 matrix—top right (High × Strong) wins.

**What about contradictions?**  
They’re a first‑class section. The doc calls them out and suggests follow‑ups (more sampling, targeted tests).

