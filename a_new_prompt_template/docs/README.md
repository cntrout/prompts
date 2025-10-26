# “A New Prompt Template” — README

**What this is**  
A flexible, reusable **prompt template** that you can adapt to many tasks—research, synthesis, analysis, writing, decision memos. It cleanly separates **Inputs**, a structured **Framework**, **Outputs**, **Exemplars**, and **Meta Guidance**. The source file is preserved verbatim.

> Original prompt: `prompts/a-new-prompt-template-ORIGINAL.md`

---

## When to use it
- You want a standard, team‑wide skeleton for new prompts.  
- You’re spinning up workflows like **RFC Summarizer**, **Vendor Comparison**, **Post‑mortem Synthesizer**, **Roadmap RFC Writer**, etc.  
- You need repeatable outputs with consistent headings for docs/notion.

---

## Sections at a glance
- **`<prompt_name>`**: wrapper and identifier.  
- **`<prompt_inputs>`**: the only part you change per run (text fields, structured fields, checkbox selections, and free‑form context).  
- **`<prompt_framework>`**: role + outcome + numbered process + output headings.  
- **`<prompt_exemplars>`**: patterns/templates/examples to imitate.  
- **`<meta_guidance>`**: style/tone/constraints and helpful rules.

Keep the framework stable; iterate by improving **inputs**.

---

## Quick start
1. Open `prompts/a-new-prompt-template-ORIGINAL.md`.  
2. Fill the `[]` checklist and the `{}` placeholders in **`<prompt_inputs>`** using one of the scenarios below.  
3. (Optional) Drop in 1–2 exemplars.  
4. Run and review. Tighten inputs, not framework wording.

---

## Input cheat sheet — realistic PM examples for **all input fields**

The input block uses curly braces `{}` for pasted/structured data and `- [ ]` for switchable options. Here are three very different scenarios.

### Scenario A — Feature Prioritization Brief (E‑commerce)

**YOUR INPUT DESCRIPTION 1:**  
`{Paste problem statement & goals. Example: "Checkout address errors cause drop‑offs; goal: +0.8–1.5% absolute completion."}`

**YOUR INPUT DESCRIPTION 2:**  
`{Paste constraints: legal, performance, platform. Example: "PCI scope unchanged; p95 < 400ms; mobile first."}`

**OR input structured data:**  
- `Label 1: {Target metric = Checkout completion}`  
- `Label 2: {Guardrail = Refund rate, CS contacts}`

**SELECTION CASE:**  
- `[x] Option 1` → *Ask for problem framing + value chain + risks*  
- `[ ] Option 2`

**CONTEXT:**  
- `{free form context}` → `Leadership review on Thursday.`  
- `Label 1: {Competitor offers Google Address Autocomplete}`

---

### Scenario B — API Change Design Review (Fintech)

**YOUR INPUT DESCRIPTION 1:**  
`{Paste proposed API diff or OpenAPI snippet.}`

**YOUR INPUT DESCRIPTION 2:**  
`{Paste migration notes: "Deprecate v1 in 90 days; retry semantics change; idempotency required."}`

**OR input structured data:**  
- `Label 1: {Surfaces = REST + SDK (Node, Python)}`  
- `Label 2: {Affected systems = Billing, Ledger}`

**SELECTION CASE:**  
- `[ ] Option 1`  
- `[x] Option 2` → *Ask for compatibility matrix, edge cases, and migration plan*

**CONTEXT:**  
- `{free form context}` → `Top 50 merchants use custom retries`  
- `Label 1: {SLA impact must be ≤ 0.1% failures}`

---

### Scenario C — Quarterly Incident Synthesis (Platform)

**YOUR INPUT DESCRIPTION 1:**  
`{Paste list of SEV incidents with timestamps and root causes.}`

**YOUR INPUT DESCRIPTION 2:**  
`{Paste business impact summary: tickets, downtime, affected revenue.}`

**OR input structured data:**  
- `Label 1: {Top categories = Deployments, Schema drift, Cloud provider}`  
- `Label 2: {Teams = Checkout, Risk, Notifications}`

**SELECTION CASE:**  
- `[x] Option 1` → *Ask for 5 Whys roll‑up + systemic fixes*  
- `[x] Option 2` → *Also produce exec‑summary slide bullets*

**CONTEXT:**  
- `{free form context}` → `Board review next week; focus on prevention & owners.`  
- `Label 1: {Introduce pre‑deployment contract tests}`

> **About `[ ]` boxes:** Put an `x` inside to turn an option on. Add your own options if needed, keeping the same `[ ]` syntax.

---

## What the framework will output
Under **`<prompt_framework>`**, the template defines:  
- A **role** (“You {role + context}”).  
- A **job** (“Your job: {desired outcome}”).  
- A **process** (Step 1…Step N).  
- A structured **Output** section with headings/sub‑sections (easy to port into docs, PRs, or tickets).

These headings act as your team’s “contract” for consistent write‑ups.

---

## Exemplars: best way to steer style fast
Drop in a short “golden” sample—e.g., your ideal executive summary or recommendation section. The LLM will mirror tone and structure without hardcoding voice rules.

---

## Meta guidance: guardrails that travel
Add timeless rules here, e.g.:  
- Be specific; prefer numbers over adjectives.  
- If data is missing, make assumptions explicit and label confidence.  
- Surface risks, dependencies, and decision tradeoffs.

---

## Repository layout
```
prompt-library-a_new_prompt_template/
├─ prompts/
│  └─ a-new-prompt-template-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-a_new_prompt_template.zip  ← packaged artifact
```

---

## FAQ
**Should I edit the framework text?**  
Prefer not to. Make a copy if you need to customize wording; keep the `-ORIGINAL` immutable for traceability.

**How many options can I use in the checklist?**  
As many as you need—use `[x]` to mark selected ones.

**What if all I have are links?**  
Paste links and give 1–2 bullets explaining why each matters (so the model doesn’t treat them equally).

