---
name: migrate
description: Plan how a captured manual workflow migrates into a system that follows the current approach, phase by phase. Use after /capture. Then build each phase with sharpen → outline → steps.
argument-hint: "[docs/flows/{slug}, default newest]"
disable-model-invocation: true
---

Read `capture.md`. Plan a system that follows the current approach: keep each step, actor, rule, state, and word as it runs today. Change one only where a pain point justifies it, and name that pain point.

For each step, stop at the first rung that holds: stays manual → a feature of a tool already in use → a small script → app code. If a repo exists, use its stack; otherwise state the simplest stack that fits as a default. Ask the user only when a step can migrate two ways with different costs: one decision per question, at most 3 in one `AskUserQuestion`, recommended first.

People who only know email, Word, and Excel adopt a tool because it is useful, so phase 1 removes their most tedious step, shown on their own data. Keep their habits: tables that sort, filter, copy, and export to Excel like a sheet; tasks and approvals that arrive by email with a link to the record; every record showing who it is waiting on. Their old sheets hold errors: move calculations into tested code, validate at entry, and reconcile totals before a sheet retires.

Write `docs/flows/{slug}/migration.md`:

- **Step map:** a table of current step → system piece (form, table, job, email notification, report, or stays manual) → rung → pain point it fixes.
- **Data move:** where each record lives today → where it lives in the system, how existing records come across, and the totals to reconcile.
- **Phases:** phase 1 systemizes the worst pain point end to end while the rest stays manual. Each phase lists what moves, what stays manual, the hand-off between them, the check that lets you stop the manual way, and how to fall back to it.
- **Rules kept:** each current rule → where the system enforces it.
- **Adoption:** a peer champion per team, who tries each phase first, and the 3–5 core tasks to test with 5 staff before the manual way stops.
- **Personas:** each persona goal → the phase that serves it.
- **Deviations:** every place the system departs from today's way, each with its pain point.
- **Risks:** every open `Guess:` from `capture.md`, each as "if X turns out true, do Y instead".

Write about 80% of the way to ASD-STE100: answer first, headings that name the content, one word per meaning, the staff's own terms, no hype or hedges. End with `/research build phase 1 of docs/flows/{slug}/migration.md`.
