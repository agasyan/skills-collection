---
name: outline
description: Check a sharpened ask against the code and outline the change at a high level: today's flow, the chosen direction, behavior changes, and slices. Step 2 of sharpen → outline → steps.
argument-hint: "[.plans/ folder, default newest]"
disable-model-invocation: true
---

Read `1-sharpen.md` (newest `.plans/*/` if no folder is given). Plan for the **Need**; the **Want** is one candidate direction. Settle every **To check** item with `path:Lstart-Lend`; mark runtime-only facts ⚠️ Unverified. Treat any cause or fix the ask names as a claim, and confirm it in the code. With a matching `docs/flows/{slug}/migration.md`, follow its step map and phases, and weigh directions only within them. With no code yet, its `capture.md` is **Now** and every file is new. If a check breaks the premise, stop and tell the user.

Weigh 2–3 directions plus doing nothing, drawn from its **Prior art** when present. Pick the one that leaves the least code: doesn't need to exist → already in the codebase → stdlib → installed dependency → new code. Keep validation, data safety, and security whatever it costs.

When a slice has screens, build on an existing design system and label everything with the words staff already use. Tables: the first column is what staff recognise, filters stay visible, edits open in a side panel, multi-row actions sit in a batch bar. Forms: validate on submit and keep every input; also check a field on leaving it when its rule can't be guessed. Every list has distinct loading, empty, and error states. Every workflow ends with a confirmation of what happened. A dashboard is only for repeated monitoring; to find, edit, or act, use a table.

Write `2-outline.md`, under 80 lines. It is done when `/steps` can work from it without making a single design decision.

- **TL;DR:** goal, direction, deciding reason.
- **Checks:** each item ✅ / ❌ / ⚠️ with evidence.
- **Now:** today's flow, cited from code or the flow doc; an ASCII sketch if 3+ parts connect.
- **Decision:** each direction with its cheaper path, its source link if any, and kill reason.
- **What changes:** behavior and contracts. List public changes (URLs, API fields, events, user-facing copy) on their own.
- **Screens:** when the slice has UI, each screen's job, the data it shows, and its actions.
- **Edge cases:** up to 5 inputs or failures the ask doesn't mention, plus its **Pitfalls**; each becomes a red test.
- **Slices:** tracer bullets, prefactor first, each shippable alone and sized for one fresh session, with Blocked-by.
- **Risks:** each as "if X turns out true, do Y instead".

Write about 80% of the way to ASD-STE100: answer first, one word per meaning, the project's own terms, no hype or hedges. End with `/steps .plans/{folder}`.
