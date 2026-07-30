# Public Gallery Reference Sources

These are the S1 reference sources for the Design Intelligence Stack. Mine them for specific decisions before building. Do not copy markup. Extract the visual system.

---

## How to Extract (for any source)

For every 3 sites you open, note:
1. **Type family** — what font? weight used at display scale? tracking at body?
2. **Type scale** — approximate sizes at display, H1, H2, body, caption
3. **Palette** — primary accent hex, neutral family (warm gray vs cool gray vs true neutral)
4. **Layout family** — hero structure (split, centered, asymmetric, editorial), grid type
5. **Motion signature** — scroll behavior (parallax, pinned, flat), hover states, entry animations
6. **Component signatures** — how are cards handled? nav structure? CTA button shape?

Convergence rule: if two or more independent sites share the same decision (same type family, same neutral, same layout) — that is a real signal, not coincidence. Weight it.

---

## Awwwards (`awwwards.com`)

**Best for:** Winning type pairings, layout composition, high-craft motion patterns.

**Navigation tips:**
- `/sites` — site of the day / week / month. Most current signal.
- `/websites/portfolio` — specifically for portfolio/agency references
- `/websites/agency` — agency/studio landing pages
- `/websites/landing-page` — SaaS and product landing pages
- Filter by year (current) to avoid dated patterns

**What to mine:**
- How display type is treated at large scale (size, weight, tracking)
- Asymmetric layout decisions — where are elements offset, overlapping, or bleeding off-screen?
- Scroll interactions — is there a scroll hijack? pinned section? parallax?
- Background treatments — mesh gradient, video, photography, flat?

**What to ignore:**
- Awards count — a site with 7 awards is not always better than one with 2
- Any site using AI-purple gradient blobs as background — this is the commodity layer now

---

## Dribbble (`dribbble.com`)

**Best for:** Color palette ideas, UI micro-interaction details, component-level decisions.

**Navigation tips:**
- Search by specific element: "SaaS pricing table", "dark mode card", "onboarding modal"
- Filter by: Following (if you follow quality designers) or Popular this week
- `/shots/popular?timeframe=week` — current signals

**What to mine:**
- Palette combinations — note the hex codes or approximate values
- Card treatments — border vs shadow vs background-only vs no card
- Button anatomy — radius, size, label style, hover state
- Spacing rhythm — how much air between elements at a given density

**What to ignore:**
- Mobile-only shots for desktop landing page work (and vice versa)
- Shots that are concept-only with no production-quality constraint

---

## CSS Design Awards (`cssdesignawards.com`)

**Best for:** Production-quality interaction, animation, and motion references. Heavier than Awwwards shots — sites here tend to be fully executed.

**Navigation tips:**
- `/wotd` — website of the day
- `/nominees` — broad browse
- Special Kudos / CSSDA Award winners for the highest-signal sites

**What to mine:**
- Scroll choreography — what happens on scroll entry for each section?
- Micro-interactions on hover — buttons, cards, nav items
- Transition between pages or sections — full-page transitions, morphing shapes
- Typography in motion — does text animate on enter? scrubbed? typewriter?

**What to ignore:**
- WebGL-heavy entries when your build target is a lightweight landing page — note the interaction pattern, not the renderer

---

## Mobbin (`mobbin.com`)

**Best for:** Mobile-first patterns, onboarding flows, navigation, bottom sheets, product UI. Use this for anything that touches product interface, not just marketing.

**Navigation tips:**
- Browse by flow type: Onboarding, Authentication, Settings, Empty State, etc.
- Search by company: "Stripe mobile", "Linear iOS" — see how established products handle specific states
- Platform filter: iOS vs Android vs Web

**What to mine:**
- Empty state design — how does the product communicate "nothing here yet" without feeling broken?
- Onboarding step structure — how many steps? what does the progress indicator look like?
- Navigation patterns — tabs, side nav, floating action button, command palette
- Form patterns — label placement, validation timing, error messaging
- Bottom sheet and modal treatment

**What to ignore:**
- Outdated screenshots (Mobbin timestamps — check the capture date)
- Screenshots from apps known for poor design standards

---

## Cross-Source Convergence Signals (as of mid-2026)

These patterns were showing up independently across multiple galleries — treat as current-signal defaults:

- **Type:** Sans-serif display dominates. Cabinet Grotesk, Neue Montreal, Geist Display, Satoshi. Serif only for editorial.
- **Scale:** Display at 80-120px+. Tight leading (0.9-1.0). Negative tracking at -0.02em to -0.04em.
- **Neutral:** Zinc/Slate family for cool, Stone for warm. True black (`#000`) rarely; off-black (`#0a0a0a`, `#111`) more common.
- **Motion:** Scroll-driven entries. Staggered reveal on section enter. Spring physics on hover.
- **Layout:** Asymmetric split heroes. Bento grids with visual variation. Max 2 marquees per page.
- **Cards:** Minimal — border only, or background tint only, rarely both.
- **CTAs:** One primary, one optional secondary. Both fit on one line. No em-dash in labels.
