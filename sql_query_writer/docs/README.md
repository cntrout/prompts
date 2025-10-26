# SQL Query Writer Prompt — README

**What this is**  
A lightweight, PM-friendly prompt that turns plain-English data questions into clear, annotated SQL (plus a plain-English explanation of results). It preserves a simple workflow: clarify the question → verify tables/columns/joins → write the query with inline comments → explain how to read the output. The original file is kept verbatim.

> Original prompt preserved at: `prompts/sql-query-writer-ORIGINAL.md`

---

## When to use it
- You need a **one-off query** to answer a product question fast (no full dashboard needed).
- You’re a PM/analyst who wants **correct joins and readable SQL**, not wizardry.
- You want **explainable outputs** teammates can trust and reuse.

---

## How the prompt is organized

1) **`<query_inputs>`** — You provide context here. These are the only fields you edit.  
2) **`<query_framework>`** — The step-by-step process and output wrapper (don’t change this).  
3) **`<meta_guidance>`** — Style tips, common patterns, and reminders (keep as-is).

> Do **not** edit the wording of the prompt itself—only fill in the `[]` fields in **`<query_inputs>`**.

---

## Quick start
1. Open `prompts/sql-query-writer-ORIGINAL.md`.  
2. Fill out **every** bracketed field in **`<query_inputs>`**.  
3. If you’re missing table/column info, include samples or a short schema blurb.  
4. Run the generated SQL in your warehouse, validate a few rows, then iterate.

---

## Input cheat sheet — examples for **every** `[]` in `<query_inputs>`

Below are **three distinct PM scenarios**. Use them as models for how to complete the inputs.

### Scenario A — Growth funnel drop-off (Checkout)
**WHAT DO YOU WANT TO KNOW: [Describe in plain English what you're trying to find out]**  
`What is the step-by-step conversion rate through the checkout funnel (view → add_to_cart → start_checkout → payment_success) for last week, broken down by device_type?`

**YOUR DATABASE: [Paste table names and columns, or just describe what tables you have]**  
```
Tables:
- events (user_id, event_name, event_time, device_type, session_id)
- orders (order_id, user_id, created_at, total_amount, status)

Notes:
- events.event_name values include: 'view_product', 'add_to_cart', 'start_checkout', 'payment_success'
- payment_success is also when an 'orders' row has status='paid'
- Warehouse: Postgres 14
- Date range: last full ISO week (Mon–Sun)
```

Optional extras:  
- Sample data: `events` example row → `(u123, 'start_checkout', '2025-10-13 10:42:00+00', 'mobile', 's456')`  
- Filters: `exclude device_type='crawler'`

---

### Scenario B — Retention and churn (SaaS cohort view)
**WHAT DO YOU WANT TO KNOW**  
`For users who signed up in September 2025, what is weekly retained_active_users for 8 weeks, and what percentage churned by week?`

**YOUR DATABASE**  
```
Tables:
- users (user_id, signup_at, plan, country)
- product_events (user_id, occurred_at, event_type)
- subscriptions (user_id, period_start, period_end, status)

Notes:
- Retained user definition: had ≥1 'session' event in a given week
- Database: BigQuery
- Cohort: signup_at between '2025-09-01' and '2025-09-30'
```

Optional extras:  
- Sample data: `product_events` row → `(u77, '2025-10-06 15:12:10 UTC', 'session')`

---

### Scenario C — Payments reliability (Issuer declines)
**WHAT DO YOU WANT TO KNOW**  
`What was the issuer decline rate by country and card_brand over the last 30 days, and which top 10 BINs had the highest decline rates?`

**YOUR DATABASE**  
```
Tables:
- payments (payment_id, created_at, user_id, amount, currency, country, card_brand, bin, status, decline_code)
- users (user_id, created_at, marketing_channel)

Notes:
- Decline definition: status='failed' AND decline_code IS NOT NULL
- Data source: Snowflake
- Date range: created_at >= current_date - interval '30 days'
```

Optional extras:  
- Filters: `exclude marketing_channel='sandbox'`

---

## What the framework enforces (so your query is trustworthy)

- **Clarify the question** first, then map **required data points**.  
- **Verify schema** (tables/columns/joins) before writing SQL.  
- Ship **well-commented SQL** that a PM or engineer can read next month.  
- Provide a **plain-English explanation** of exactly what the result returns—and how to tweak it.

---

## Tips & patterns (from the prompt’s meta_guidance)

- **Keep it simple**: one query that answers the question; split complex needs into smaller queries.  
- **Common patterns**:  
  - Counting: `COUNT(DISTINCT user_id)`  
  - Percentages: `100.0 * X / NULLIF(Y, 0)`  
  - Time buckets: `DATE_TRUNC('day', ts)` / `DATE_TRUNC('week', ts)`  
  - Cohorts: group by `DATE_TRUNC('week', signup_at)`  
- **Explain results**: Include what each column means and how to validate with a quick spot-check.

---

## Repository layout

```
prompt-library-sql_query_writer/
├─ prompts/
│  └─ sql-query-writer-ORIGINAL.md
├─ docs/
│  └─ README.md
└─ prompt-library-sql_query_writer.zip  ← export artifact
```

---

## FAQ
**Can I change the framework or meta-guidance?**  
Keep the `-ORIGINAL` file immutable. If you need a version for your org (naming conventions, safety checks), copy it and edit your copy.

**What if I don’t know the exact schema?**  
Paste what you do know (table names, column guesses, or a short “shape” of the data). The prompt will ask targeted questions to fill gaps.

**How do I validate the query?**  
Run with a `LIMIT` first, check a few rows against your product UI or logs, then remove the limit and add final filters.
