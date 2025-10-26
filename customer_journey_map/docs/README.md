# Customer Journey Map Prompt — README

**What this is**  
A reusable prompt that helps you map an end-to-end **customer/user journey** and turn it into concrete product opportunities. It guides you through defining boundaries, stages, actions & touchpoints, emotions & pain points, gaps, opportunities, and a prioritized action plan. The original prompt is preserved **verbatim** for traceability.

> Original file: `prompts/customer-journey-map-ORIGINAL.md`

---

## When to use it
- You’re planning a **new flow** (onboarding, billing, migration) and want to see the full funnel experience.  
- You’re seeing **drop-off, support pain, or churn** and need to pinpoint where/why.  
- You need a shared artifact to align **PM, Design, Eng, Sales/CS, and Support** on the top opportunities.

---

## How the prompt is organized

1. **`<journey_inputs>`** — The only section you edit. You specify what journey, who the user is, what research you have, and what questions you want to answer.  
2. **`<mapping_framework>`** — A 7‑step process (boundaries → behaviors & touchpoints → emotions/pain → gaps → opportunities → prioritization → product decisions).  
3. **Example Journey Map Structure** — A copy‑pasteable outline the model will populate.

Keep the framework text unchanged; only fill the bracketed fields in **`<journey_inputs>`**.

---

## Quick start
1) Open `prompts/customer-journey-map-ORIGINAL.md`.  
2) In **`<journey_inputs>`**, complete all `[]` fields and tick the `[ ]` boxes you care about.  
3) Run the prompt to generate a first pass.  
4) Iterate by adding missing research (quotes, funnel screenshots) and refining stage names.  

---

## Input cheat‑sheet — realistic PM examples for **every `[]`** in `<journey_inputs>`

Below are **three very different product scenarios** to show exactly how to fill the inputs.

### Scenario A — SaaS Onboarding (self‑serve analytics tool)
**WHAT YOU'RE MAPPING:**  
`[new user onboarding]`

**USER PERSONA:**  
`[Data‑curious PM in a mid‑market SaaS company; light SQL, heavy dashboard usage]`

**YOUR RESEARCH:**  
`[12 user interviews, 1,800 signup sessions (Mixpanel), 145 support tickets tagged 'onboarding', 3 moderated usability tests]`

**WHAT YOU WANT TO UNDERSTAND:**  
- `[x] Where do users struggle?`  
- `[x] Where do they drop off?`  
- `[x] Where are opportunities?`  
- `[ ] What's the emotional journey?`

---

### Scenario B — B2B Purchase & Implementation (enterprise security product)
**WHAT YOU'RE MAPPING:**  
`[enterprise purchase process]`

**USER PERSONA:**  
`[Security director at a 500–2,000 employee company; buyer + technical evaluator]`

**YOUR RESEARCH:**  
`[6 opportunity win/loss interviews, 9 customer calls, 72-day CRM cycle analysis, 38 procurement tickets, sales‑engineer notes]`

**WHAT YOU WANT TO UNDERSTAND:**  
- `[x] Where do users struggle?`  
- `[ ] Where do they drop off?`  
- `[x] Where are opportunities?`  
- `[x] What's the emotional journey?`

---

### Scenario C — Two‑sided Marketplace (home services booking)
**WHAT YOU'RE MAPPING:**  
`[daily workflow]`

**USER PERSONA:**  
`[Homeowner booking first cleaning; iOS, price‑sensitive, prefers same‑day]`

**YOUR RESEARCH:**  
`[2,100 session replay samples, 480 CS tickets tagged 'reschedule/cancel', NPS verbatims (N=1,240), funnel data for search→book→complete]`

**WHAT YOU WANT TO UNDERSTAND:**  
- `[ ] Where do users struggle?`  
- `[x] Where do they drop off?`  
- `[x] Where are opportunities?`  
- `[x] What's the emotional journey?`

---

## What the framework enforces (and why it works)

1) **Define boundaries** — Start earlier than the product UI (awareness/setup) and end at **goal achieved**, not just “form submitted.”  
2) **Stage the journey (3–7)** — Enough detail to be useful, not overwhelming.  
3) **Actions & touchpoints per stage** — What users do, decide, and where they interact (marketing, product, sales, support).  
4) **Emotions & pain points** — Use an emotional curve and **🔥 intensity** to triage (🔥🔥🔥 critical, 🔥🔥 major, 🔥 minor).  
5) **Expose gaps** — Information, tool, support, and expectation gaps.  
6) **Turn pain into opportunities** — Quick wins, major improvements, and delight ideas.  
7) **Prioritize & decide** — Impact × Effort matrix and concrete product decisions (features, copy, flow, support, comms).

This prevents “pretty wallpaper” maps and pushes toward **actionable decisions**.

---

## Tips for great outputs
- Bring **evidence**: quotes, funnel screenshots, support counts; the map will surface **frequency + intensity**.  
- Name stages in the user’s language (“Find a pro”, “Get a quote”), not your org chart.  
- Keep 3–7 stages; merge or split until each stage has distinct actions & needs.  
- Mark at most **3–5 top opportunities**; attach owners and timeframes.

---

## Repository layout

```
prompt-library-customer_journey_map/
├─ prompts/
│  └─ customer-journey-map-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-customer_journey_map.zip  ← packaged artifact
```

---

## FAQ
**Do I need both qual and quant?**  
No, but having both strengthens decisions. Start with what you have; the process will highlight gaps to fill.

**How do I keep it from becoming a poster nobody uses?**  
Force the Step 7 **product decisions** and attach the **Prioritized Opportunities** to your backlog with owners/dates.

**What about non‑linear journeys?**  
Capture alternate paths under each stage (“if fail, retry via support chat”). Don’t force a single path if reality branches.

