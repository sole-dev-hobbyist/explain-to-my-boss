---
name: explain-to-my-boss
description: Translate any technical content — errors, code, architecture decisions, PRs, tickets, or concepts — into clear, plain English that a non-technical manager or executive can understand and act on.
intent: >-
  Take any technical input and rewrite it in plain language for a non-technical audience. The goal is not to dumb things down — it's to communicate clearly: what happened, why it matters, what it will take to fix or build, and what decision (if any) is needed.
type: component
theme: communication
best_for:
  - "Explaining a production incident to leadership"
  - "Justifying technical debt or refactoring work to a manager"
  - "Translating a stack trace or error into something actionable"
  - "Making a PR or architecture decision legible to non-engineers"
  - "Helping non-technical stakeholders understand a timeline or estimate"
scenarios:
  - "Here's our stack trace from last night's outage, explain it to my boss"
  - "Explain why we need to rewrite this legacy service"
  - "Translate this PR description into something the product team can understand"
  - "Why is this feature taking 3 weeks? Help me explain that"
  - "Make this security vulnerability report readable for the exec team"
estimated_time: "1-2 min"
---

## Purpose

Take anything technical and make it understandable for someone who doesn't code. Not a watered-down summary — a clear, confident explanation that respects your audience's intelligence while meeting them where they are.

This skill works for **any technical input**: error logs, PRs, architecture diagrams, migration plans, performance metrics, security reports, dependency updates, estimates, refactoring rationale, or anything else.

---

## What "Explain to My Boss" Means

Your boss doesn't need to understand `NullPointerException`. They need to understand:
- **What happened** (or what we're building / what we're changing)
- **Why it matters** (impact on the business, users, or team)
- **What it takes** (time, cost, risk, effort)
- **What decision is needed** (if any)

That's the frame. Always answer those four questions, even if only one was asked.

---

## How to Apply This Skill

### Step 1: Identify the input type

Determine what you're translating:

| Input Type | Key Question to Answer |
|---|---|
| Error / stack trace | What broke, why, and is it fixed? |
| Production incident | What happened, who was affected, what did we do? |
| PR / code change | What changed, why, and what's the risk? |
| Architecture decision | What are we building and why this way? |
| Tech debt / refactor | Why spend time on this with no new features? |
| Estimate / timeline | Why does this take as long as it does? |
| Security vulnerability | How serious is it, what's exposed, what's the fix? |
| Dependency / upgrade | Why are we doing this and what could go wrong? |
| Performance issue | What's slow, what does it cost users, how do we fix it? |

### Step 2: Write the explanation

Use this structure — adjust length to match the stakes:

**One-liner (always include):**
A single sentence that captures the essence. If your boss only reads one line, this is it.

**What happened / What this is:**
Plain description. No jargon. If a technical term is unavoidable, define it in parentheses immediately.

**Why it matters:**
Business impact. User impact. Team impact. Skip it if there's genuinely none.

**What it takes:**
Time, effort, cost, or risk. Be honest. Don't hide complexity — translate it.

**What we need from you (if anything):**
A clear ask: approval, a decision, awareness, or nothing at all. Be explicit.

### Step 3: Tone calibration

Adjust tone based on context:

- **Incident / outage**: Calm, factual, no blame. Focus on resolution and prevention.
- **Asking for time/budget**: Confident, direct. Lead with business value.
- **Explaining a delay**: Honest, no excuses. Explain the constraint, not the victim.
- **Security issue**: Serious but not alarmist. Severity + action plan.
- **Technical choice**: Show you considered alternatives. "We chose X because Y, not Z because..."

---

## Rules

1. **No unexplained jargon.** If you use a technical term, define it inline.
2. **Lead with impact, not mechanism.** Don't start with how it works — start with what it means.
3. **Avoid passive voice.** "The database went down" not "there was a database-related issue."
4. **Be specific about time and risk.** "About a week" is better than "some time." "Low risk" needs a reason.
5. **Don't over-explain.** If it's a 2-sentence fix, say so. Padding destroys credibility.
6. **End with a clear status.** Resolved / In progress / Needs decision / No action needed.

---

## Examples

### Example 1: Stack Trace → Boss-Ready

**Input:**
```
java.lang.NullPointerException at com.app.OrderService.processPayment(OrderService.java:142)
```

**Output:**
> **One-liner:** The payment processing feature crashed for some users this morning due to a missing piece of data it expected to find.
>
> **What happened:** Our order system tried to process a payment but encountered data that wasn't there — like trying to open a file that doesn't exist. This caused the payment step to fail.
>
> **Who was affected:** Users who attempted to check out between 9:02–9:47am. Approximately 34 orders failed. All affected users have been notified and can retry — no money was charged.
>
> **What it takes:** The fix is a one-line code change with a proper check added. It's deployed and verified. The root cause was a data migration last week that left some records incomplete.
>
> **Status:** Resolved. We're running a cleanup script on the affected records tonight.

---

### Example 2: Refactor Request → Boss-Ready

**Input:** Developer wants to rewrite the authentication module. No new features. Will take 2 weeks.

**Output:**
> **One-liner:** We're proposing 2 weeks to rebuild the part of our system that handles user logins — not to add features, but to prevent future outages and cut ongoing maintenance time.
>
> **What this is:** Our login system was built 4 years ago and has been patched repeatedly. It now takes 3x longer to make changes to it than it should, and it's the most common source of bugs in our security audit.
>
> **Why it matters:** Every new feature that touches login (password reset, SSO, 2FA) costs twice as long as it should because of this old code. We also have an upcoming compliance review — the current system will likely flag issues.
>
> **What it takes:** 2 weeks of one engineer's time. No downtime expected. Users won't notice any change. The payoff is faster feature delivery and a clean bill of health on the security audit.
>
> **What we need from you:** Approval to prioritize this over the reporting dashboard feature for the next sprint.

---

### Example 3: "Why is this taking 3 weeks?"

**Input:** PM asks why a feature that "seems simple" is taking 3 weeks.

**Output:**
> **One-liner:** The feature looks simple on the surface, but it requires changes in three separate systems that don't currently talk to each other.
>
> **What's happening:** Adding the export button requires: (1) building the export logic itself, (2) connecting it to our data pipeline (a separate system we don't own), and (3) handling the cases where exports are large or the system is busy — otherwise we'd crash the page for other users.
>
> **The honest breakdown:**
> - Export logic: 3 days
> - Data pipeline integration + testing: 5 days
> - Load handling + edge cases: 4 days
> - QA and release: 2 days
>
> **What we need from you:** If 3 weeks is too long, we can ship a limited version (CSV only, no scheduling) in 1 week — but the full feature would still need the remaining 2 weeks after that.

---

## Anti-Patterns

| ❌ Don't do this | ✅ Do this instead |
|---|---|
| "There was an NPE in the payment service" | "The checkout feature crashed due to missing data" |
| "We need to refactor the legacy auth module" | "We need 2 weeks to prevent future login outages" |
| "It's a race condition in the async handler" | "Two processes were trying to update the same record at the same time" |
| "The P99 latency spiked to 4200ms" | "The slowest 1% of page loads took over 4 seconds — 8x slower than normal" |
| "We have significant tech debt in this area" | "This part of the code takes 3x longer to change than it should" |

---

## Related Skills
- `skills/user-story/SKILL.md` — Turn requirements into dev-ready stories
- `skills/postmortem/SKILL.md` — Full incident postmortem format (if it exists)
