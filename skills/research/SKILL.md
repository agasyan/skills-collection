---
name: research
description: Sharpen a rough ask into what the user wants, what they actually need, and what is wrong today, plus how others solve it per web best practice. Step 1 of sharpen → outline → steps. Prefer /sharpen for obvious changes.
argument-hint: "[ask, constraints, or idea]"
disable-model-invocation: true
allowed-tools: WebSearch, WebFetch
---

Help the user see what they want, what they need, what is wrong now, and how others solve it. Open with one line: "Reading this as: {outcome} for {who}, within {constraint}."

Facts are yours. Read any matching `docs/flows/{slug}/` docs first, then find code facts with grep and read. Then search the web for how others meet the need: official docs, the libraries this repo already uses, well-known open-source projects, standards, and peer-reviewed or measured studies. Open every source you cite and take each number from the page, never from memory. Match versions to what the repo pins. Stop when two independent primary sources agree, or after about 8 fetches.

Decisions are the user's. Ask only those still blocking after the research: one decision per question, 2–4 options with the recommended one first, at most 3 in one `AskUserQuestion`. Everything else gets a default you state.

Write `.plans/{YYMMDD}-{slug}/1-sharpen.md`:

- **Want:** what the user asked for, in one sentence.
- **Need:** the outcome that must be true for them. When it differs from the want, or best practice points elsewhere, say how and which serves them better.
- **Wrong now:** what is broken, missing, or painful today, with `path:line`, a flow-doc step, or observed behavior. If the code already does what they want, say so here.
- **Done when:** checkable outcomes of the need. For a screen, a task a user completes, with its completion, time, or error target.
- **Constraints** and **Non-goals**.
- **Prior art:** 2–4 approaches, each with how it works, its cost, and a link.
- **Best practice** and **Pitfalls:** what the sources agree on and warn about, each with a link. Mark opinion with no data `opinion`.
- **Assumptions:** `Default: X, because Y`, each with `path:line`, a link, or a one-line reason. The user overrides them here.
- **To check:** facts the code must settle before planning, each with your guess.

Mark a claim backed by a single secondary source `⚠️ one source`. Stay on the problem; the design belongs to `/outline`. Write about 80% of the way to ASD-STE100: answer first, one word per meaning, the project's own terms, no hype or hedges. End with `/outline .plans/{folder}`.
