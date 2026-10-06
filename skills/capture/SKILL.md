---
name: capture
description: Capture how a workflow runs today, exactly, manual or partly automated. Step 0 when the current process isn't written down. Next: /migrate.
argument-hint: "[workflow name or description; paste notes, files, or screenshots]"
disable-model-invocation: true
---

Document the workflow as it runs today, not as it should run. The facts live with the user, so start from what they gave: notes, files, screenshots, a description. If they gave nothing, ask for one brain dump: "Walk me through the last time you did this, step by step."

Document the manual steps first; derive everything else from them. Draft the whole capture from that dump, filling every gap with a guess marked `Guess:`. Then ask only what blocks the map: at most 4 questions per `AskUserQuestion`, each with your guess as the recommended answer. Stop when every step has an actor, an input, and an output.

Write `docs/flows/{slug}/capture.md`:

- **Purpose:** trigger → outcome, one line.
- **Actors and tools:** who is involved, where the work lives (spreadsheet, chat, email, paper), the setting (desk, phone, peak hours), and what each tool does well for them.
- **Words:** the terms staff use for records, statuses, and actions, verbatim.
- **Steps:** numbered, each as who · does what · in which tool · input → output. Mark hand-offs `→ {actor}`.
- **Rules:** every "if X then Y" the person applies, including unwritten ones.
- **Volume and time:** how often it runs, how many items, minutes per step.
- **Exceptions:** what happens when something is missing, late, or wrong.
- **Pain points:** slow, repeated, error-prone, or forgotten steps, each with how often it bites.
- **Personas:** per actor, the user first as "me": "As {actor}, I want to {goal}, so that {outcome}." Each names a goal, never a feature, and cites the steps and pain points it comes from.
- **Sketch:** a flowchart when 3+ steps hand off.
- **Open guesses:** every `Guess:` the user hasn't confirmed.

Describe exactly; changes belong to `/migrate`. Write about 80% of the way to ASD-STE100: answer first, headings that name the content, one word per meaning, the staff's own terms, no hype or hedges. End with `/migrate docs/flows/{slug}`.
