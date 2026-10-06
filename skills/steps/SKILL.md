---
name: steps
description: Ground the outline in the code and write the steps: red tests, files with line anchors, actions, and the done command per slice. Step 3 of sharpen → outline → steps.
argument-hint: "[.plans/ folder, default newest] [slice number]"
disable-model-invocation: true
---

Read `2-outline.md`. Open every file each slice touches; the outline's anchors are hints, and HEAD wins. Find the test and lint commands, and one existing sibling to copy for each new file. Grep every caller of anything whose signature or shape changes. If HEAD forces a change to the decision, stop and ask.

Write `3-steps.md`, or only the given slice's section. List **Corrections vs outline** first, then per slice:

- **Red first:** test file › case › input → expected literal. One per edge case in the outline. A slice with screens also gets one per loading, empty, and error state, and one per validation message.
- **Files:** `path` · `Lstart-Lend` or `new` · one-line change.
- **Keeps working:** callers left untouched, and why.
- **Steps:** verb + exact target + new behavior + existing helper to reuse. Signatures only, no bodies. Add `Run:` / `Expected:` where a command proves the step.
- **Done:** the command that goes green.

Before handing off, check:
- The slice count matches the outline, and every slice has a red test and anchors.
- Zero `TODO`, `...`, "etc.", "similar to above", "same pattern for the rest", or "handle errors".
- No flag, fallback, or abstraction that no requirement asks for.

Write steps about 80% of the way to ASD-STE100: one command per step, one word per meaning. End with: `Implement slice 1 of .plans/{folder}/3-steps.md, red tests first.`
