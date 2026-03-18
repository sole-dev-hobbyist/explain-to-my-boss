# explain-to-my-boss

A Claude Code skill that translates **any technical content** into plain English your manager or executive can understand and act on.

Works with: stack traces, production incidents, PRs, architecture decisions, estimates, security vulnerabilities, tech debt rationale, performance issues — anything.

---

## Install

```bash
npx skills add explain-to-my-boss
```

Or manually copy `SKILL.md` into your `~/.claude/skills/explain-to-my-boss/` directory.

---

## Usage

```
/explain-to-my-boss <paste anything technical here>
```

**Examples:**

```
/explain-to-my-boss our Redis cache keeps evicting keys under load and the LRU policy isn't tuned correctly

/explain-to-my-boss NullPointerException at OrderService.processPayment line 142

/explain-to-my-boss why the new user dashboard feature is taking 3 weeks when it "looks simple"

/explain-to-my-boss CVE-2024-XXXX critical RCE in log4j affecting our API server
```

---

## What it produces

Every output answers four questions — regardless of input type:

| Question | What it covers |
|---|---|
| **What happened / What this is** | Plain description, no jargon |
| **Why it matters** | Business, user, or team impact |
| **What it takes** | Time, cost, risk, effort — honestly |
| **What's needed from you** | A clear ask, or explicit "no action needed" |

---

## Input types supported

| Input | Key question answered |
|---|---|
| Error / stack trace | What broke, why, is it fixed? |
| Production incident | What happened, who was affected, what did we do? |
| PR / code change | What changed, why, what's the risk? |
| Architecture decision | What are we building and why this way? |
| Tech debt / refactor | Why spend time on this with no new features? |
| Estimate / timeline | Why does this take as long as it does? |
| Security vulnerability | How serious, what's exposed, what's the fix? |
| Performance issue | What's slow, what does it cost users, how do we fix it? |

---

## Examples

See [`examples/sample.md`](./examples/sample.md) for five full worked examples covering:
- Stack trace → boss-ready incident summary
- Refactor request → budget justification
- "Why 3 weeks?" → honest timeline breakdown
- Critical CVE → executive security briefing
- Performance regression → clear status update

---

## Why this exists

Engineers are good at solving problems. Communicating them upward is a different skill. This bridges the gap — so you spend less time writing Slack messages and more time shipping.

---

## License

MIT
