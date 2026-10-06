# taste-skill
Frontend design skills that make an agent read the brief, set three dials, obey binary bans, and pass a pre-flight check.
Source: github.com/Leonxlnx/taste-skill @ ce26fc2 (2026-09-26)

## The three dials (1-10, baseline 8 / 6 / 4)
- **DESIGN_VARIANCE.** 1-3 Predictable symmetric grid; 4-7 Offset overlaps and mixed ratios; 8-10 Asymmetric masonry, big empty zones.
- **MOTION_INTENSITY.** 1-3 Static, hover only; 4-7 Fluid CSS transitions; 8-10 Advanced Choreography with scroll-driven reveals and parallax.
- **VISUAL_DENSITY.** 1-3 Art Gallery with huge gaps; 4-7 Daily App spacing; 8-10 Cockpit with 1px dividers and mono numbers.
- **Infer, then declare.** Set dials from the brief, state one "Reading this as: ..." line, and ask at most one question.

## Design rules
- **Real systems.** When the brief reads as Material, Fluent, Carbon, or shadcn, install the official package; one system per project.
- **Typography.** Sans display (Geist, Satoshi, Outfit) over Inter; serif only for editorial brands; emphasize with same-font italic.
- **Color and locks.** One desaturated accent on neutral bases, one theme, one radius system, identical across the whole page.
- **Layout.** Off-center heroes above variance 4; at least 4 layout families per 8 sections; at most 2 zigzags in a row.
- **Hero.** Headline ≤ 2 lines, subtext ≤ 20 words, CTA visible without scrolling, at most 4 text elements.
- **Content density.** Sections get a ≤ 8-word headline and ≤ 25-word body; lists over 5 items become cards, tabs, or carousels.
- **Components.** Cards only when elevation shows hierarchy; bento has exactly N cells for N items; nav fits one line, ≤ 80px.
- **States and CTAs.** Ship loading, empty, and error states; one label per CTA intent; AA contrast on every button and input.
- **Motion.** Justify each animation in one sentence; use springs, transform and opacity only, reduced-motion fallback, one marquee max.

## AI tells (banned by default)
- **Visual.** Skip neon glows, pure black, AI-purple gradients, three equal feature cards, div-built fake screenshots, and hand-drawn icons.
- **Labels.** Skip section-number eyebrows, version badges, scroll cues, decorative dots, locale strips; max one eyebrow per three sections.

## Writing bans
- **Zero em-dashes.** Replace every em-dash with a hyphen, period, comma, or colon; the ban is zero, not "sparingly".
- **Plain words.** Use concrete verbs, real-sounding names, active voice; drop elevate, seamless, unleash, delve, Acme, lorem ipsum.
- **Copy self-audit.** Reread every visible string; rewrite cute or vague lines plainly and label invented numbers as mock.

## No truncation (output-skill)
- **Lock the count.** Count requested deliverables first, then compare the output against that count before replying.
- **Full output.** Write every part in full: no `// ...`, `// TODO`, "similarly for the rest", or "let me know".
- **Clean pause.** Near the limit, stop at a clean boundary with "[PAUSED - X of Y complete]" and resume without recap.

## Why models shortcut
- **Trained brevity.** RLHF and stopping pressure reward short confident answers; tutorial code teaches `// implement here` as normal.
- **Budget fear.** Models compress early when the full answer looks too long; chunk work into outline, then parts.
- **Effort, not memory.** Truncation is a behavioral choice on complex tasks, not forgetting; explicit bans and checks counter it.

## Steal this
- **Binary bans.** Write "zero" or "exactly N", never "sparingly", and name the exact condition that lifts each ban.
- **Mechanical pre-flight.** End with countable checkboxes (eyebrows ≤ sections / 3); one failed box means the work is not done.
