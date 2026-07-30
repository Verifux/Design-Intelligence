---
name: mastery-loop
description: "Continuous improvement operating system for product building and design. Load at the start of every Claude session to activate the observe-extract-encode-apply-measure loop. Prevents planning-as-avoidance and keeps work pointed at shipping."
argument-hint: "[session type: start | review | blocker | weekly]"
---

# Mastery Loop

Continuous improvement operating system. Run at the start of every session and for 2 minutes at the end.

---

## The Core Loop

```
OBSERVE -> EXTRACT -> ENCODE -> APPLY -> MEASURE -> REPEAT
```

1. **OBSERVE** - What worked, what stalled, what surprised you, what did you skip.
2. **EXTRACT** - One insight worth keeping. One repeating pattern. What it says about the system, not just the task.
3. **ENCODE** - Write it somewhere retrievable. Memory, a project note, or update this file. Name it so future-you finds it fast.
4. **APPLY** - Use it in the very next task. Change a default now, not later.
5. **MEASURE** - Was the next session faster or cleaner? Did the change stick or get reverted?
6. **REPEAT** - Mini-review at end of every session (2 min). Full review weekly (10 min).

---

## Weakness Diagnosis

Named patterns to call out directly, not gently talk around:

| Pattern | What it looks like | Direct move |
|---|---|---|
| **Planning-as-avoidance** | Another round of strategy, positioning, or design refinement before the current version ships | Ship the smaller, uglier version today |
| **Waiting for perfect conditions** | "Once X is sorted I'll start Y" | Start Y in parallel, in its current imperfect state |
| **Identity-performance fusion** | Delaying a task because getting it wrong feels unsafe, not just inconvenient | Name it: the risk is the discomfort, not the outcome. Do it anyway |
| **Control-seeking via over-research** | Reading/comparing more options instead of committing to one and moving | Pick the reasonable option, timebox the decision, move |
| **Silent stall** | A task quietly disappears from the conversation for multiple sessions without being named as dropped | Ask directly: is this cancelled, delayed, or avoided? |

**The Override** — apply the moment any of the above shows up:
Do the smallest possible version of the thing right now. Not the perfect version. The started version.

---

## Design Intelligence Stack Routing

When any session involves UI, visual design, copy, or product positioning, run this chain in order:

| Stage | Skill(s) | Job |
|---|---|---|
| 0 - Strategy | `/taste-arbitrage` | What should the words say? Weak-vs-strong test before any copy is written |
| 1 - Reference | Public galleries (Awwwards, Dribbble, CSSDA, Mobbin) | Palette, type, pattern. Pull from public sources before building anything |
| 2 - Generate | `/design-taste-frontend` (landing/portfolio), peer deps for any UI | Build with constraints from stages 0-1 already in hand |
| 3 - Audit | `/redesign-existing-projects` + peer dep `21st-ui-review` | For existing builds, audit before generating |
| 4 - Verify | Peer dep `impeccable` | Post-flight. `npm run design:check`. Exit 2 = fix before shipping |
| 5 - Deliver | Peer deps `/scroll-world` + `/frontend-design-toolkit` | Ship in the right format |

**Convergence rule:** Where two or more tools independently flag the same issue, that is the real signal. Act on it.

---

## Prompt Quality Checklist

**Before sending:**
1. Is the goal clear in the first sentence?
2. Enough context that no assumptions are needed?
3. One thing or five things? Split if five.
4. Right model for this task?
5. Can this be front-loaded to avoid three follow-up turns?

**After receiving:**
1. Did it answer what was actually needed?
2. If not — unclear prompt or model limitation?
3. What one change makes the next prompt better?

---

## Model Selection

| Task type | Model | Thinking |
|---|---|---|
| Complex strategy, architecture, hard decisions | Opus | High |
| Product design, spec writing, UX work | Sonnet | Medium |
| Code generation, component building | Sonnet | Low-Medium |
| Quick questions, formatting, lookups | Sonnet | Off |

---

## Context Hygiene

**Degrades quality:**
- Long threads re-sending everything each turn
- Missing or stale project files
- Switching topics without a fresh chat
- Pasting code without explaining intent

**Fixes:**
- Fresh chat per topic
- One living project context file, max one page
- Targeted edits, not full regenerations
- Dense front-loaded prompts over multi-turn back-and-forth

---

## Weekly Review (10 min)

- What did I build or ship this week?
- What did I avoid, and why — name the real reason?
- One thing I will do differently.
- What moved closer to the primary project goal?

---

## Shipping Pressure Question

When a session drifts into pure design or strategy polish with no shipping step attached, ask:
> "Does this get us closer to a shipped thing this week, or is this comfortable planning?"

Say it plainly. Do not soften it.

---

## Skill Self-Update Protocol

Update this file when:
- A new workflow pattern emerges
- A model default changes
- A new tool or MCP connector changes the stack
- A weekly review reveals a gap
- A weakness pattern shows up that is not yet named above

Add a version line at the top with date and one-line summary of the change.
