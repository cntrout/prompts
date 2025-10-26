

<experiment_readout>

<experiment_inputs>
PASTE YOUR DATA:
[Raw results - control vs treatment metrics, or describe what you have]

THE TEST:
- What you tested: [Feature/change]
- Hypothesis: [What you expected]
- Primary metric: [What you measured]
- Duration: [How long]
- Sample size: [Users per variant]

YOUR DECISION CRITERIA:
[What was agreed upfront - ship if X, don't ship if Y]
</experiment_inputs>

<readout_framework>

You analyze experiments to make data-driven decisions. Your process:

**STEP 1: Validate the experiment**

**Before analyzing results, check:**
- Did test run for planned duration?
- Was sample size sufficient?
- Was traffic split as expected (50/50)?
- Any implementation bugs?
- Any external factors (holidays, outages, campaigns)?

**Red flags that invalidate results:**
- Imbalanced traffic split
- Test stopped early because "it was winning"
- Major bug discovered in variant
- External event during test (site down, viral moment, etc.)

**If experiment is invalid → don't ship, re-run test**

**STEP 2: Analyze primary metric**

**The question:**
Did treatment move primary metric vs control?

**Statistical test:**
- Difference: [X%]
- P-value: [Number]
- Confidence interval: [Range]
- Statistical significance: [Yes if p<0.05]

**Practical significance:**
- Is difference big enough to matter?
- Does it meet your MDE (minimum detectable effect)?
- Business impact: [Calculate actual value]

**Common pitfall:**
"Statistically significant" ≠ "big enough to care about"
A 0.1% improvement might be significant but not worth the complexity.

**STEP 3: Check guardrail metrics**

**Did anything break?**

For each guardrail metric:
- Did it stay stable? (within ±X%)
- Did it improve? (bonus)
- Did it degrade? (concern)

**If guardrails broke:**
Even if primary metric improved, might not ship if:
- User experience degraded
- Revenue decreased
- Key flow broke
- NPS dropped

**STEP 4: Segment analysis**

**Did it work for everyone or just some users?**

Segment by:
- New vs returning users
- Mobile vs desktop
- Geography
- User cohort
- Product tier

**Patterns to look for:**
- Works great for segment A, hurts segment B
- Only works for new users (or only returning)
- Platform-specific (desktop yes, mobile no)

**If segmented results:**
Consider shipping to only winning segments.

**STEP 5: Look for surprises**

**Secondary metrics:**
Did anything unexpected move?

**Qualitative feedback:**
- User comments
- Support tickets
- Sales feedback
- Social sentiment

**Sometimes data says "ship" but users say "this is confusing"**
→ Investigate the disconnect

**STEP 6: Calculate business impact**

**If you ship to 100%:**

**Impact calculation:**
[Metric lift %] × [baseline volume] × [value per conversion]
= [Annual impact]


**Example:**
5% conversion lift × 10K users/mo × $100 LTV
= 500 more conversions/mo × $100
= $50K/mo = $600K/year

**Compare to:**
- Cost to build/maintain
- Opportunity cost (what else could team build)

**STEP 7: Make recommendation**

**Framework:**

**Ship if:**
- Primary metric improved (statistically + practically significant)
- Guardrails stable
- Positive or neutral qualitative feedback
- Business impact > cost

**Don't ship if:**
- Primary metric flat or negative
- Guardrails broke
- Negative qualitative feedback
- Not worth the complexity

**Iterate if:**
- Results promising but mixed
- Some segments won, some lost
- Qualitative concerns despite data win

**Re-test if:**
- Results inconclusive (not enough data)
- External factors muddied results
- Implementation issues

Now analyze the provided experiment data and make a clear recommendation.

</readout_framework>

---

## Example Experiment Readout

*(Structure will vary based on the experiment, but here's a typical flow)*

### Decision Summary

**Recommendation:** [SHIP / DON'T SHIP / ITERATE / RE-TEST]

**One-line rationale:**
[Primary metric moved X%, guardrails stable, qualitative positive - ship it]

**If shipping:**
- To whom: [100% / specific segments / gradual rollout]
- When: [Timeline]
- With what: [Any changes based on learnings]

---

### Experiment Overview

**Tested:** [Description]  
**Hypothesis:** [Expected outcome]  
**Duration:** [Dates]  
**Sample size:** [N users per variant]  
**Traffic split:** [Actual split achieved]

**Test validity:** ✅ Valid / ⚠️ Concerns / ❌ Invalid
[Note any issues]

---

### Primary Metric Results

**Metric:** [Name]

**Control:** [X%]  
**Treatment:** [Y%]  
**Lift:** [+Z%] (absolute: [A percentage points])

**Statistical significance:** [Yes/No]  
**P-value:** [Number]  
**Confidence interval:** [Range]

**Practical significance:**
[Is this big enough to matter? Business impact calculation]

**Interpretation:**
[What this means in plain language]

---

### Guardrail Metrics

| Metric | Control | Treatment | Change | Status |
|--------|---------|-----------|--------|--------|
| [Metric 1] | [X] | [Y] | [±Z%] | [✅/⚠️/❌] |
| [Metric 2] | [A] | [B] | [±C%] | [Status] |

**Issues:** [Any guardrails that broke]

---

### Segment Analysis

**By [segment type]:**

[Show results for key segments - might be table, might be bullet points, adapt to data]

**Key finding:**
[Did it work better for some segments?]

**Implication:**
[Should we ship to all users or just certain segments?]

---

### Unexpected Findings

**What surprised us:**
[Things that moved unexpectedly]

**Qualitative signals:**
[User feedback, support tickets, sales comments]

**Consistency check:**
[Do data and qualitative align or conflict?]

---

### Business Impact

**If we ship to 100%:**

[Calculate actual impact in revenue, users, or other business metric]

**ROI:**
[Impact vs cost to build/maintain]

---

### Recommendation Details

**Why [ship/don't ship]:**
[Detailed reasoning]

**Confidence level:** [High/Medium/Low]

**Risks:**
[What could still go wrong]

**Next steps:**
[Specific actions]

</experiment_readout>