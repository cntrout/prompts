# User Persona Prompt — README

**What this is**  
A practical prompt that helps teams create **useful, evidence-backed user personas** (not decorative posters). It forces you to ground personas in real research, focus on behaviors/goals, and extract design/messaging implications. The original prompt is preserved **verbatim**.

> Original file: `prompts/user-persona-ORIGINAL.md`

---

## When to use it
- You’re kicking off a feature/initiative and need alignment on **who** you’re building for.  
- You’ve got interviews/surveys/usage data and want **patterns**, not anecdotes.  
- You need artifacts marketing, design, PM, and sales can **reference in decisions**.

---

## How the prompt is organized

1) **`<persona_inputs>`** — The only section you edit. You paste research and check the intended **purpose** (alignment, design, messaging, prioritization).  
2) **`<persona_framework>`** — Structured persona template (Overview → Demographics & Context → Jobs-to-be-Done → Behaviors → Pain → Motivations/Barriers → Quotes → Implications → Do/Don’t).  
3) **`<persona_patterns>`** — Common archetypes (Power User, Occasional User, Admin/Buyer, Evaluator) with design implications.  
4) **`<meta_guidance>`** — Principles to keep personas **real, specific, and actionable**.

Keep the framework text unchanged; only fill in the bracketed `[]` fields in **`<persona_inputs>`**.

---

## Quick start
1. Open `prompts/user-persona-ORIGINAL.md`.  
2. Fill every `[]` in **`<persona_inputs>`** and tick the `[ ]` boxes for **PURPOSE**.  
3. Run the prompt to generate 1–3 personas.  
4. Share with the team and iterate quarterly based on fresh data.

---

## Input cheat-sheet — realistic PM examples for **every `[]`** in `<persona_inputs>`

Below are **three distinct product contexts** showing concrete, copy-pasteable entries for **all** bracketed fields, including the PURPOSE checkboxes.

### Scenario A — Ecommerce Checkout (Mobile)

**YOUR RESEARCH:**  
- User interviews: `[20 recent buyers, 12 abandoners; semi-structured, Sep–Oct 2025]`  
- Usage data: `[Checkout funnel: cart→checkout 61%, address step→payment 43%; mobile share 62%]`  
- Customer segments: `[New vs returning shoppers; US/CA/UK; iOS vs Android]`  
- Feedback/quotes: `["Typing address on mobile is annoying", "I don't trust the suggested address when it's slow"]`

**WHAT YOU KNOW:**  
- Who uses your product: `[Consumers 18–55; price-sensitive; frequent promo users]`  
- How they use it: `[Shop weekly; add-to-cart on mobile; complete on mobile/desktop mix]`  
- Why they use it: `[Convenience, delivery speed, easy returns]`

**PURPOSE:**  
- `[x] Team alignment on target user`  
- `[x] Design guidance`  
- `[ ] Marketing messaging`  
- `[ ] Prioritization framework`

---

### Scenario B — B2B SaaS Analytics (Saved Views)

**YOUR RESEARCH:**  
- User interviews: `[15 admins/analysts across mid-market and enterprise]`  
- Usage data: `[58% re-apply same filters; p95 query time 0.9s; WAU 38k]`  
- Customer segments: `[Pro vs Enterprise tiers; heavy vs light users]`  
- Feedback/quotes: `["I keep rebuilding the same view", "Give me a way to pin my filters"]`

**WHAT YOU KNOW:**  
- Who uses your product: `[PMs/analysts in SaaS; data-savvy; collaborate with GTM teams]`  
- How they use it: `[Dashboards daily, ad-hoc analysis weekly; share links in Slack]`  
- Why they use it: `[Faster insight for roadmap and KPI reviews]`

**PURPOSE:**  
- `[x] Team alignment on target user`  
- `[x] Design guidance`  
- `[x] Marketing messaging`  
- `[ ] Prioritization framework`

---

### Scenario C — Fintech Payments Platform (Smart Retries)

**YOUR RESEARCH:**  
- User interviews: `[10 enterprise merchants (payments ops), 6 SMBs]`  
- Usage data: `[Auth rate 88.7% blended; long-tail BINs 83.2%; top decline codes: Do Not Honor 31%, Insufficient Funds 18%]`  
- Customer segments: `[Recurring vs one-time; domestic vs cross-border; card brands]`  
- Feedback/quotes: `["Let me tune retries by issuer", "Stop retrying cards that will never work"]`

**WHAT YOU KNOW:**  
- Who uses your product: `[Merchants with engineering teams; finance/risk stakeholders sign off]`  
- How they use it: `[API-first; dashboard for monitoring; weekly config changes]`  
- Why they use it: `[Increase authorization rates and revenue; reduce ops load]`

**PURPOSE:**  
- `[ ] Team alignment on target user`  
- `[x] Design guidance`  
- `[x] Marketing messaging`  
- `[x] Prioritization framework`

---

## What the framework enforces (and why it works)

- **Evidence-first**: personas built from interviews, behavior, and segments — not made-up demographics.  
- **Behavior & JTBD focus**: goals, jobs, and workflows over superficial traits.  
- **Pain → Implications**: each pain point must translate into product and messaging guidance.  
- **Do/Don’t**: specific instructions so teams actually act differently.

---

## Tips for great personas
- Keep to **2–4** personas max; more means you’re not focused.  
- Use **exact quotes** to keep it real.  
- Quantify where possible (e.g., “**58%** re-apply filters”).  
- Revisit **quarterly**; personas evolve with product/market.

---

## Repository layout

```
prompt-library-user_persona/
├─ prompts/
│  └─ user-persona-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-user_persona.zip  ← packaged artifact
```

---

## FAQ
**Can I add demographics?**  
Only if they change product decisions. Otherwise, focus on behavior and goals.

**How many personas should we keep?**  
Two or three that the team actually references in planning/design.

**How do we avoid bias?**  
Include diverse research sources and show frequencies (e.g., “X of Y interviews”, “N of M survey responses”).

