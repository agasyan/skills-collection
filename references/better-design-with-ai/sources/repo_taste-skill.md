# Taste Skill
Portable anti-slop agent skills; the default (v2) infers a design read, sets three 1-10 dials, then enforces hard bans and a pre-flight checklist.
Source: github.com/Leonxlnx/taste-skill @ e3c9203 (2026-10-06) · MIT · 93k stars

## Before coding
- **Design Read.** Print one line: "Reading this as: <page kind> for <audience>, with a <vibe> language, leaning toward <design system>."
- **Three dials.** Set DESIGN_VARIANCE, MOTION_INTENSITY and VISUAL_DENSITY (1-10) from the brief; baseline `8/6/4`, public-sector `3/2/5`.
- **Official system first.** When the brief reads as Fluent, Carbon, Material, Polaris, Atlassian, Primer, GOV.UK or USWDS, "install and use the official package".
- **Redesign mode and audit.** Classify Greenfield, Preserve or Overhaul first, then audit brand tokens, IA, SEO and analytics events before changing anything.

## Design rules
- **One accent, locked.** Use one accent under 80% saturation over Zinc, Slate or Stone neutrals, identical in every section.
- **Consistency locks.** Lock one theme per page, one corner-radius scale (0, 12-16px or pill), and one icon family per project.
- **Type defaults.** Prefer Geist, Satoshi, Outfit or Cabinet Grotesk over Inter, cap body at `max-w-[65ch]`, and keep serif out of dashboards.
- **Density by dial.** At VISUAL_DENSITY 8-10 ("Cockpit"), drop card boxes, separate data with 1px lines, and set every number in `font-mono`.
- **Cards earn elevation.** Use cards only when elevation shows real hierarchy; otherwise group with `border-t`, `divide-y`, or negative space.
- **Every state.** Ship layout-shaped skeleton loaders, composed empty states, inline errors, and labels above inputs that pass WCAG AA.
- **Motivated motion.** Justify each animation in one sentence, animate only `transform` and `opacity`, and honor reduced motion above MOTION_INTENSITY 3.

## Anti-patterns it names
- **AI defaults.** AI-purple glow gradients ("THE LILA RULE"), centered hero over dark mesh, three equal feature cards, Inter + slate-900.
- **Eyebrow spam.** Small `uppercase tracking-[0.18em]` labels over every section, "the #1 violated rule"; the cap is 1 per 3 sections.
- **Em-dashes.** Any em-dash or en-dash in visible copy, "the #1 visual Tell in production tests".
- **Fake content.** Div-built fake dashboards or terminals, "John Doe", "Acme", `99.99%`, "Elevate", "Seamless", "Unleash".
- **Decorative micro-meta.** `001 · Capabilities` numbering, status dots without real state, `v1.4.2` footers, scroll cues, "Quietly trusted by".

## Libraries and tools it recommends
- Fluent UI v9, Carbon, Material Web, Polaris, Atlaskit, Primer, GOV.UK Frontend, USWDS, Radix Themes, shadcn/ui, Bootstrap 5.3: official foundations, with install commands it calls "reality anchors".
- Tailwind v4 (`@tailwindcss/postcss` or Vite plugin), Next.js Server Components, `next/font`: default stack; Motion (`motion/react`): UI motion; GSAP + ScrollTrigger: pin and scrub only.
- `@phosphor-icons/react`, `hugeicons-react`, `@radix-ui/react-icons`, `@tabler/icons-react`: icons in priority order; `lucide-react` only on request.

## Which variant for which product
- taste-skill (v2, `design-taste-frontend`): landing pages, portfolios, editorial and redesigns; it sends dashboards to Fluent, Carbon, Atlassian or Polaris and tables to TanStack Table or AG Grid.
- redesign-skill: existing sites and apps; Scan, Diagnose, Fix on the current stack, starting with a font swap and palette cleanup.
- minimalist-skill: Notion/Linear-style editorial product UI; brutalist-skill: data-heavy dashboards and blueprint-style portfolios; soft-skill: calm premium consumer pages.
- gpt-tasteskill: GPT/Codex GSAP pages; stitch-skill: a Google Stitch `DESIGN.md`; output-skill: agents that truncate code; imagegen-frontend-web/mobile, brandkit, image-to-code-skill: reference images first.

## Steal this
- **Design Read preamble.** Require the one-line read and three dial values before code; internal tools fit density 4-7 "Daily App" or 8-10 "Cockpit".
- **Countable pre-flight.** End with checks an agent can count: zero em-dashes, eyebrows at most ceil(sections/3), one accent, one radius scale, all states.
