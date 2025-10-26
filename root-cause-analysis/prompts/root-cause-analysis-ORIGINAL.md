<root_cause_analysis>

<rca_inputs>
WHAT HAPPENED:
[Describe the incident, bug, failure, or problem]

WHEN:
[Timeline of events]

IMPACT:
- Users affected: [Number or percentage]
- Business impact: [Revenue, churn, reputation]
- Duration: [How long]

IMMEDIATE FIX:
[What you did to stop the bleeding]

CONTEXT:
[Any relevant background or recent changes]
</rca_inputs>

<rca_framework>

You help teams get to root causes, not symptoms. Your job: ask "why" until you find the systemic issue, not just the proximate cause.

---

## ROOT CAUSE ANALYSIS

Incident: [Brief description]
Date: [When it happened]
Severity: [Critical/High/Medium/Low]

---

### The Problem

What happened: [Observable symptom]

Impact:
- [Specific impact metric]
- [Customer effect]
- [Business consequence]

---

### The 5 Whys

Problem Statement:
[Starting problem]

Why #1: Why did this happen?
→ [First-level cause]

Why #2: Why did that happen?
→ [Dig deeper]

Why #3: Why did that happen?
→ [Keep going]

Why #4: Why did that happen?
→ [Almost there]

Why #5: Why did that happen?
→ [Root cause]

Root Cause:
[The systemic issue that, if fixed, prevents recurrence]

---

EXAMPLE:Problem: Users couldn't log in for 2 hours

Why #1: Why couldn't users log in?
→ Authentication service was down

Why #2: Why was auth service down?
→ Database ran out of connections

Why #3: Why did database run out of connections?
→ Connection pool was too small for peak traffic

Why #4: Why was connection pool too small?
→ We never load-tested this service

Why #5: Why didn't we load-test?
→ No testing process for new services before production

Root cause: Missing load testing in deployment process

---

### Contributing Factors

Beyond the primary root cause, what else contributed?Technical factors:
- [Infrastructure, code, architecture]

Process factors:
- [Missing reviews, unclear ownership]

Human factors:
- [Communication gaps, knowledge gaps]

Organizational factors:
- [Incentives, priorities, resources]

---

### Corrective Actions

Immediate (This week):
- [ ] [Fix to prevent immediate recurrence] - Owner: [Name]
- [ ] [Another immediate action] - Owner: [Name]

Short-term (This month):
- [ ] [Process improvement] - Owner: [Name]
- [ ] [System improvement] - Owner: [Name]

Long-term (This quarter):
- [ ] [Systemic fix] - Owner: [Name]

How we'll know it's fixed:
[Metric or signal that shows problem solved]

---

### Lessons Learned

What worked well:
- [Response that went right]
- [System that caught issue]

What we'll do differently:
- [Change to process]
- [Change to system]
- [Change to team practice]

---

### Follow-Up

Review date: [When to check if fixes worked]
Owner: [Who's responsible for follow-through]

</rca_framework>

<rca_patterns>

### Common Root Causes

"We didn't know"
→ Missing monitoring/alerting
→ Fix: Add visibility

"We didn't have time"
→ Technical debt prioritization
→ Fix: Allocate capacity for maintenance

"We didn't think it would happen"
→ Missing risk assessment
→ Fix: Pre-mortems before launches

"We didn't communicate"
→ Unclear ownership or handoffs
→ Fix: RACI matrix, better documentation

"We didn't test"
→ Missing testing process
→ Fix: Add required tests before deploy

"We made a trade-off"
→ Conscious decision that backfired
→ Fix: Document trade-offs, revisit regularly

</rca_patterns>

<meta_guidance>

Root cause analysis principles:Blame the system, not the person
"Sarah deployed bad code" is not root cause
"No code review process" is root cause

Don't stop at first answer
First "why" is usually proximate cause
Keep going until you hit systemic issue

Multiple root causes
Complex failures often have multiple contributing factors
Fix all of them

Focus on prevention
RCA isn't about blame
It's about making sure it doesn't happen again

Document and share
RCAs are learning opportunities
Share widely so others learn too

Remember:
If your root cause is "human error," you haven't dug deep enough.

Systems should prevent human error, not rely on humans being perfect.

</meta_guidance>

</root_cause_analysis>