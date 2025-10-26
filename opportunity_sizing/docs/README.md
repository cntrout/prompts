# Opportunity Sizing Prompt — README

**What this is**  
A pragmatic, PM-friendly prompt to size a **feature/product/market** in a way that’s both **ambitious and defensible**. It walks you from inputs → methodology (top‑down / bottom‑up / value‑based) → TAM/SAM/SOM → scenarios → revenue model → validation → business case. The original prompt is preserved **verbatim**.

> Original file: `prompts/opportunity-sizing-ORIGINAL.md`

---

## When to use this
- You need a **quick but rigorous** view of the opportunity before committing roadmap or budget.  
- You’re preparing a **business case** or **board deck** and need a clear TAM → SAM → SOM story.  
- You want to **triangulate** using multiple methods and expose assumptions up front.

---

## How the prompt is organized
1. **`<sizing_inputs>`** — The only section you edit. You provide the “what,” current knowledge, business context, and confidence level.  
2. **`<sizing_framework>`** — The 8‑step process the model follows: methodology → TAM → SAM → SOM → scenarios → revenue model → validation → business case.  
3. **Example Opportunity Sizing** — A clean template you can paste into a doc/slide.

> Keep the framework text unchanged; only fill the bracketed `[]` fields in **`<sizing_inputs>`**.

---

## Quick start
1) Open `prompts/opportunity-sizing-ORIGINAL.md`.  
2) Fill **every** `[]` in **`<sizing_inputs>`** (see the three scenarios below).  
3) Run once to get **TAM/SAM/SOM + scenarios + revenue model**.  
4) Tighten assumptions, add sources, and re-run. Attach the output to your PRD/one‑pager.

---

## Input cheat‑sheet — realistic PM examples for **every `[]`** in `<sizing_inputs>`

Three **totally different** contexts to copy/tweak. Each fills **all** placeholders (What you’re sizing, What you know, Business context, Confidence level).

### Scenario A — B2B SaaS: “AI Doc Assistant” Add‑on (per-seat)
**WHAT YOU'RE SIZING:**  
`[AI documentation assistant add‑on for our developer platform]`

**WHAT YOU KNOW:**  
- Market data: `[~45M professional developers worldwide; ~7M in our ICP (English-speaking, cloud-native). GenAI code tools attach rates 15–30%.]`  
- User data: `[200k monthly active seats on our core product; 22% heavy docs usage; 9% already hitting rate limits.]`  
- Competitive data: `[GitHub Copilot Business $19/mo seat; Confluence AI add‑on $10–$15/seat; comparable “AI wiki” players quoting $12–$25/seat.]`

**BUSINESS CONTEXT:**  
- Current ARR/revenue: `[~$86M ARR]`  
- Target segments: `[Mid‑market (200–2,000 employees) and Enterprise SaaS]`  
- Pricing model: `[Add‑on, $15/seat/month with volume discounts; annual preferred]`

**CONFIDENCE LEVEL NEEDED:**  
- `[ ] Rough estimate (back of napkin)`  
- `[x] Business case (defendable numbers)`  
- `[ ] Board deck (high confidence)`

---

### Scenario B — Two‑Sided Marketplace: “Express Jobs” Same‑Day Offering
**WHAT YOU'RE SIZING:**  
`[Express same‑day jobs in top 12 cities for home services]`

**WHAT YOU KNOW:**  
- Market data: `[Local services TAM ~$600B US; ~8–12% of demand is urgent/same‑day according to industry reports and TaskRabbit/Thumbtack disclosures.]`  
- User data: `[We complete ~52k jobs/month; 17% cancellations tied to scheduling friction; CS tickets show 480/month asking for same‑day.]`  
- Competitive data: `[TaskRabbit same‑day premium +$15–$25; Uber-style surge models in two competitors.]`

**BUSINESS CONTEXT:**  
- Current ARR/revenue: `[GMV ~$78M; take rate 18% → ~$14M net revenue]`  
- Target segments: `[Urban zip codes with SLA‑capable supply density; categories: cleaning, handyman, furniture assembly]`  
- Pricing model: `[Dynamic “express fee” +$12–$25 on top of standard take rate]`

**CONFIDENCE LEVEL NEEDED:**  
- `[x] Rough estimate (back of napkin)`  
- `[ ] Business case (defendable numbers)`  
- `[ ] Board deck (high confidence)`

---

### Scenario C — Fintech: EU Freelancer FX Card (neobank expansion)
**WHAT YOU'RE SIZING:**  
`[EUR/GBP multi‑currency debit + FX for EU/UK freelancers]`

**WHAT YOU KNOW:**  
- Market data: `[~32M freelancers in EU/UK; avg cardable spend €1.2k–€1.8k/mo; FX exposure for cross‑border clients 20–35%.]`  
- User data: `[Current 410k MAU; 22% receive cross‑border payments via SEPA/SWIFT; avg balance €640; active carders 31%.]`  
- Competitive data: `[Wise/Revolut take ~0.3–2.0% FX; interchange yields ~0.2–0.3% in EU; premium tiers €7–€15/mo.]`

**BUSINESS CONTEXT:**  
- Current ARR/revenue: `[~€24M ARR from accounts + payments]`  
- Target segments: `[Freelancers/sole traders billing US/UK clients; marketplaces payouts]`  
- Pricing model: `[Interchange + FX spread (0.45–0.85%) + optional €9/mo premium]`

**CONFIDENCE LEVEL NEEDED:**  
- `[ ] Rough estimate (back of napkin)`  
- `[ ] Business case (defendable numbers)`  
- `[x] Board deck (high confidence)`

---

## What the framework enforces (8 steps, summarized)
1) **Pick methods** — Use **top‑down**, **bottom‑up**, **value‑based**; triangulate.  
2) **TAM** — Full opportunity via market totals, bottom‑up units×ARPU, or spend×capture %.  
3) **SAM** — Focus slice (geo, ICP, tech fit, regulation).  
4) **SOM** — Realistic capture (sales capacity, share %, timeline).  
5) **Scenarios** — Conservative/Base/Optimistic with stated assumption deltas.  
6) **Revenue model** — Customers × ARPU × retention, by segment/tier over time.  
7) **Validation** — Reality checks (deals/month, share), comps, and where you’re aggressive vs conservative.  
8) **Business case** — Investment, ROI/NPV, risks, break‑even/payback.

---

## Tips & pitfalls
- **Triangulate**: present 2–3 methods and reconcile differences.  
- **Source everything** (links, reports, or internal logic). If unknown, mark assumption and test plan.  
- Convert % into **people, deals, reps, months** so it’s operational.  
- Never present a single magic number—**show a range with scenarios** and confidence.

---

## Repository layout
```
prompt-library-opportunity_sizing/
├─ prompts/
│  └─ opportunity-sizing-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-opportunity_sizing.zip  ← packaged artifact
```

---

## FAQ
**Top‑down vs bottom‑up—when to prefer which?**  
Use top‑down when credible category totals exist; bottom‑up when you have solid **units** and **ARPU**. Value‑based helps when displacing spend.

**What if I lack market reports?**  
Start bottom‑up from your telemetry (active accounts, attach rates, pricing). Add a “Data to collect” list in Validation.

**How do I avoid optimism bias?**  
Pre‑commit to **decision thresholds** (e.g., “ship if base‑case SOM ≥ $5M in 3 years and payback < 18 months”).

