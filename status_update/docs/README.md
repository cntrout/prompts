# Status Update Prompt — README

**What this is**  
A practical prompt that turns your project updates into **short, scannable, action-oriented** status notes that busy people actually read. It standardizes audience-based formats, forces BLUF (status first), and ends with clear **asks**. The original file is preserved **verbatim**.

> Original: `prompts/status-update-ORIGINAL.md`

---

## When to use it
- Weekly/biweekly/monthly **project updates** to your team, stakeholders, or execs.  
- Pre-standup or pre-read before a steering meeting.  
- Anytime a project changes color (**Green → Yellow → Red**) and you need to notify fast.

---

## How the prompt is organized
1) **`<update_inputs>`** — *The only part you edit.* You specify the project, audience, period, status color, wins, next, risks, and asks (plus optional uploads).  
2) **`<update_framework>`** — Guidance on **format by audience**, a **universal template**, and detailed instructions for each section.  
3) **`<quality_check>`** — A quick list to ensure your update is scannable, honest, and actionable.  
4) **`<meta_wisdom>`** — Practical advice on frequency, color-coding, and making real asks.

Keep the framework text unchanged; just fill the fields.

---

## Quick start
1. Open `prompts/status-update-ORIGINAL.md`.  
2. Fill every field in **`<update_inputs>`** (see the examples below).  
3. Use the **Universal Template** in Part 2 to draft your update.  
4. Run the prompt and copy the **Ready to Send** version (plus a shorter/longer variant if needed).

---

## What each section means (at a glance)

- **Overall status (Green/Yellow/Red):** Honest health signal. Don’t hide issues.  
- **One‑sentence status line:** BLUF. “What’s the headline right now?”  
- **Wins / Progress:** Shipped items, decisions, and impact (numbers if possible).  
- **Next / Upcoming:** 3–5 items with dates.  
- **Risks / Blockers:** Top 1–3 with severity + mitigation.  
- **Asks / Needs:** Who needs to do what, by when, and why it matters.

The framework also provides audience-specific **length** and **tone** guidance.

---

## Input cheat‑sheet — realistic PM examples for every field in `<update_inputs>`

Below are **three very different product contexts**. Each shows exactly what to put into the `[]` placeholders of the **input section** and also demonstrates the optional audience/format fields inside the framework.

### Scenario A — B2B SaaS: “Saved Views” MVP (Team weekly)

**WHAT YOU'RE UPDATING ON**  
1) Project/initiative name → `[Saved Views MVP]`  
2) Audience → `[team]`  
3) Frequency → `[weekly]`  
4) Period covered → `[this sprint: Oct 13–Oct 26]`

**YOUR STATUS**  
5) Overall status → `[Green]`  
6) Key accomplishments →  
   `[Shipped pin-to-dashboard; Closed design on multi-select filters; Finalized event schema; 14 pilot users created ≥1 Saved View]`  
7) What’s next →  
   `[Enable sharing to workspace; Instrument adoption funnel; Prep rollout checklist]`  
8) Blockers/risks →  
   `[Query builder edge cases on nested filters; Designer at 50% capacity]`  
9) What you need →  
   `[1 backend for 2 days to finish audit logs; Pilot list from CS by Wednesday]`

**(Optional uploads)** → `[Mixpanel retention chart PNG, design link, pilot feedback doc]`

**Framework audience & format**  
Your audience → `[Team]` • Format to use → `[Detailed]`

**Status line** → `[🟢 On track: Saved Views MVP set for Nov 12 beta]`

---

### Scenario B — E‑commerce: Address Validation (Stakeholder biweekly)

**WHAT YOU'RE UPDATING ON**  
1) Project/initiative name → `[One‑click Address Validation]`  
2) Audience → `[stakeholders]`  
3) Frequency → `[biweekly]`  
4) Period covered → `[this fortnight: Oct 1–Oct 14]`

**YOUR STATUS**  
5) Overall status → `[Yellow]`  
6) Key accomplishments →  
   `[Integrated USPS + Google APIs; Fixed mobile address parsing; Won security sign‑off]`  
7) What’s next →  
   `[Ramp to 25% traffic; Post‑integration latency test; Draft A/B experiment plan]`  
8) Blockers/risks →  
   `[API timeouts spiking to 4%; Legal review of data retention terms pending]`  
9) What you need →  
   `[Decision on fallback behavior by Oct 29; Approval to extend QA by 3 days]`

**(Optional uploads)** → `[Funnel screenshot, latency dashboard, legal ticket link]`

**Framework audience & format**  
Your audience → `[Stakeholders]` • Format to use → `[Medium]`

**Status line** → `[🟡 Slight risk: latency spikes; mitigation in progress—beta still targeted for Nov 5]`

---

### Scenario C — Fintech: Smart Retries (Exec monthly)

**WHAT YOU'RE UPDATING ON**  
1) Project/initiative name → `[Smart Retries (issuer‑aware)]`  
2) Audience → `[execs]`  
3) Frequency → `[monthly]`  
4) Period covered → `[October]`

**YOUR STATUS**  
5) Overall status → `[Red]`  
6) Key accomplishments →  
   `[Completed risk review; Deployed sandbox with two issuers; Drafted rollout gates]`  
7) What’s next →  
   `[Finalize BIN window rules; Expand pilot to top‑5 merchants; Define chargeback guardrails]`  
8) Blockers/risks →  
   `[Legal review outstanding 3 weeks; Elevated dispute rate in one pilot cohort; SDK adoption slower than planned]`  
9) What you need →  
   `[VP Legal approval by Nov 4; OK to add a contract engineer for 6 weeks; Merchant introductions from BD]`

**(Optional uploads)** → `[Issuer performance spreadsheet, dispute cohort analysis, SDK adoption chart]`

**Framework audience & format**  
Your audience → `[Execs]` • Format to use → `[Executive]`

**Status line** → `[🔴 Blocked on legal: launch date pending; pilot expansion paused until approval]`

---

## Formatting & length guidelines (from the framework)
- Team updates: **200–400 words**; Stakeholders: **150–250**; Execs: **≤100**.  
- Use **emojis/symbols**, **bold** keywords, **bullets**, and **whitespace** so it’s skimmable.  
- Lead with **status color + one‑liner**. Make **asks** explicit (owner + date).

---

## Repository layout

```
prompt-library-status_update/
├─ prompts/
│  └─ status-update-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-status_update.zip  ← packaged artifact
```

---

## FAQ
**What if I don’t have numbers yet?**  
Use directional statements and add dates for when metrics will be available.

**Can I share the same update to multiple audiences?**  
Trim to fit each audience’s template—do not send the team version to execs.

**How honest should I be with color?**  
Err on the side of **Yellow/Red** when warranted; trust rises when risks are explicit.

