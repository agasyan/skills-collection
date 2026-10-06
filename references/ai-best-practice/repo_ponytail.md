# Ponytail
A "lazy senior dev" coding skill. Stop at the first rung of a reuse-before-write ladder, and never cut safety.
Source: github.com/DietrichGebert/ponytail @ 552acd5 (2026-10-05)

## Rules
- **The ladder.** Stop at the first rung that holds: need it, codebase, stdlib, native platform, installed dep, one line, minimum.
- **Read first.** Trace the real flow end to end before climbing. The ladder shortens the solution, not the reading.
- **Root cause.** Grep every caller of the function you touch and fix the shared function once.
- **Safety floor.** Always keep trust-boundary validation, data-loss handling, security, accessibility and anything explicitly requested.
- **Default, then ask.** Ship the lazy version and question the rest in the same reply instead of stalling.
- **One check.** Non-trivial logic leaves one runnable check: an assert self-check or one small test file.
- **Mark the corner.** Tag deliberate shortcuts `ponytail: <ceiling>, <upgrade path>` so `/ponytail-debt` can collect them into a ledger.

## Output
- **Code first.** Then at most three short lines: `[code] → skipped: [X], add when [Y].`
- **Review format.** `/ponytail-review` and `/ponytail-audit` emit numbered `<N>. L<line>: <tag> <what>. <replacement>.` lines.
- **Tags.** `delete:`, `stdlib:`, `native:`, `reuse:`, `yagni:`, `shrink:`. Each finding names its replacement.
- **Scoring.** End with `net: -<N> lines possible.` If there is nothing to cut, print `Lean already. Ship.` and stop.
- **Levels.** `lite` names the lazier option, `full` enforces the ladder, `ultra` challenges the requirement first.

## Steal this
- **Operational verbs.** Phrase steps as tool actions like "grep every caller". In tests, only that wording changed model behavior.
- **Frame the right move as lazier.** Present the root-cause fix as the smaller diff so the model's instinct pulls toward it.
- **Numbered findings.** Number every finding so the user can reply "fix 2 and 5".
- **Named floor.** List what must survive. A bare "YAGNI + one-liners" prompt dropped a path-traversal guard.
- **Tagged deferrals.** A grep-able marker naming the limit and the trigger to revisit becomes a ledger. Flag markers with no trigger as `no-trigger`.
- **Edit on evidence.** Add skill text only when a test shows it moves the result. Extra counter-rules made small models worse.
- **Single-step rules.** One-step rules transferred to Haiku. The two-step "grep callers, fix the shared function" rule worked only on Sonnet and Opus.
- **Carry rules into subagents.** Context injected at session start never reaches spawned subagents, so inject the rules into each one.
