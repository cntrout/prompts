# Impact Sizing Prompt — README

**What this is**  
A practical prompt that helps you turn a fuzzy “how big is this?” question into a **defensible, assumption‑driven impact model**. It walks you from inputs → value chain → assumptions → math → validation → business translation (and it bakes in sanity checks to avoid wishful thinking). The original prompt is preserved **verbatim** for traceability.

> Original file: `prompts/impact-sizing-ORIGINAL.md`

---

## When to use this
- You need to **quantify potential impact** before prioritizing a feature/initiative.  
- You want a **clear, honest model** (not hand‑wavy, not fantasy).  
- You need a **one‑pager** that leaders can challenge and say “ship / don’t ship / validate first.”

---

## How the prompt is organized
1. **`<sizing_inputs>`** — You fill in your context (these are the only fields you edit).  
2. **`<sizing_framework>`** — Step‑by‑step method (value chain → assumptions → math → scenarios).  
3. **`<quality_check>`** — A checklist so the model is believable and actionable.  
4. **`<meta_wisdom>`** — Mindsets to avoid common sizing failure modes.

> Do **not** change the prompt wording. Only fill the `[]` fields in **`<sizing_inputs>`**. The framework will guide the rest.

---

## Quick start
1) Open `prompts/impact-sizing-ORIGINAL.md`.  
2) Complete **every** field in **`<sizing_inputs>`**.  
3) Run the prompt to generate value chain, assumptions, math, and scenarios.  
4) Use **Quality Check** to pressure‑test; add an experiment plan to de‑risk.

---

## Input cheat‑sheet — examples for **every `[]` field** in `<sizing_inputs>`

Below are **three very different PM scenarios**. Each shows realistic entries for all inputs (1–10 + uploads). Copy the closest one and tweak.

### Scenario A — E‑commerce: One‑click Address Validation (conversion lift)
1. **Feature/initiative description:** `[One‑click address validation in checkout to prevent typos and failed deliveries]`  
2. **Metric impacted:** `[Conversion]`  
3. **Current baseline:** `[Checkout completion = 5.2% site‑wide; mobile = 4.1%]`  
4. **Hypothesis about impact:** `[Reduce checkout drop‑offs on address step; +0.8–1.5% absolute site‑wide]`  

5. **Total addressable users:** `[420,000 sessions/month reach checkout address step]`  
6. **Expected adoption rate:** `[60% of address‑step users will use the one‑click suggestion]`  
7. **Time to impact:** `[Effects visible within 2 weeks; full adoption by week 6]`  

8. **Usage analytics:** `[35% of address‑step abandonments include invalid address errors; mobile share = 62%]`  
9. **Customer research:** `[48% of surveyed customers report frustration with manual address entry; N=600]`  
10. **Comparable features:** `[Competitor X reports +1.2% absolute conversion from address auto‑complete; our past “1‑click card update” gave +0.6%]`  

**Uploads (if available):** Analytics funnel screenshot, heatmap of address field interactions, competitor case study PDF.

---

### Scenario B — B2B SaaS: “Saved Views” in Analytics (retention & engagement)
1. **Feature/initiative description:** `[Saved Views for dashboards so users can pin filters and return quickly]`  
2. **Metric impacted:** `[Retention]`  
3. **Current baseline:** `[Day‑30 retained_active_users = 32% for Pro tier]`  
4. **Hypothesis about impact:** `[Saved Views increases weekly engagement depth → +2–4 pts D30 retention]`  

5. **Total addressable users:** `[18,500 monthly active Pro users]`  
6. **Expected adoption rate:** `[25% create ≥1 Saved View within first 30 days]`  
7. **Time to impact:** `[Requires habit formation; expect 8–12 weeks to full effect]`  

8. **Usage analytics:** `[Median sessions/week = 1.3; 58% of users re‑apply the same filters repeatedly]`  
9. **Customer research:** `[User interviews: 9/12 asked for faster “return to last view”; support tag #saved‑filters appears 140×/qtr]`  
10. **Comparable features:** `[Our “Starred Dashboards” increased weekly opens +11%; Competitor Y claims +3 pts D30 with saved filters]`  

**Uploads:** Mixpanel retention curves, tagged support tickets export, interview notes snippet.

---

### Scenario C — Fintech Payments: Network‑level Smart Retries (revenue/efficiency)
1. **Feature/initiative description:** `[Network‑level smart retries with issuer‑aware rules and BIN‑specific windows]`  
2. **Metric impacted:** `[Revenue]`  
3. **Current baseline:** `[Authorization rate = 88.7% blended; long‑tail BINs = 83.2%]`  
4. **Hypothesis about impact:** `[+0.6–1.2 pts auth rate from intelligent retry windows; biggest lift on cross‑border cards]`  

5. **Total addressable users:** `[12,400 active merchants; 6.8M payments/month]`  
6. **Expected adoption rate:** `[Default‑on for SDK merchants (70%); opt‑in for API merchants (30%)]`  
7. **Time to impact:** `[Gradual; 4–6 weeks as risk models warm and merchants update SDKs]`  

8. **Usage analytics:** `[Top decline codes: Do Not Honor (31%), Insufficient Funds (18%); highest lift opportunity in BR/IN]`  
9. **Customer research:** `[Enterprise merchants explicitly asked for retry controls; 14/20 cite revenue loss on soft declines]`  
10. **Comparable features:** `[Acquirer Z publishes +0.8–1.5 pts with network retries; our past “card updater” yielded +0.4 pts]`  

**Uploads:** Decline code histogram, regional auth‑rate table, merchant survey quotes.

---

## What the framework enforces (so your model is credible)
- **Value chain clarity:** Feature → behavior change → metric → business.  
- **Explicit assumptions:** Adoption, effect size, and ramp time with confidence levels.  
- **Scenario math:** Conservative / Moderate / Optimistic with shown calculations.  
- **Validation plan:** What could make you wrong, and how to test quickly.  
- **Business translation:** From % lift to **$ impact**, **payback**, and a recommendation.

---

## Tips & pitfalls
- Don’t assume >50% adoption unless you have strong evidence; ramp matters.  
- Keep effects realistic: most features move core metrics **1–5%**.  
- Add **anti‑cannibalization** notes (e.g., “saves buyers from using the old flow”).  
- Include **owner + date** on actions that come out of the model.

---

## Repository layout
```
prompt-library-impact_sizing/
├─ prompts/
│  └─ impact-sizing-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-impact_sizing.zip  ← packaged artifact
```

---

## FAQ
**Can I tweak the framework?**  
Keep the `-ORIGINAL` file immutable. If you need org‑specific variations, copy it and edit the copy.

**What if I lack data for assumptions?**  
State your best estimate, mark confidence **Low**, and add a small experiment (fake door, UX prototype, cohort analysis) to improve it.

**How do I avoid bias?**  
Run a quick **pre‑mortem**: list how you could be wrong, then design a check for each risk.

