# Impeccable
One `/impeccable` skill with 24 commands and 60 deterministic detector rules; core idea: "Every model trained on the same SaaS templates," so record product truth, commit to a direction, then scan for the tells.
Source: github.com/pbakaus/impeccable @ 12b25ae (2026-10-06) · Apache-2.0 · 78k stars

## Before coding
- **Product truth first.** `init` writes PRODUCT.md with users, purpose, positioning, constraints, and evidence; visual style comes later, per surface.
- **Mode per surface.** Pick Persuade, Operate, Read, or Experience; for Operate (apps, dashboards, tools) ask the task, important states, frequency.
- **Inherit what exists.** A new section, feature, or state inside an established surface keeps that surface's visual world.
- **Direction contract.** Before code, write THESIS, OWN-WORLD, STORY, FIRST VIEWPORT, FORM, and FINISH in roughly 150 words.

## Design rules
- **Earned familiarity.** The visual world lends only "type, palette, density, and one signature move"; layout, navigation, and controls stay standard.
- **Product type.** Use one well-tuned sans, a fixed rem scale at a 1.125–1.2 ratio, and 65–75ch prose.
- **Restrained, not gray.** Tint the shell, rail, or ground; reserve accent for actions, selection, and state; standardize state colors.
- **Full state set.** Every control ships default, hover, focus, active, disabled, loading, and error; skeletons for loading; empty states that teach.
- **Spacing rhythm.** Group tightly, separate generously, leave more space above a heading than below, on a 4-unit scale.
- **Motion as state.** Product transitions run 150–250 ms, convey state only, and use exponential ease-out like `cubic-bezier(0.16, 1, 0.3, 1)`.
- **Theme browser surfaces.** Style text selection, caret, scrollbars, focus rings, underline offset, and tabular numerals from the palette.

## Anti-patterns it names
- **Side-tab accent border.** Thick colored `border-left` or `border-right` on cards, alerts, and list items; "the most recognizable tell".
- **Card kit.** Same-size icon-tile-plus-heading-plus-text cards as page structure; cards nested in cards, which are "always wrong".
- **Hero-metric and kicker.** Big number, small label, supporting stats, accent; a tiny tracked label above a heading, "a ban, not a default".
- **AI palette.** Purple-to-blue gradients, cyan-on-dark, cream or beige default ground, dark glows, gradient text, gray text on color.
- **Overused defaults.** Inter, Roboto, Fraunces, Geist, Plus Jakarta Sans, Space Grotesk; monospace as costume; bounce easing; "supercharge" copy.

## Libraries and tools it recommends
- `npx impeccable detect` and the browser extension: run the 60 rules on files or URLs, with no LLM and no API key
- DESIGN.md (google-labs-code/design.md spec): YAML token frontmatter plus eight sections, so new screens stay on-brand
- Per-command picks: motion, GSAP, Three.js, OGL, regl, TanStack Virtual, deck.gl, D3 for `overdrive`; Tippy.js, Popper.js, Intro.js, Shepherd.js, React Joyride for `onboard`; Lighthouse, WebPageTest for `optimize`

## Steal this
- **Floor right before edits.** Load a short Verify list (contrast, depth, spacing, type, motion, states, browser surfaces, copy) and Refuse list just before any UI edit; keep accessibility reminders for the audit, since design-time reminders produce "safe, underdesigned output".
- **Two-pass critique.** Score Nielsen's 10 heuristics 0–4, tag issues P0–P3, check for ≤4 visible options per decision; run the detector in an isolated subagent and merge only after the design review finishes, so judgment stays unanchored.
- **Category test.** Add the line "if someone could guess your aesthetic from the category alone, or from category-plus-avoidance, rework until neither answer is obvious."
