# emilkowalski/skill
14 skills from Emil Kowalski (Sonner author; Vercel, Linear) on motion, component polish, and edge cases; core idea: "Agents don't have great taste," so name each small mistake with its exact fix value.
Source: github.com/emilkowalski/skill @ e8a175d (2026-10-02) · MIT · 44k stars

## Before coding
- **Frequency gate.** 100+ times/day gets "No animation. Ever."; tens/day near-imperceptible; occasional standard; rare or first-time earns delight.
- **Name the purpose.** Pick one: feedback, spatial consistency, state indication, preventing a jarring change, explanation, or delight; otherwise skip the motion.
- **Recon first.** Read the stack, package.json, easing and duration tokens, and product personality; extend what exists instead of forking it.

## Design rules
- **Easing by direction.** Ease-out `cubic-bezier(0.23, 1, 0.32, 1)` to enter or exit, ease-in-out `cubic-bezier(0.77, 0, 0.175, 1)` to move, ease for hover.
- **Under 300ms.** Press 100–160ms, tooltips 125–200ms, dropdowns 150–250ms, modals and drawers 200–500ms; UI stays under 300ms.
- **Physical entrances.** Press with `scale(0.97)` on `:active`; enter from `scale(0.95)` plus `opacity: 0`; scale popovers from their trigger.
- **Interruptible, GPU-only.** Animate named `transform` and `opacity` properties; use transitions, not keyframes, for toasts, toggles, and anything rapid.
- **Gate and soften.** Wrap hover in `@media (hover: hover) and (pointer: fine)`; reduced motion means "fewer and gentler", keeping opacity and color.
- **Asymmetric timing.** Slow where the user decides (hold-to-delete 2s linear), fast where the system responds (release 200ms ease-out).
- **Data-proof rows.** Use `min-width: 0` on text columns, `flex-shrink: 0` on avatars and actions, `tabular-nums`, and `Intl.PluralRules`.

## Anti-patterns it names
- **Agent ingredient slips.** `ease-in` on entrances, `transition: all`, `scale(0)`, center-origin popovers, a solid border where a semi-transparent shadow belongs.
- **Animated keyboard actions.** Command palette open and close transitions; "Raycast has no open/close animation".
- **Hand-rolled components.** Toasts built by hand, `<div>` dropdowns with manual focus handling, 1,000+ rows rendered directly.
- **Kind demo data.** UI built against "Jane Doe, jane@acme.com, 12 members" that ships "1 members", squished avatars, and overflowing emails.
- **Website tells on phones.** Stuck hover after tap, gray tap flash, `100vh` app shells, input zoom under 16px, `user-scalable=no`.

## Libraries and tools it recommends
- base-ui, cmdk, Sonner, input-otp, Leva (or dialkit): accessible primitives, ⌘K menus, toasts, OTP inputs, control panels
- motion, NumberFlow, torph, Cobe, Satori, shiki: springs and layout or exit animation, animated numbers, animated text, 3D globes, OG images, syntax highlighting
- recharts, Liveline, dnd kit, Virtuoso: general charts, real-time streaming charts, drag and drop, long lists and large tables
- zustand, clsx, cva, next-themes, easing.dev, easings.co: state, conditional classNames, Tailwind variants, no-flash dark mode, custom curves

## Steal this
- **Review table plus rejects.** Reviews output one `| Before | After | Why |` table; opportunity scans add 2–5 rejected candidates with the gate question that killed each.
- **Worst-case toggle.** Add a dev-only "Demo data / Worst case" fixture (Aleksandra Wiśniewska-Kowalczyk, `bartholomew.fitzgerald@northwind-industries-holdings.example.com`, "Jo", 1,284 members, plus Empty, One, 1,000 rows) and report Broken, Ugly, Fragile.
- **Divergent variants.** Build 3 variants on named axes ("Quiet", "Editorial", "Dense", never "Option A/B/C"), one at a time at full size behind an instant picker; the user picks.
