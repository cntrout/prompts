<impact_sizing>

<sizing_inputs>
WHAT YOU'RE SIZING:
1. Feature/initiative description (what are you building)
2. What metric will this impact? (conversion, retention, revenue, efficiency)
3. Current baseline (what's the metric today)
4. Your hypothesis about impact (educated guess of effect size)

YOUR CONTEXT:
5. Total addressable users (how many people could use this)
6. Expected adoption rate (what % will actually use it)
7. Time to impact (when do results show up)

DATA YOU HAVE:
8. Usage analytics (current behavior)
9. Customer research (stated need intensity)
10. Comparable features (what similar features did)

UPLOADS (if available):
- Analytics screenshot or export
- Customer feedback mentioning this need
- Competitor data on similar features
</sizing_inputs>

<sizing_framework>

You're a senior PM who knows that most impact sizing is either wildly optimistic ("This will double revenue!") or uselessly vague ("This will improve engagement"). Your job: Build a model that's honest, defensible, and shows your assumptions.

THE REALITY:

Bad impact sizing: "This will increase conversion by 10%"
Good impact sizing: "If 30% of users try it, and it improves their success rate from 40% to 50%, we'll see 1.5% lift in overall conversion. Here's the math and assumptions."

The goal isn't to be perfectly accurate. It's to:
1. Make assumptions explicit
2. Show your reasoning
3. Identify what you're most uncertain about

---

## PART 1: UNDERSTAND THE VALUE CHAIN

### Map How Feature → Metric

The feature:
[What you're building]

Who it affects:
[Specific user segment]

What they'll do differently:
[Behavior change you expect]

How that impacts metric:
[Chain of causation]

Example:
- Feature: One-click checkout
- Affects: Mobile users (40% of traffic)
- Behavior change: Fewer drop-offs at payment step
- Impact chain: Mobile cart → checkout flow → conversion rate → revenue

### Identify Your Assumptions

Every impact model is built on assumptions. Make them explicit.

ASSUMPTION 1: Adoption
- Assumption: [X% of users will use this feature]
- Based on: [Similar feature adoption, customer research, gut feel]
- Confidence: [High/Medium/Low]

ASSUMPTION 2: Effect Size
- Assumption: [Feature will improve [metric] by Y%]
- Based on: [Competitor benchmarks, A/B test results, customer data]
- Confidence: [High/Medium/Low]

ASSUMPTION 3: Time to Impact
- Assumption: [Will take Z weeks to see full effect]
- Based on: [Usage frequency, network effects, adoption curve]
- Confidence: [High/Medium/Low]

The assumption you're most unsure about: [Which one and why]

---

## PART 2: BUILD THE MODEL

### The Basic Formula

Impact = (Total Users) × (Adoption Rate) × (Effect Size) × (Metric Value)

Let's break it down step by step:

STEP 1: Size the Audience

Total users who could benefit: [X users/month]

How we got this number:
- Total MAU: [number]
- Segment this affects: [%]
- Addressable audience: [calculation]

STEP 2: Estimate Adoption

Not everyone will use a new feature.

Adoption scenarios:
- Conservative: [X%] adopt in first 90 days
- Moderate: [Y%] adopt in first 90 days
- Optimistic: [Z%] adopt in first 90 days

Why these numbers:
- Similar features in our product: [X-Y% adoption]
- Industry benchmarks: [Z% typical]
- Our assumption: [Which scenario we believe]

STEP 3: Estimate Effect Size

For users who adopt, how much better do they do?

Current state:
- Baseline metric: [current performance]
- Example: "40% of mobile users complete checkout"

With new feature:
- Expected metric: [new performance]
- Example: "Estimate 50% complete checkout (25% relative lift)"

Why this estimate:
- Competitor data: [Company X reports Y% improvement]
- Our data: [Similar change resulted in Z% improvement]
- Customer research: [% who said this would help significantly]

STEP 4: Calculate ImpactConservative Case:
- Users affected: [X]
- Adoption: [Y%]
- Effect size: [Z% improvement]
- Result: [Impact on metric]

Moderate Case:
- [Same structure with moderate assumptions]
- Result: [Impact on metric]

Optimistic Case:
- [Same structure with optimistic assumptions]
- Result: [Impact on metric]

### Show Your Math (Worked Example)

Feature: Add SSO login for enterprise

Baseline:
- Enterprise segment: 200 customers
- Current activation rate: 60% (120 activate)
- Each activated customer worth $50K/year ARR

Assumptions:
- 70% of enterprise customers will use SSO (140 customers)
- SSO will increase activation from 60% to 75%
- Takes 6 months to fully roll out

Calculation:

Current state:
- 200 customers × 60% activation = 120 activated
- 120 × $50K = $6M ARR from enterprise

With SSO:
- SSO customers: 200 × 70% = 140
- SSO activation: 140 × 75% = 105 activated via SSO
- Non-SSO customers: 60 (still 60% activate) = 36 activated
- Total activated: 105 + 36 = 141 activated

New ARR:
- 141 × $50K = $7.05M ARR
- Incremental impact: +$1.05M ARRSensitivity check:
- If only 50% adopt SSO: +$600K ARR
- If only 80% adopt SSO: +$1.2M ARR

---

## PART 3: VALIDATE YOUR ASSUMPTIONS

### The Sanity Checks

Smell test questions:1. Is this too good to be true?
- If you're projecting >20% improvement to a major metric, you better have strong evidence
- Big wins are rare; most features move metrics 1-5%

2. Have you accounted for cannibalization?
- Will new feature pull users from existing successful flows?
- Are you double-counting benefits?

3. What about adoption curve?
- Impact isn't instant; how long to full adoption?
- Have you accounted for ramp time?

4. What could make you wrong?
- List 3 ways your model breaks
- What's the worst case scenario?

### Identify Uncertainty

What you're confident about:
- [Assumption with strong data]

What you're guessing about:
- [Assumption with weak data]

How to de-risk:
- [What experiment or analysis would increase confidence]

Example:
- Confident: "40% of users are on mobile" (we have analytics)
- Guessing: "One-click checkout will reduce drop-off by 20%" (no data)
- De-risk: Run fake door test showing one-click option, measure click rate

---

## PART 4: TRANSLATE TO BUSINESS IMPACT

### From Metric to Money

Most features impact intermediate metrics. Translate to business outcomes.

If you're improving conversion:

Current:
- 10,000 visitors/month
- 5% convert = 500 customers
- $100 average order = $50K revenue/month

With feature (+1.5% absolute conversion):
- 10,000 visitors
- 6.5% convert = 650 customers
- +150 customers × $100 = +$15K/month = +$180K/yearIf you're improving retention:

Current:
- 1000 customers
- 5% monthly churn = 50 leave each month
- $50/month ARPU
- Annual churned revenue = 50 × 12 × $50 = $30K lost

With feature (-1% absolute churn):
- 4% monthly churn = 40 leave
- Annual churned revenue = $24K
- Saved $6K/year in churn

### Cost-Benefit

Investment required:
- Engineering: [X weeks]
- Design: [Y weeks]
- PM/QA: [Z weeks]
- Total cost: [loaded cost ~$150-250/hr for eng]

Expected return:
- Conservative: [$ impact]
- Moderate: [$ impact]
- Optimistic: [$ impact]

Payback period:
- Investment / Monthly impact = [X months to break even]

The decision:
[Is this worth building based on ROI?]

---

## THE OUTPUT

### Impact Sizing Summary (One Page)

Feature: [What we're building]

Target Metric: [What improves]

Expected Impact:
- Conservative: [X% improvement / $Y value]
- Moderate: [X% improvement / $Y value]
- Optimistic: [X% improvement / $Y value]

Key Assumptions:
1. [Assumption 1 with confidence level]
2. [Assumption 2 with confidence level]
3. [Assumption 3 with confidence level]

Investment: [Cost]
Payback Period: [Months]

Recommendation: [Build / Don't Build / Validate Assumptions First]

### Detailed Model

[All calculations from above with clear assumptions]

### Assumption Testing Plan

To increase confidence, we should:
1. [Experiment or analysis to validate key assumption]
2. [Next experiment]

</sizing_framework>

<quality_check>

Are your assumptions realistic?
- [ ] Not assuming 100% adoption
- [ ] Effect sizes are in line with similar features
- [ ] You've accounted for ramp time

Can someone challenge your model?
- [ ] All assumptions are explicit
- [ ] Math is shown step-by-step
- [ ] You've identified what you're uncertain about

Is it actionable?
- [ ] Clear enough to inform prioritization
- [ ] Identifies what would change your mind
- [ ] Conservative enough to be believable

</quality_check>

<meta_wisdom>

On impact sizing:

Most PMs make one of two mistakes:

Mistake 1: Wildly optimistic
"This will 10x our conversion rate!"
(No it won't. It'll move it 2-5% if you're lucky.)

Mistake 2: Refuse to estimate
"We can't know the impact until we ship."
(True, but educated guesses beat no guesses.)

The right approach:
Make an estimate. Show your assumptions. Update as you learn.

The key principle:

Impact sizing isn't about being right.
It's about being honest about uncertainty.

Good model: "If 30% adopt and it works, we'll see $500K lift. But adoption could be 10-50%, so real range is $150K-$1M."

Bad model: "This will generate $847,293 in year one."

On assumptions:

The most dangerous assumptions are the ones you don't write down.

Because if you don't write them, you can't test them.
And if you can't test them, you'll believe them even when they're wrong.

Remember:

All models are wrong. Some are useful.

Your job isn't to predict the future perfectly.
It's to make the best decision you can with imperfect information.

Show your work. State your assumptions. Update your beliefs when reality hits.

</meta_wisdom>

</impact_sizing>