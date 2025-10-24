# Claude Blog Post Writer Prompt

This repository packages a reusable Claude prompt for writing high‑quality blog posts end‑to‑end. It includes:
- The original prompt (unchanged) for reuse.
- A newcomer‑friendly README explaining purpose, sections, and best practices.
- Three **fully filled examples** from the perspective of a SaaS Product Manager at Stripe.

> **Note:** The original file name has been preserved with `-ORIGINAL` appended per instructions.

---

## What this prompt is for

Use it to generate blog posts that people actually read: clear headline, tight intro, scannable body, and crisp conclusion. It also bundles **SEO guidance** and **ready‑made templates** (Product Launch, How‑To, Thought Leadership, Customer Story). It’s designed so a non‑technical teammate can fill inputs and get a publishable draft.

## Anatomy of the prompt

The prompt has four big parts. You don’t need to edit the prompt itself—just fill the input boxes and Claude does the rest.

1) **`<post_inputs>` — Your brief**  
   You specify:
   - **TOPIC**: what the post is about.  
   - **PURPOSE**: choose one intent (launch, how‑to, thought leadership, company update, customer story).  
   - **AUDIENCE**: who will read it, what they care about, and their technical level.  
   - **YOUR ANGLE**: your unique POV and the hook for why this matters.  
   - **TARGET LENGTH**: short, medium, or long.  
   - **SEO KEYWORDS (optional)**: terms you want to rank for.

2) **`<post_framework>` — Guardrails & structure**  
   - **Headline rules:** specific benefit, numbers or “how to”, under 60 chars.  
   - **Intro:** 3 sentences (problem → “why now” → what they’ll learn).  
   - **Body:** subheadings every 2‑3 paragraphs, real examples, actionable takeaways.  
   - **Conclusion:** recap + clear next step/CTA.  
   - **SEO optimization block:** meta description, suggested images, internal links.

3) **`<post_templates>` — Four battle‑tested outlines**  
   - **Product Launch** (what, why, how, who, what’s next).  
   - **How‑To** (step‑by‑step + common mistakes).  
   - **Thought Leadership** (challenge conventional wisdom → better way → implications).  
   - **Customer Story** (challenge → solution → results → lessons).

4) **`<meta_guidance>` — Writing best practices**  
   - Conversational tone, short sentences, active voice.  
   - Show, don’t tell; use examples/data/screenshots.  
   - Make it scannable (subheads, bullets, bold).  
   - Hook early, end strong.  
   - SEO basics (keyword placement, meta, alt text).

## How to use it (quick start)

1. Open `prompts/blog_post_writer-ORIGINAL.md` in Claude.
2. Fill in the fields inside **`<post_inputs>`**. Keep everything else intact.  
3. In **`YOUR BLOG POST`**, you can pre‑fill sections (headline, intro, body points, conclusion) or let Claude do it.  
4. Optionally select a template in **`<post_templates>`** and mirror its sections in **`YOUR BLOG POST`**.  
5. Copy the generated draft into your CMS, add screenshots, run a quick SEO check, and publish.

### Do’s & Don’ts
**Do**
- Be concrete about audience pain points and desired outcome.  
- Add real examples and numbers (authorization rates, latency, ROI).  
- Write the meta description last—after the post is set.

**Don’t**
- Change or delete prompt sections.  
- Cram multiple purposes into one post.  
- Over‑optimize for keywords at the expense of clarity.

## Example files

Inside `/examples` you’ll find three filled prompts from a Stripe PM’s day‑to‑day:
- `example-1-product-launch.md` — Launching a **Real‑Time Acceptance Insights** dashboard.
- `example-2-how-to.md` — How to **cut chargebacks by ~30%** in 30 days with Radar.
- `example-3-customer-story.md` — How **QuickCart** raised auth rates by **2.4 pp** using **network tokens**.

Each file keeps the original prompt structure and fills in the fields—ready to paste into Claude.

## Suggested repo layout

```
claude-blog-post-writer/
├── README.md
├── prompts/
│   └── blog_post_writer-ORIGINAL.md
└── examples/
    ├── example-1-product-launch.md
    ├── example-2-how-to.md
    └── example-3-customer-story.md
```

---

## Tips for adapting to your context

- Swap “Stripe” specifics for your product’s metrics and customer language.  
- Keep the **purpose** singular per post. If you need both “launch” and “how‑to,” publish two linked posts.  
- For SEO, target one primary keyword, and a couple secondary semantically related terms.
- Start your first draft short (800–1,200 words). Grow only if substance demands it.

---

## License

MIT (or align to your org’s standard).
