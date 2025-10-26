# Message Response Prompt — README

**What this is**  
A compact, reliable prompt that turns messy email threads into **clear, decisive replies**. It forces BLUF (Bottom Line Up Front), picks the right response type, and outputs a short, tone-matched email plus alternative versions. The original prompt is preserved **verbatim** in this package for traceability.

> Original file: `prompts/message-response-ORIGINAL.md`

---

## When to use this
- You’ve got a long, fuzzy email and need a **tight response** in minutes.  
- You want help **saying no**, **making a call**, or **asking for something** clearly.  
- You’re replying to **execs, customers, or partners** and tone matters.

---

## How the prompt is organized

1. **`<email_inputs>`** — _Only part you edit._ Paste the thread and answer 5 quick context questions (plus optional context).  
2. **`<response_framework>`** — The coaching workflow: Decode → Determine type → Structure the reply → Patterns → Tone.  
3. **`<quality_check>`** — A final checklist (clear, complete, concise).  
4. **`<meta_wisdom>`** — The BLUF rule, tone calibration, and the “confidence edit.”

Keep the framework text unchanged; only fill the bracketed fields in **`<email_inputs>`**.

---

## Quick start
1) Open `prompts/message-response-ORIGINAL.md`.  
2) Paste the **full email thread** and complete the 5 context bullets.  
3) (Optional) Add related docs/Slack links and/or your rough draft.  
4) Run the prompt → copy the **Recommended Response**. Use alt versions if needed.

---

## Input cheat-sheet — realistic PM examples for **every `[]`** in `<email_inputs>`

Below are **three very different scenarios**. Each shows copy-pasteable entries for all bracketed fields.

### Scenario A — Sales asks for a roadmap commitment to save a deal (B2B SaaS)

**PASTE THE EMAIL YOU NEED TO RESPOND TO — `[Full email thread]`**  
> AE: “Prospect needs **Feature X** this quarter or we’ll lose the deal. Can we commit to Q4? Also need a slide by tomorrow.”

**YOUR CONTEXT**  
1) Who is this from? → `[customer-facing sales rep (Account Executive)]`  
2) What do they want? → `[a firm delivery commitment and a slide to share]`  
3) What's your relationship? → `[internal peer; we collaborate often]`  
4) Urgency level? → `[same-day reply; draft slide by tomorrow 12:00]`  
5) Tone needed? → `[direct and supportive; no over-promising]`

**OPTIONAL**  
- Related context: `[Feature X is adjacent to “Saved Views”; eng sizing not done; legal risk if we commit]`  
- Your initial draft: `[“We’ll try for Q4.” (too vague)]`

---

### Scenario B — Customer escalation about a billing bug (Fintech)

**PASTE THE EMAIL — `[Full email thread]`**  
> Customer Ops: “Enterprise client saw duplicate charges. They want explanation + fix timeline. Execs copied.”

**YOUR CONTEXT**  
1) From? → `[customer (enterprise finance lead) via our support manager]`  
2) Want? → `[root cause summary, confirmation of refunds, and precise ETA]`  
3) Relationship? → `[external customer; high-revenue account]`  
4) Urgency? → `[respond within 60 minutes]`  
5) Tone? → `[apologetic but confident; solution-oriented]`

**OPTIONAL**  
- Related: `[Incident ticket INC-2041; Stripe dashboard links; draft refund CSV]`  
- Initial draft: `[Long apology paragraph with no dates (not good)]`

---

### Scenario C — VP asks for a decision between two launch plans (Internal exec)

**PASTE THE EMAIL — `[Full email thread]`**  
> VP Product: “Option A (big-bang) vs Option B (phased). Which do you recommend? Decide today.”

**YOUR CONTEXT**  
1) From? → `[exec/boss]`  
2) Want? → `[a decision and 2-line rationale]`  
3) Relationship? → `[manager]`  
4) Urgency? → `[respond in 15 minutes]`  
5) Tone? → `[concise, confident]`

**OPTIONAL**  
- Related: `[Risk doc link; experiment results; rollout constraints]`  
- Initial draft: `[Leaning B because lower risk; can outline phases.]`

---

## What the framework enforces (and why it works)

- **Decode → Determine type**: identify whether the sender needs a **decision**, **information**, **status**, or **escalation** response.  
- **BLUF structure**: first sentence = answer/action; then 1–2 lines of context; finish with **next steps** and **dates/owners**.  
- **Patterns library**: reusable structures for saying **no**, giving **status**, **deciding**, **asking**, and **apologizing/recovering**.  
- **Tone calibration**: choose **formal/casual/apologetic/direct**, remove weakeners (“just”, “maybe”).  
- **Quality check**: confirms the email is **clear, complete, concise** before you send.

---

## Tips to get great results
- Copy the **entire** thread so the model catches tone and politics.  
- If you’re stuck, paste your messy **draft**—the prompt will tighten it.  
- Always end with a **specific next step** with an owner and date.  
- Keep replies **3–5 sentences** unless legal/sensitive.

---

## Repository layout

```
prompt-library-message_response/
├─ prompts/
│  └─ message-response-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-message_response.zip  ← packaged artifact
```

---

## FAQ
**Should I rewrite the framework?**  
No—keep it stable so responses are consistent. Change only the inputs.

**What if I’m unsure of the response type?**  
Pick the closest, write the BLUF answer, and ask a **single clarifying question** in next steps.

**Can it draft subject lines?**  
Yes—use the “Subject line” field in the final output if you’re starting a new thread or need to reframe.

