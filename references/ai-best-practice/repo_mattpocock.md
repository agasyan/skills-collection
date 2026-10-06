# Skills For Real Engineers (mattpocock/skills)
Small, composable Claude Code skills: grill to align, slice into tracer bullets, build test-first; precise wording steers the agent.
Source: github.com/mattpocock/skills @ 4588b32 (2026-10-05)

## Writing for agents
- **Leading word.** Anchor a behaviour with one pretrained term like tracer bullet, fog of war, or red.
- **No-op test.** Delete every sentence the model already obeys by default; swap weak words for stronger ones like relentless.
- **Positive phrasing.** Name the behaviour you want; a prohibition puts the banned behaviour into context.
- **Completion criterion.** End every step on a checkable, demanding done-condition; vague bounds invite premature completion.
- **Context pointer.** A skill description's wording decides when it fires: leading word first, one trigger per branch.
- **Progressive disclosure.** Inline what every branch needs; move branch-only reference to a linked file.
- **Environment over cache.** Let the agent look up what the repo already states; write down only unwritten conventions and reasons.

## Skills worth copying
- **grilling.** Interview in rounds over a design tree until every branch is resolved and the user confirms.
- **to-tickets.** Cut work into tracer-bullet vertical slices, each with blocking edges, sized for one fresh context window.
- **tdd.** Confirm seams first, then loop one red test and minimal green code; refactoring belongs to review.
- **diagnosing-bugs.** Build one tight command that goes red on the exact symptom before forming any hypothesis.
- **wayfinder.** Chart work too big for one session as decision tickets; keep still-fuzzy questions in the fog of war.
- **handoff.** Write a summary for a fresh agent that links existing artifacts and names the skills to load.

## Steal this
- **Recommended answer.** Number every question and attach your recommended answer, so the user mostly confirms.
- **Frontier round.** Ask every question whose prerequisites are settled at once; dependent questions wait for the next round.
- **Facts vs decisions.** Look up facts yourself or with a subagent, asking other questions meanwhile; bring the user only decisions.
- **Highest seam.** Test at the fewest, highest seams, ideally one, and confirm them before any test is written.
- **Prefactor first.** Make the change easy, then make the easy change.
- **Wrapper skill.** Mark hand-fired skills disable-model-invocation to cost zero context; grill-me is one line calling grilling.
