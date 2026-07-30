---
name: design-intelligence
description: "6-stage design intelligence orchestrator. Routes any UI, copy, or product design task through the right skill at the right stage: S0 Strategy, S1 Reference, S2 Generate, S3 Audit, S4 Verify, S5 Deliver. Load this first at the start of any design or product session."
argument-hint: "[task description or stage name]"
allowed-tools: Bash, Read, Write, Edit, AskUserQuestion, Skill
---

# Design Intelligence Stack — Orchestrator

6 stages. Every UI, copy, and product design task routes through this chain. Do not skip stages — each one is a quality gate.

---

## Stage Map

| Stage | Name | Skill(s) | Job |
|---|---|---|---|
| S0 | Strategy | `/taste-arbitrage` | What should the words say? Run weak-vs-strong test before any copy is written |
| S1 | Reference | Public galleries (Awwwards, Dribbble, CSSDA, Mobbin) | Extract palette, type, and layout signals before building anything |
| S2 | Generate | `/design-taste-frontend` (landing/portfolio) + peer deps for any UI | Build with constraints from S0 and S1 already in hand |
| S3 | Audit | `/redesign-existing-projects` + peer dep `21st-ui-review` | For existing builds, audit before generating |
| S4 | Verify | Peer dep `/impeccable` | Post-flight. `npm run design:check`. Exit 2 = fix before shipping |
| S5 | Deliver | Peer dep `/scroll-world` (cinematic landing) + `/frontend-design-toolkit` (tool selection) | Deliver the output in the right format |

---

## Routing Logic

When invoked, read the task context and route:

**Copy or positioning is being written or reviewed** → start at S0 (`/taste-arbitrage`)

**Starting a new landing page, portfolio, or redesign** → S1 (gallery reference) → S2 (`/design-taste-frontend`)

**Existing site being improved** → S3 (`/redesign-existing-projects`) → S2 if rewriting, S4 to verify

**Component or UI in any framework** → S2 (peer dep: `21st-ai` / `21st-ui-build` / `ui-styling`)

**Cinematic scroll landing page** → S5 (peer dep: `/scroll-world`)

**Choosing which tool or skill to use** → S5 (peer dep: `/frontend-design-toolkit`)

**End of any session** → Run the `/mastery-loop` retrospective (2 min)

---

## S0 — Strategy: `/taste-arbitrage`

Run before any copy is written. The weak-vs-strong test:
1. Does it lead with an aesthetic claim with no problem named behind it? Weak.
2. Does it name a specific user, workflow, or consequence before describing the interface? Strong.
3. Could a competitor with the same AI tools produce the exact same sentence? If yes, commodity layer.
4. Does it show the decision trail (research → reframe → build) or only the shipped artefact? Trail is strong.
5. Does it connect user need, business goal, and technical constraint in one paragraph? Connected is strong.

---

## S1 — Reference: Public Galleries

Pull from these sources before building. Mine for specific decisions, not whole systems.

| Source | What to extract |
|---|---|
| **Awwwards** (`awwwards.com`) | Winning type pairings, layout composition, motion patterns. Filter by year — check site of the day and site of the month for current signals |
| **Dribbble** (`dribbble.com`) | Color palette ideas, micro-interaction patterns, card and UI component details |
| **CSS Design Awards** (`cssdesignawards.com`) | Production-quality interaction and animation references. Look at Special Kudos winners |
| **Mobbin** (`mobbin.com`) | Mobile-first patterns, onboarding flows, navigation patterns. Best for product UI reference |

**Extraction method:** Pick 3 sites from any source. For each, note: font family, type scale, primary color + neutral, layout family (grid type, hero layout), motion signature (scroll behavior, hover states). Do not copy markup — extract the visual system.

**Convergence rule:** Where two or more independent references independently use the same type choice, palette signal, or layout pattern, that is the real trend. Weight it.

---

## S2 — Generate

### Landing pages and portfolios
Use `/design-taste-frontend`. Set the three dials from the brief before writing any code:
- `DESIGN_VARIANCE` — 1 (symmetric) to 10 (asymmetric chaos)
- `MOTION_INTENSITY` — 1 (static) to 10 (cinematic)
- `VISUAL_DENSITY` — 1 (art gallery) to 10 (cockpit)

Declare the design read first: *"Reading this as: [page kind] for [audience], with a [vibe] language, leaning toward [design system or aesthetic family]."*

### Any UI (components, product interfaces)
**Peer dependencies required** — install separately:
```bash
# 21st.dev (AI-powered component generation, 62.6k stars)
claude plugin add nextlevelbuilder/ui-ux-pro-max-skill

# Or 21st.dev MCP for live component search
claude mcp add 21st-dev ...
```

### Component library / design system
**Peer dependencies:**
```bash
npx ui-skills add baseline-ui
npx ui-skills add fixing-accessibility
npx ui-skills add fixing-motion-performance
```

---

## S3 — Audit: `/redesign-existing-projects`

For any existing site. Run before generating. Covers:
- Typography (font swap priority, tracking, scale)
- Color and surfaces (palette cleanup, accent discipline)
- Layout (symmetry, grid, spacing, max-width)
- Interactivity and states (hover, active, loading, empty, error)
- Content (copy quality, fake data, AI tells)
- Component patterns (generic card, three-equal-cards, accordion FAQ)
- Code quality (semantic HTML, inline styles, z-index scale)

**Supplementary audit peer dep:**
```bash
# 21st.dev UI review (lint-style design check)
claude plugin add 21st-dev/21st-ui-review
```

---

## S4 — Verify

**Peer dependency:**
```bash
# impeccable (design quality checker)
npx add-skill impeccable/impeccable
```

After wiring, verify runs as:
```bash
npm run design:check
```

Exit code 2 = fix before shipping. Non-negotiable.

---

## S5 — Deliver

### Cinematic scroll landing page
**Peer dependency:**
```bash
claude plugin add oso95/scroll-world
```
Generates a scroll-scrubbed landing page using Higgsfield (stills) and Monid (video). Full 8-step pipeline: interview → stills → float → camera architecture → connectors → encode → assemble → QA.

### Tool and skill selection
**Peer dependency:**
```bash
claude plugin add wilwaldon/Claude-Code-Frontend-Design-Toolkit
```
Reference for 70+ frontend tools organized by task — picks the right animation lib, MCP, or install stack for the job.

---

## Peer Dependencies — Install Everything

```bash
# Bundled (included in this repo)
# /taste-arbitrage, /design-taste-frontend, /redesign-existing-projects, /mastery-loop

# Third-party peer deps — install separately
claude plugin add nextlevelbuilder/ui-ux-pro-max-skill
claude plugin add oso95/scroll-world
claude plugin add wilwaldon/Claude-Code-Frontend-Design-Toolkit
claude mcp add context7 -s user -- npx -y @upstash/context7-mcp@latest
claude mcp add playwright -s user -- npx @playwright/mcp@latest
npx ui-skills add baseline-ui
npx ui-skills add fixing-accessibility
npx ui-skills add fixing-motion-performance
```

---

## Convergence Rule

Where two or more tools independently flag the same issue — same type problem, same copy weakness, same layout pattern — that is the real signal. Act on it.

---

## Anti-Skipping Rule

Do not invoke S2 (Generate) without running S0 (copy check) and S1 (reference pull). Do not call a build done without S4 (verify). Every skipped stage is a quality debt that shows up in production.
