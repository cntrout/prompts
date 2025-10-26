# Shorten Writing Prompt — README

**What this is**  
A compact, dependable **editing prompt** that turns long or wobbly text into something **short, clear, and on‑tone**. It preserves your meaning, trims filler, moves the point up front, and can match different tones. The original file is kept **verbatim** for traceability.

> Original: `prompts/shorten-writing-ORIGINAL.md`

---

## When to use it
- Tightening **emails**, **Slack posts**, **release notes**, **PRDs**, or **exec updates**.  
- You need a **short version** (one paragraph / three sentences / one sentence / specific word count).  
- You want to keep the **same tone** while removing hedging and redundancy.

---

## How it’s organized
1) **`<writing_inputs>`** — The only part you edit. Paste what you wrote, choose a **target length**, select a **tone**, and mark **what to preserve**.  
2) **`<editing_framework>`** — The step‑by‑step process the model follows (core message → cut → active voice → front‑load → produce the edit + change log + ultra‑short alt).  
3) **`<meta_guidance>`** — Handy before/after phrasing and the **50% rule** reminder.

Keep the framework text unchanged; just fill the `[]` fields in **`<writing_inputs>`**.

---

## Quick start
1. Open `prompts/shorten-writing-ORIGINAL.md`.  
2. Paste your draft under **PASTE WHAT YOU WROTE**.  
3. Choose a **Target length** (tick one, or specify `X words`).  
4. Set **Tone to maintain** (or “Match original”).  
5. Pick **What to preserve** (facts, asks, action items, or “Everything important”).  
6. Run the prompt. You’ll get: original vs new word counts, a tightened version, what changed, and an even shorter alternative.

---

## What each input means (and how to fill it)

- **PASTE WHAT YOU WROTE `[Your draft]`** — Paste the full text. If it’s an email thread, paste only **your** message unless you want the model to consider the thread tone.  
- **TARGET LENGTH** — Choose one format:  
  - `[ ] Half the length` — Good for drafts that are too wordy.  
  - `[ ] One paragraph` — Crisp update suitable for Slack/email.  
  - `[ ] 3 sentences` — Great for concise status or recap.  
  - `[ ] One sentence` — Subject line or TL;DR.  
  - `[ ] Specific: [X words]` — Force a hard cap (e.g., 75 words).  
- **TONE TO MAINTAIN** — Keep voice consistent with audience: **Professional**, **Casual/friendly**, **Direct/firm**, **Empathetic**, or **Match original**.  
- **WHAT TO PRESERVE** — Prioritize content to protect: **Key facts/numbers**, **Specific asks**, **Action items**, or **Everything important**.

---

## Input cheat‑sheet — realistic PM examples for **every `[]`**

Below are **three very different scenarios**. Each fills all the input brackets to show exactly how to use the template.

### Scenario A — Exec update via Slack (B2B SaaS)

**PASTE WHAT YOU WROTE:**  
`[Team, I wanted to quickly follow up on Saved Views. I think we’re in a good spot, but maybe we should probably consider moving the beta back a week if legal has concerns. We actually shipped pin‑to‑dashboard and the API endpoint is basically ready. Adoption is looking kind of promising with around fourteen pilot users creating at least one saved view so far. Let me know what you think.]`

**TARGET LENGTH:**  
- `[ ] Half the length`  
- `[x] One paragraph`  
- `[ ] 3 sentences`  
- `[ ] One sentence`  
- `[ ] Specific: [X words]`

**TONE TO MAINTAIN:**  
- `[x] Professional`  
- `[ ] Casual/friendly`  
- `[ ] Direct/firm`  
- `[ ] Empathetic`  
- `[ ] Match original`

**WHAT TO PRESERVE:**  
- `[x] Key facts/numbers`  
- `[ ] Specific asks`  
- `[ ] Action items`  
- `[x] Everything important (just shorter)`

---

### Scenario B — Customer email about a billing fix (Fintech)

**PASTE WHAT YOU WROTE:**  
`[Hi there—circling back to the duplicate charge issue. We’re still looking into it and we’ll get back to you soon with more details, but we wanted you to know that we’re taking it very seriously and doing everything we can. It would be great if you could possibly send the last four digits of the card so we can speed things up.]`

**TARGET LENGTH:**  
- `[ ] Half the length`  
- `[ ] One paragraph`  
- `[x] 3 sentences`  
- `[ ] One sentence`  
- `[ ] Specific: [X words]`

**TONE TO MAINTAIN:**  
- `[ ] Professional`  
- `[ ] Casual/friendly`  
- `[ ] Direct/firm`  
- `[x] Empathetic`  
- `[ ] Match original`

**WHAT TO PRESERVE:**  
- `[x] Specific asks`  
- `[ ] Action items`  
- `[x] Everything important (just shorter)`  
- `[ ] Key facts/numbers`

---

### Scenario C — PRD intro section (Marketplace)

**PASTE WHAT YOU WROTE:**  
`[This document intends to outline our future plans for Express Jobs and basically serve as a place to collect thoughts from everyone. We really want to improve the situation around last‑minute bookings because there’s a lot of frustration, and our plan is to maybe consider different ideas about how to implement an express fee.]`

**TARGET LENGTH:**  
- `[ ] Half the length`  
- `[ ] One paragraph`  
- `[ ] 3 sentences`  
- `[x] One sentence`  
- `[ ] Specific: [X words]`

**TONE TO MAINTAIN:**  
- `[x] Direct/firm`  
- `[ ] Professional`  
- `[ ] Casual/friendly`  
- `[ ] Empathetic`  
- `[ ] Match original`

**WHAT TO PRESERVE:**  
- `[ ] Key facts/numbers`  
- `[ ] Specific asks`  
- `[x] Action items`  
- `[x] Everything important (just shorter)`

---

## What the framework enforces (and why it works)

- **Core message first** → identifies the one thing the text must say.  
- **Ruthless cuts** → removes fillers (“just”, “really”, “maybe”), hedges, and redundancy.  
- **Active voice** → “The team decided” beats “A decision was made.”  
- **Front‑load the point** → answer first; details second.  
- **Change log** → shows items removed/simplified/reordered for quick review.  
- **Ultra‑short alt** → a TL;DR version if you need even less.

---

## Tips for great results
- If shortening a **thread**, paste only the bits you’re rewriting to avoid drift.  
- When specifying `[X words]`, add 10% slack for names/jargon.  
- For sensitive topics, choose **Empathetic** tone and keep **facts + action items**.  
- For execs, aim for **one paragraph** and start with the **decision or impact**.

---

## Repository layout

```
prompt-library-shorten_writing/
├─ prompts/
│  └─ shorten-writing-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-shorten_writing.zip  ← packaged artifact
```

---

## FAQ
**Can I ask it to rewrite for a different audience?**  
Yes—set Tone and Target length to fit (e.g., “Direct/firm” + “One paragraph” for execs).

**Will it change my meaning?**  
No—the **What to preserve** checklist protects critical content; the change log shows edits.

**What if I need bullet points?**  
Paste your draft as bullets; the framework will condense and keep bullets if that improves clarity.

