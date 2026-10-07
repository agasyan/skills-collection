# AntiSlopUI
A Claude Code plugin (one skill, 16 references, eight agents) for awwwards-style animated Next.js + Tailwind sites, built on "Generic motion is worse than no motion."
Source: github.com/Adefebrian/AntislopUI @ d12026c (2026-06-02) · MIT · 15 stars

## Before coding
- **Brief first.** A creative director writes concept, art direction, page structure, 2-3 signature moves, motion budget and delegation table.
- **Values, not adjectives.** Write "clamp(3rem, 9vw, 11rem), leading-[0.95], expo.out reveal", not "big bold animated text".
- **Tokens before motion.** The designer wires palette, type scale, spacing and radius into Tailwind tokens before anyone animates.
- **Copy verified patterns.** Open the matching reference file and copy its pattern; write every API from the references, not memory.

## Design rules
- **Motion has a reason.** Each movement reveals hierarchy, guides the eye, rewards interaction or expresses brand; cut the rest.
- **Easing is identity.** Choose one or two signature eases, such as `[0.16, 1, 0.3, 1]` for UI or `expo.out` for heroes.
- **Timing table.** Keep micro-interactions at 0.2-0.4s, UI reveals 0.5-0.9s, page transitions 0.6-1.2s, sibling stagger 0.03-0.1s.
- **Quiet color.** Use near-black `#0a0a0a` and off-white `#f5f5f0` with one or two accents, never pure black or white.
- **Type.** Use two families at most; hero display `clamp(2.5rem, 9vw, 12rem)`, body leading 1.5-1.7, `tabular-nums` on stats.
- **Cheap properties.** Animate only `transform`, `opacity`, `filter` and `clip-path`; drive per-frame pointer work with `gsap.quickTo`.
- **Access gates.** Ship a `prefers-reduced-motion` path, gate pointer effects behind `(pointer: fine)`, and pass WCAG AA in every theme.

## Anti-patterns it names
- **Fade-up everything.** Every element fades up 20px on scroll with the same 0.3s `ease-in-out`.
- **Template look.** A drop shadow plus `border-radius: 8px` on every card, centered single-column layout, equal spacing top to bottom.
- **Undecided type and color.** System font at 16px, headings at 2x body, pure `#000` on `#fff`; "Slop is the absence of decisions."
- **Effect pileup.** Three animations on one element, every effect at once, stock library components, invented props, eases or imports.

## Libraries and tools it recommends
- `gsap` + `@gsap/react` (`useGSAP`): ScrollTrigger, SplitText, Flip and every plugin, "free since 2025", "Verified against gsap.com/docs/v3 (v3.15)".
- `motion` via `"motion/react"`: AnimatePresence, `layoutId`, gestures, scroll values, "Verified against motion.dev"; never `framer-motion`.
- `lenis` (`lenis/react`): smooth scroll on the GSAP ticker; `animejs` v4: light SVG and UI timelines, "Verified against animejs.com/documentation (v4)".
- `z-proximity-engine` (peers `gsap ^3.15`, `@gsap/react ^2.1`): cursor-proximity effects; UI TripleD, UseLayouts, `goey-toast` v0.4.0: components to restyle.

## Which variant for which product
- Calm internal tool: easing palette, timing table, `layoutId` nav pill, AnimatePresence panels, toasts "only on real state changes", access gates, QA checklist.
- Marketing sites only: Lenis, preloaders, custom cursors, magnetic and ZProximity effects, pinned or horizontal scroll, scroll video, theme-shift, 9vw-17vw type, marquees.
- Direct skill call: a single effect; studio team (director, architect, four parallel specialists, QA gate): any multi-section build.
- `/antislopui:define`, `plan`, `build`, `redesign`: documented in the README, with no command files in the repo at d12026c.

## Steal this
- **Signature-move budget.** Have the agent name 2-3 signature moves and one easing signature up front; everything else stays quiet.
- **QA gate subagent.** Finish with a reviewer that checks each API against docs, runs `tsc --noEmit`, and returns ship or no-ship by severity.
