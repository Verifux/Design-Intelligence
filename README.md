# design-intelligence-skill

A 6-stage design intelligence stack for Claude Code. Builds non-generic, high-quality web interfaces — from copy strategy through cinematic delivery — without the AI design tells.

---

## What This Is

A Claude Code skill plugin with 4 proprietary skills and an orchestrator that routes tasks through the right stage at the right time. Third-party tools are listed as peer dependencies so you install exactly what you want.

**6 stages:**

| Stage | Name | Skill | Job |
|---|---|---|---|
| S0 | Strategy | `/taste-arbitrage` (included) | Copy and positioning — weak-vs-strong test before any word is written |
| S1 | Reference | Public galleries (Awwwards, Dribbble, CSSDA, Mobbin) | Extract visual system signals before building |
| S2 | Generate | `/design-taste-frontend` (included) | Anti-slop landing pages and portfolios — 3 configurable dials, 50+ Pre-Flight rules |
| S3 | Audit | `/redesign-existing-projects` (included) | Upgrade existing sites without rewriting from scratch |
| S4 | Verify | `impeccable` (peer dep) | Post-flight design quality check |
| S5 | Deliver | `scroll-world` + `frontend-design-toolkit` (peer deps) | Cinematic scroll landing pages and tool selection |

---

## Quick Install

```bash
# Clone and install the plugin
gh repo clone kishanrama/kish-design-intelligence ~/.claude/plugins/kish-design-intelligence

# Or install via Claude marketplace (when available)
claude plugin add kishanrama/kish-design-intelligence
```

### Then install peer dependencies (pick what you need)

```bash
# Animation and component generation (recommended)
claude plugin add nextlevelbuilder/ui-ux-pro-max-skill

# Cinematic scroll landing pages (S5)
claude plugin add oso95/scroll-world

# Frontend tool reference (S5)
claude plugin add wilwaldon/Claude-Code-Frontend-Design-Toolkit

# Live framework docs — essential for React 19, Tailwind v4, Next.js App Router
claude mcp add context7 -s user -- npx -y @upstash/context7-mcp@latest

# Visual browser testing
claude mcp add playwright -s user -- npx @playwright/mcp@latest

# Design quality polish
npx ui-skills add baseline-ui
npx ui-skills add fixing-accessibility
npx ui-skills add fixing-motion-performance
```

---

## What's Included

### `/design-intelligence` — Orchestrator
The main entry point. Reads your task and routes to the right stage and skill. Start here for any design or product session.

```
/design-intelligence build a landing page for a B2B SaaS tool
/design-intelligence audit my existing portfolio site
/design-intelligence review this copy for weak signals
```

### `/taste-arbitrage` — Copy and Positioning
Based on the thesis that AI has commoditized execution — judgment is now the scarce skill. Tests any positioning line, case study paragraph, or proposal sentence against 5 questions to separate judgment signals from commodity copy.

Best for: landing page copy, portfolio case studies, client proposals, pitch decks.

### `/design-taste-frontend` — Anti-Slop Frontend
Landing pages, portfolios, and redesigns. 3 configurable dials (`DESIGN_VARIANCE`, `MOTION_INTENSITY`, `VISUAL_DENSITY`), design system routing by brief, 50+ Pre-Flight rules covering typography, color, layout, motion, accessibility, and copy. The em-dash is banned.

Not for dashboards, data tables, or multi-step product UI (those belong in Fluent, Carbon, or Atlassian).

### `/redesign-existing-projects` — Upgrade Without Rewriting
Diagnoses 60+ generic patterns (AI design tells, font problems, color clashes, layout defaults, missing states) and applies targeted fixes without changing the tech stack or breaking existing functionality.

### `/mastery-loop` — Session Operating System
The continuous improvement loop: Observe, Extract, Encode, Apply, Measure, Repeat. Run at the start of every session. Includes weakness diagnosis patterns (planning-as-avoidance, silent stall, identity-performance fusion) and a prompt quality checklist.

---

## Reference Sources

`references/public-gallery-sources.md` — detailed extraction guides for:
- **Awwwards** — layout composition, type pairings, motion patterns
- **Dribbble** — palette ideas, micro-interaction details
- **CSS Design Awards** — production-quality animation and scroll interaction
- **Mobbin** — mobile-first patterns, onboarding flows, product UI states

---

## Usage Examples

**Starting a new landing page:**
```
/design-intelligence build a landing page for [your product]
```
Routes to: S1 gallery reference → S2 `/design-taste-frontend`

**Auditing an existing site:**
```
/redesign-existing-projects
```
Scans codebase, diagnoses problems, applies targeted fixes.

**Checking copy before shipping:**
```
/taste-arbitrage
```
Runs the weak-vs-strong test on any positioning or case study copy.

**End-of-session retrospective:**
```
/mastery-loop
```
2-minute review. What worked, what stalled, what changed.

---

## What This Is Not

- Not a design system (no component library)
- Not a dashboard or data UI tool (those have dedicated systems)
- Not a Figma plugin

---

## License

MIT

---

## Credits

Built on top of public gallery research (Awwwards, Dribbble, CSSDA, Mobbin) and open-source peer dependencies. Third-party skills (`ui-ux-pro-max`, `scroll-world`, `frontend-design-toolkit`, etc.) are independent projects — check their respective repos for license and install instructions.
