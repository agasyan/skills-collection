# Better Design with AI
"Every model trained on the same SaaS templates." Give the agent product context, a committed direction, binary bans, and a check after building, and build from libraries that are widely used and recently released.
Source: 8 notes in `sources/` (2026-10-07). A tag like `[impeccable]` names the note that backs the rule; an untagged rule is house style. Per-repo file: `design-md-template.md`.

## Before the agent writes code
- **Product truth first.** Users, purpose, and operating context go in a product file; the visual system goes in `DESIGN.md`, following the Google Labs spec. [impeccable] [DESIGN.md spec]
- **State the read in one line:** "Reading this as: {page kind} for {audience}, with a {vibe} language." [taste-skill]
- **Pick the mode.** Apps, dashboards, and tools are Operate surfaces: style lends only type, palette, density, and one signature move; controls stay standard. [impeccable]
- **Set three dials:** layout variance, motion intensity, visual density. Internal tools want low, low, and high. [taste-skill]
- **Commit to a direction.** Brief the agent as a studio lead whose client "has already rejected proposals that felt cliché or templated"; write a token plan before code. [frontend-design]
- **Use the real design system** when the brief reads as one (Carbon, Material, Fluent, GOV.UK, shadcn). [taste-skill]
- **Mock with real content:** realistic values, real labels, one state worth seeing, never placeholder tiles. [impeccable]

## Ban the tells
- **The usual tells:** Inter for everything, purple-to-blue gradients, cards nested in cards, gray text on colored backgrounds, a rounded-square icon tile above every heading. [impeccable] Also three equal cards, neon glows, fake round numbers, "Elevate" or "Seamless" copy, and emoji. [taste-skill]
- **Phrase bans as "zero X"**, never "use sparingly"; soft wording gets skimmed. [taste-skill]
- **"Generic motion is worse than no motion."** [antislopui] Product transitions run 150–250 ms and convey state only. [impeccable] Use plain CSS for a simple hover or fade. [emil]
- **Keep accessibility out of the design prompt** and check it in the audit; design-time reminders produce "safe, underdesigned output". [impeccable]

## Check after building
- **Run a detector.** `npx impeccable detect` runs 60 deterministic rules on files or URLs, with no LLM or API key. [impeccable]
- **Critique from screenshots**, then fix. [frontend-design] End with a countable pre-flight checklist. [taste-skill]
- **Break it on purpose:** long names, huge numbers, empty lists. Fix with `min-width: 0`, `tabular-nums`, and `Intl.NumberFormat`. [emil]
- **Check every library API against current docs**; agents invent plausible ones. [antislopui]

## Libraries: widely used and released in the last six months
Numbers are weekly npm downloads and latest release, measured 2026-10-07. [npm 2026-10] On Cloudflare's free plan, `cloudflare-free-limitation.md` says which of these run in the browser and which may run in the Worker.
| Need | Pick | Evidence |
|---|---|---|
| Styling | Tailwind CSS 4 | 163M/wk, 4.3.3 (Jul 2026); taste-skill asks for v4 [taste-skill] |
| Components | shadcn/ui on Radix or Base UI | shadcn 13M/wk (Oct 2026); `radix-ui` 1.7.0 and `@base-ui/react` 1.8.0, both released this quarter [emil] |
| Full kit instead | Mantine, MUI, or Ant Design | 9.7.1 (Oct), 9.4.0 (Aug), 6.6.5 (Sep 2026) |
| Icons | Tabler | 3.49.0 (Oct 2026) and on taste-skill's list; Phosphor ranks first there but has no release since May 2025; taste-skill uses `lucide-react` only on request [taste-skill] |
| Motion | `motion` 14 (`motion/react`) | 28M/wk, Oct 2026; `framer-motion` is the old name [emil] |
| Toasts / command menu | sonner / cmdk | 63M/wk (Aug 2026) / 55M/wk but no release since Mar 2025 [emil] |
| Tables and server data | TanStack Table + TanStack Query | 9.2.6 and 5.104.1, both Oct 2026 |
| Forms | react-hook-form + zod | 7.89.0 and 4.6.5, Sep 2026 |
| Charts | recharts | 71M/wk, 3.10.1 (Jul 2026) [emil] |
| Fonts | Geist and Geist Mono | OFL, 1.7.2 (Jun 2026) [taste-skill] |
| Class names | clsx, tailwind-merge, cva | small, stable utilities [emil] |

Avoid for new UI: vaul (no release since Dec 2024), Heroicons (Nov 2024), and the deprecated `@base-ui-components/react`. GSAP 3.15 is free under a "no charge" license, not open source; save it for scroll-heavy marketing pages.

## Where the sources disagree
- **Custom cursors and theme changes mid-scroll:** taste-skill bans them; AntislopUI uses them as signature moves. For internal tools, ban them.
- **GSAP with Motion:** taste-skill says "NEVER mix GSAP / Three.js with Motion in the same component tree"; AntislopUI allows both if they never drive the same property. Pick one per app.
- **taste-skill's variants contradict its main skill** on serif fonts, eyebrow pills, and looping card animations; follow the main skill.
- **AntislopUI admits some APIs are unverified**, and it targets award-style marketing sites; take its motion discipline, not its effects, into a working tool.
