---
name: sharpen
description: Sharpen a rough ask into what the user wants, what they actually need, and what is wrong today, from docs and code only, no web search. Step 1 of sharpen → outline → steps. Prefer /research when best practice matters.
argument-hint: "[ask, constraints, or idea]"
disable-model-invocation: true
---

Help the user see what they want, what they need, and what is wrong now. Open with one line: "Reading this as: {outcome} for {who}, within {constraint}."

Facts are yours: read any matching `docs/flows/{slug}/` docs first, then grep and read the code. Decisions are the user's. Ask only those that block the requirement: one decision per question, 2–4 options with the recommended one first, at most 3 in one `AskUserQuestion`. Everything else gets a default you state.

Write `.plans/{YYMMDD}-{slug}/1-sharpen.md`:

- **Want:** what the user asked for, in one sentence.
- **Need:** the outcome that must be true for them. When it differs from the want, say how, and which serves them better.
- **Wrong now:** what is broken, missing, or painful today, with `path:line`, a flow-doc step, or observed behavior. If the code already does what they want, say so here.
- **Done when:** checkable outcomes of the need. For a screen, a task a user completes, with its completion, time, or error target.
- **Constraints** and **Non-goals**.
- **Assumptions:** `Default: X, because Y`, each with `path:line` or a one-line reason. The user overrides them here.
- **To check:** facts the code must settle before planning, each with your guess.

Stay on the problem; the design belongs to `/outline`. Write about 80% of the way to ASD-STE100: answer first, one word per meaning, the project's own terms, no hype or hedges. End with `/outline .plans/{folder}`.
