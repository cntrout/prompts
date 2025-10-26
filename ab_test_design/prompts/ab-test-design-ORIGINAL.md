

<ab_test_design>

<test_inputs>
WHAT YOU WANT TO TEST:
[Describe the change - new feature, UI change, algo tweak, etc.]

WHY YOU'RE TESTING IT:
- Hypothesis: [What you believe will happen]
- Expected impact: [Metric you think will improve]
- Risk: [What could go wrong if you ship to everyone]

YOUR PRODUCT CONTEXT:
- Daily/monthly active users: [Volume]
- Current baseline metric: [The metric you're trying to move]
- Existing conversion/engagement rate: [If relevant]
- How users are assigned: [Session, user ID, random]

CONSTRAINTS:
- Timeline: [How long can you run test]
- Traffic: [Can you split 50/50 or need different allocation]
- Technical: [Any limitations on what you can test]
</test_inputs>

<test_framework>

You design A/B tests that produce reliable results. Follow this analysis:

**STEP 1: Form a clear hypothesis**

Bad hypothesis: "New design will be better"
Good hypothesis: "Adding social proof to checkout will increase conversion rate from 5% to 6%"

**Hypothesis format:**
If we [change]
Then [metric] will [improve by X%]
Because [reasoning based on user behavior]


**Check:**
- Is it specific? (Not "improve," but "increase by X%")
- Is it measurable? (Clear metric)
- Is it testable? (Can you prove/disprove)
- Is the expected change realistic? (6% → 7% yes, 6% → 60% no)

**STEP 2: Choose primary metric carefully**

Your primary metric should be:
- **North Star adjacent:** Tied to what actually matters for business
- **Measurable quickly:** Can detect change in reasonable timeframe
- **Sensitive enough:** Will move if change works
- **Stable enough:** Not too noisy day-to-day

**Bad primary metrics:**
- Page views (vanity, doesn't show value)
- Time on site (could mean confused, not engaged)
- Clicks on button (metric hacking, doesn't show outcome)

**Good primary metrics:**
- Conversion rate (shows real outcome)
- Revenue per user (business impact)
- Feature adoption rate (engagement)
- Retention day 7 (long-term value)

**STEP 3: Define guardrail metrics**

These are metrics that should NOT get worse:

**Must not break:**
- Page load time
- Error rates
- User satisfaction (NPS)
- Core flows (login, checkout, etc.)

**Format:**
Primary metric: [Conversion rate]
Goal: Increase by [X%]
Guardrail metrics:
• Page load time: Must stay <2s
• Error rate: Must stay <1%
• Cart abandonment: Must not increase


**STEP 4: Calculate sample size**

You need enough users to detect the change:

**Required inputs:**
- Baseline rate: [Current metric value]
- Minimum detectable effect: [Smallest change you care about]
- Statistical power: [Usually 80%]
- Significance level: [Usually 95%]

**Rule of thumb calculations:**

For **conversion rate** changes:
- To detect 10% relative lift (5% → 5.5%): ~10,000 users per variant
- To detect 20% relative lift (5% → 6%): ~2,500 users per variant
- To detect 5% relative lift (5% → 5.25%): ~40,000 users per variant

For **engagement metrics** (sessions, clicks):
- Generally need less volume
- But more noise, so longer runtime

**Calculator formula:**
n = 2 × (Zα + Zβ)² × p × (1-p) / (MDE)²
Where:
• Zα = 1.96 (for 95% confidence)
• Zβ = 0.84 (for 80% power)
• p = baseline rate
• MDE = minimum detectable effect


**Then determine runtime:**
Days needed = Sample size needed / (Daily traffic × % allocated to test)


**STEP 5: Design variant carefully**

**Control (A):**
- Current experience
- No changes
- Baseline measurement

**Treatment (B):**
- ONE clear change
- Everything else identical
- Change is measurable

**Common mistakes:**
- Testing multiple changes at once (can't tell what caused effect)
- Making change too subtle (won't detect difference)
- Making change too different (not realistic to ship)

**STEP 6: Plan rollout & assignment**

**User assignment:**
- **By user ID:** Same user always sees same variant (better for logged-in products)
- **By session:** Each session could be different (okay for anonymous products)
- **By device:** Mobile vs desktop

**Traffic allocation:**
- **50/50:** Standard, maximum power
- **90/10:** If risky change, minimize exposure
- **33/33/33:** Testing 2 variants against control

**Rollout plan:**
- Start with 10% of traffic (canary)
- Monitor for 24 hours
- If stable, ramp to 50%
- If still good, full test

**STEP 7: Define decision criteria upfront**

**Ship if:**
- [ ] Primary metric improves by [X%] with 95% confidence
- [ ] Guardrails stay stable
- [ ] No major bugs reported
- [ ] Qualitative feedback is positive

**Don't ship if:**
- [ ] Primary metric neutral or negative
- [ ] Any guardrail breaks
- [ ] Major bugs or user complaints
- [ ] Confidence level <95%

**Inconclusive if:**
- [ ] Small positive movement but not statistically significant
- [ ] Then: Run longer OR redesign test

**STEP 8: Plan instrumentation**

**Events to track:**
test_exposure:
user_id: [ID]
variant: [A or B]
timestamp: [When]
[primary_metric_event]:
user_id: [ID]
variant: [A or B]
value: [Metric value]
timestamp: [When]


**Check before launch:**
- [ ] Events firing correctly
- [ ] Variant assignment is random
- [ ] No overlap with other tests
- [ ] Can filter by variant in analytics

</test_framework>

---

## A/B TEST DESIGN DOC

**Test Name:** [Descriptive name]
**Owner:** [Your name]
**Status:** [Draft / Ready to launch / Running / Complete]

---

### Hypothesis

**If we** [specific change]  
**Then** [primary metric] will [increase/decrease by X%]  
**Because** [reasoning about user behavior]

**Example:**
"If we add customer testimonials to the pricing page, then free-to-paid conversion will increase from 12% to 14% because social proof reduces purchase anxiety."

---

### The Change

**Control (A) - Current experience:**
[Description or screenshot]

**Treatment (B) - New experience:**
[Description or screenshot]

**What's different:**
- [Specific change 1]
- [Specific change 2]

**What stays the same:**
[Everything else]

---

### Metrics

**PRIMARY METRIC (Decision maker):**

**Metric:** [Name]  
**Current baseline:** [X%]  
**Target:** [Y%]  
**Minimum detectable effect:** [Z%]

**Why this metric:**
[Why this is the right thing to measure]

---

**GUARDRAIL METRICS (Must not break):**

| Metric | Current | Must stay above/below |
|--------|---------|----------------------|
| [Metric 1] | [Value] | [Threshold] |
| [Metric 2] | [Value] | [Threshold] |
| [Metric 3] | [Value] | [Threshold] |

**Why these guardrails:**
[What you're protecting against]

---

**SECONDARY METRICS (Understand impact):**
- [Metric 1]: [What we'll learn]
- [Metric 2]: [What we'll learn]

---

### Sample Size & Timeline

**Sample size needed per variant:** [X users]

**Calculation:**
- Baseline rate: [%]
- Target lift: [%]
- Statistical power: 80%
- Significance level: 95%

**Daily traffic:** [Y users/day]  
**Traffic allocation:** [Z% to test]  
**Users per day in test:** [Y × Z%]

**Days needed:** [X users ÷ (Y × Z%)] = [W days]

**Proposed timeline:**
- Start: [Date]
- End: [Date]
- Duration: [W days]

**If we need results faster:**
[Options: increase traffic %, accept lower power, larger MDE]

---

### Traffic Allocation

**Split:**
- Control (A): [50%]
- Treatment (B): [50%]

**Assignment method:**
- [ ] By user ID (consistent experience)
- [ ] By session (can vary per session)
- [ ] Other: [Specify]

**Rollout plan:**
- Day 1: Launch to [10%] of traffic
- Day 2: If stable, ramp to [50%]
- Day 3+: Full test at [50/50]

**Monitoring triggers:**
- Error rate >2% → pause test
- Crash rate up >50% → kill test
- Angry user feedback → investigate

---

### Decision Criteria

**SHIP TO 100% IF:**
- ✅ Primary metric improves by ≥[X%] with p<0.05
- ✅ All guardrails stable (within [Y%] of baseline)
- ✅ No major bugs or user complaints
- ✅ Test ran for full [W days]

**DON'T SHIP IF:**
- ❌ Primary metric flat or negative
- ❌ Any guardrail degrades >[Y%]
- ❌ Significant bugs or complaints
- ❌ Low confidence (p>0.05)

**INCONCLUSIVE IF:**
- ⚠️ Small positive movement but p>0.05
- **Then:** Run [X more days] OR redesign test

**No cherry-picking results:** Wait for full duration, don't stop early because it's winning.

---

### Instrumentation

**Events to implement:**

**Test exposure:**
experiment_viewed:
user_id: string
experiment_name: "test_name"
variant: "A" or "B"
timestamp: datetime


**Primary metric event:**
[event_name]:
user_id: string
variant: "A" or "B"
[metric_value]: number
timestamp: datetime


**Pre-launch checklist:**
- [ ] Events fire on staging
- [ ] Variant assignment is random (check logs)
- [ ] Can filter analytics by variant
- [ ] Guardrail metrics tracked
- [ ] No conflicts with other running tests

---

### Risks & Mitigation

**RISK 1: [Potential problem]**
- **Likelihood:** [High/Med/Low]
- **Impact:** [High/Med/Low]
- **Mitigation:** [What we'll do]
- **Kill switch:** [How to disable quickly]

**Example:**
"Risk: New checkout flow confuses users, increases abandonment  
Likelihood: Medium  
Impact: High (revenue loss)  
Mitigation: Monitor abandonment hourly, qualitative feedback survey  
Kill switch: Feature flag to revert to control"

---

**RISK 2: [Another risk]**
[Same format]

---

### User Experience Considerations

**Switching variants:**
- What happens if user assigned variant A yesterday sees variant B today?
- Plan: [Consistent assignment by user ID]

**Partial exposure:**
- What if user only sees variant on mobile, not desktop?
- Plan: [Accept, assignment is per-device]

**Existing users vs new users:**
- Does this change affect both equally?
- Plan: [Segment analysis by user age]

---

### Analysis Plan

**Primary analysis:**
- Compare [primary metric] between A and B
- Statistical test: [Two-sample t-test / Chi-square]
- Confidence level: 95%

**Segmentation to check:**
- [ ] New vs returning users
- [ ] Mobile vs desktop
- [ ] By geography
- [ ] By user cohort

**Questions to answer:**
1. Did primary metric move?
2. Did any guardrails break?
3. Are there segment differences?
4. Is qualitative feedback consistent with data?

**Dashboard:** [Link to live results]

---

### Rollback Plan

**If we need to kill test:**

**Trigger conditions:**
- [Specific condition 1]
- [Specific condition 2]

**How to rollback:**
1. [Step 1: Turn off feature flag]
2. [Step 2: Verify users see control]
3. [Step 3: Monitor for recovery]

**Communication:**
- Internal: [Slack #team-channel]
- Users: [If needed, what to say]

**Owner on-call:** [Name, contact]

---

### Launch Checklist

**BEFORE LAUNCH:**
- [ ] Hypothesis documented
- [ ] Metrics instrumented and tested
- [ ] Sample size calculated
- [ ] Decision criteria agreed
- [ ] Design/eng review complete
- [ ] QA tested both variants
- [ ] Feature flag configured
- [ ] Rollback plan documented
- [ ] Stakeholders aligned

**AT LAUNCH:**
- [ ] Start at 10% traffic
- [ ] Check events firing
- [ ] Check variant assignment random
- [ ] Monitor for first 2 hours
- [ ] Ramp to full traffic if stable

**DURING TEST:**
- [ ] Daily metrics check
- [ ] Weekly stakeholder update
- [ ] User feedback review
- [ ] Guardrail monitoring

**AT CONCLUSION:**
- [ ] Full statistical analysis
- [ ] Segment breakdowns
- [ ] Qualitative synthesis
- [ ] Decision made and documented
- [ ] Results shared with team

---

### Success Criteria Review

**Expected outcome:**
[What you think will happen]

**Best case:**
[If way better than expected]

**Worst case:**
[If it hurts metrics]

**Most likely:**
[Realistic expectation]

**We'll consider this test successful if:**
[Even if we don't ship, what will we learn?]

</ab_test_design>