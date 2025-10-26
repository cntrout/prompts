# Blog Post Writer Prompt — README

**Purpose**  
A reusable prompt for writing blog posts your audience actually reads. It standardizes inputs (topic, audience, angle, SEO), gives you a clear structure (headline → intro → body → conclusion), and includes four handy templates (Launch, How‑To, Thought Leadership, Customer Story). The original prompt is preserved **verbatim**.

> Original file: `prompts/blog_post_writer-ORIGINAL.md`

---

## When to use this
- **Product/feature launch** posts that need to be crisp and benefit‑led  
- **Educational how‑to** guides that readers can scan and apply fast  
- **Opinionated/POV** pieces that challenge common wisdom  
- **Customer stories/case studies** with real metrics and quotes

---

## How it’s organized

1. **`<post_inputs>`** — You fill in the blanks. These are the only fields you edit.  
2. **`<post_framework>`** — A universal structure that keeps posts skimmable.  
3. **`<post_templates>`** — Four ready-made patterns for common post types.  
4. **`<meta_guidance>`** — Style, scannability, and SEO best practices.

> Don’t alter the prompt wording—only provide values inside the `[]` fields in **`<post_inputs>`**.

---

## Quick start
1) Open `prompts/blog_post_writer-ORIGINAL.md`.  
2) Fill out the `[]` fields in **`<post_inputs>`** (see examples below).  
3) Choose a template in **`<post_templates>`** or use the generic framework.  
4) Generate a draft. Tighten the headline, verify examples, and add screenshots before publishing.

---

## Input cheat sheet (real PM examples for **every** `[]` in `<post_inputs>`)

Below are **three distinct scenarios** to show how a PM might fill the inputs. Pick one as a blueprint and adapt.

### Scenario A — Product Launch (Billing/Fintech)
**TOPIC:**  
`Launching Usage‑Based Pricing in Stripe Billing`

**PURPOSE (select one):**  
`[x] Announce product/feature`

**AUDIENCE**  
- Who’s reading: `Prospects`  
- What they care about: `Monetizing new pricing models without rebuilding billing or metering`  
- Technical level: `Somewhat technical`

**YOUR ANGLE**  
- What’s your unique take: `Metering + invoicing must stay in lockstep or usage pricing backfires`  
- Why should they care: `Faster time‑to‑revenue with fewer billing edge cases`

**TARGET LENGTH:**  
`[x] Medium (800–1500 words)`

**SEO KEYWORDS (optional):**  
`usage based pricing, billing api, stripe billing, metering`

---

### Scenario B — How‑To (Conversion Optimization)
**TOPIC:**  
`Reduce Checkout Drop‑Off with One‑Click Address Validation`

**PURPOSE (select one):**  
`[x] Educational/how-to`

**AUDIENCE**  
- Who’s reading: `Customers`  
- What they care about: `Lower cart abandonment with minimal engineering lift`  
- Technical level: `Non-technical`

**YOUR ANGLE**  
- What’s your unique take: `Micro‑frictions at address capture drive outsized abandonment; remove them with auto‑validation`  
- Why should they care: `2–5% conversion lift within days`

**TARGET LENGTH:**  
`[x] Short (500–800 words)`

**SEO KEYWORDS (optional):**  
`checkout conversion, address validation, reduce cart abandonment, ecommerce ux`

---

### Scenario C — Customer Story (Payments Reliability)
**TOPIC:**  
`How BrewBox Raised Approval Rates by 3.8% with Network‑Level Smart Retries`

**PURPOSE (select one):**  
`[x] Customer story`

**AUDIENCE**  
- Who’s reading: `Industry`  
- What they care about: `Authorization rates, fraud losses, and operational overhead`  
- Technical level: `Very technical`

**YOUR ANGLE**  
- What’s your unique take: `Small approval wins compound at scale—network‑level retries outperform manual rules`  
- Why should they care: `Each basis point can mean millions in recovered revenue`

**TARGET LENGTH:**  
`[x] Long (1500–3000 words)`

**SEO KEYWORDS (optional):**  
`payment authorization rates, smart retries, payment success, issuer optimization`

---

## What the framework enforces
- **Headline** — Promise a concrete benefit; keep it under ~60 characters where possible.  
- **Intro (3 sentences)** — Problem → why it matters now → what they’ll learn.  
- **Body** — Scannable sections with subheads every 2–3 paragraphs; **examples over theory**; **actionable takeaways**.  
- **Conclusion** — Recap, clear next step, and CTA.  
- **SEO basics** — Headline + first paragraph keyword, natural usage 3–5×, meta description, image alt text.

---

## Tips for stronger posts
- Choose **one** primary audience and **one** purpose; if you have two, write two posts.  
- Lead with **outcomes** and **specifics** (numbers, screenshots, quotes).  
- If readers only skim subheads and takeaways, they should still get the gist.  
- End with a **single, unambiguous CTA** (start trial, talk to sales, view docs).

---

## Repo layout

```
prompt-library-blog_post_writer-v2/
├─ prompts/
│  └─ blog_post_writer-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-blog_post_writer-v2.zip  ← export artifact
```

---

## FAQ
**Can I change the templates?**  
Keep the `-ORIGINAL` file immutable. If you need variants, copy it and edit your copy.

**How do I handle brand voice and legal reviews?**  
Add a short brand/voice line **before** generation (e.g., “Write in a clear, trustworthy voice with light technical depth”) and route drafts through your standard review path.

**Where do visuals go?**  
Use the “Suggested images” in the SEO section to plan assets early; drop in final screenshots before publishing.

