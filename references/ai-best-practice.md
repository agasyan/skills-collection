# AI Best Practice
How to write skills, prompts, and agent instructions a model follows reliably at low cost.
Source: 7 repo notes in `ai-best-practice/` (fresh clones, 2026-10-06).
A tag like `[ponytail]` names the `ai-best-practice/repo_*.md` note that backs the rule. An untagged rule is house style.

## Size
- **Short wins.** Core skills run 7–16 lines [mattpocock]; frequently loaded skills stay under 200 words [superpowers]; the system prompt is a few lines plus skills loaded on demand [pi].
- **No-op test.** Delete any sentence the model obeys anyway [mattpocock]; every sentence must change a decision [oh-my-pi].
- **Edit on evidence.** Run the task without the skill, record the shortcuts, write rules against those only [superpowers]. Extra counter-rules made small models worse [ponytail].
- **Ties go to shorter** [superpowers]. If a trial compression saves under 10%, keep the original [oh-my-pi].
- **Set length in lines or words**; `effort` changes depth, not length.

## Frontmatter and description
- **Fields:** `name` (= folder = `/command`), `description`, optional `argument-hint`, `disable-model-invocation`, `allowed-tools`.
- **Description = when to use + what it returns.** Leave the workflow out; the model follows the summary and skips the body [superpowers] [pi].
- **Compress the body, not the trigger.** Keep the description natural and keyword-rich [oh-my-pi]. Plain "Use when…" beats "CRITICAL: you MUST".
- **`disable-model-invocation: true`** costs zero context; the user calls the skill by name [mattpocock].
- **One skill, one folder.** No shared files between skills.

## Wording
- **Leading words.** One familiar term (tracer bullet, red) anchors a behavior [mattpocock].
- **Say the positive**; a ban primes the banned thing [mattpocock]. Pair any NEVER with what to do instead [oh-my-pi].
- **Operational verbs.** "Grep every caller" changed behavior; "trace the flow" didn't [ponytail].
- **Single-step rules for small models.** One-step rules held on Haiku; two-step rules only on Sonnet and Opus [ponytail].
- **Binary, countable rules.** "Zero X" holds; "use sparingly" gets skimmed [taste-skill].
- **Critical rules at both edges**; the middle gets the least attention [oh-my-pi].
- **Persist, never budget.** "Be efficient with tokens" causes early quitting [oh-my-pi].

## Questions
- **Facts are the agent's, decisions are the user's.** Look up what can be looked up; ask only decisions, each with a recommended answer [mattpocock] [oh-my-pi].
- **Default, then ask.** Ship the default and let the user override it [ponytail].
- **One decision per question**; omit the questions section when nothing blocks [pi].

## Output
- **Fixed shape.** List the sections in order; for wrong-shaped output, a recipe beats a list of bans [superpowers] [pi].
- **Checkable done.** "Every caller accounted for" drives work; a vague bound invites quitting early [mattpocock].
- **Evidence before claims.** Run the command that proves it; "review your work" proves nothing [superpowers] [oh-my-pi].
- **Pre-flight checklist** of countable boxes; one unticked box means not done [taste-skill].
- **Ban placeholders by name:** `TODO`, `// ...`, "for brevity", "the rest follows the same pattern" [taste-skill].
- **Replies to humans** lead with the next action and end with one concrete next step, no preamble or recap [i-have-adhd].
- **Name the safety floor:** validation at trust boundaries, data-loss handling, security. A bare "YAGNI" prompt dropped a path-traversal guard [ponytail].

## Agents and loops
- **Subagents start blank.** Paste the rules they need; session-start context never reaches them [ponytail] [oh-my-pi].
- **Each spawn carries** the objective, inputs as file paths, output format and size, the done criterion, and how to report a blocker. Return summaries, never raw traces.
- **Status codes:** `DONE`, `DONE_WITH_CONCERNS`, `BLOCKED`, `NEEDS_CONTEXT` [superpowers].
- **Cap delegation;** spawn only for large, independent work. Cheap models take 2–3× the turns, so turn count beats token price [superpowers].
- **Drop "double-check your work."** Keep human gates, tool loops, and fresh-context reviewers.
- **Loop only when a tool can say "done".** Cap rounds, one change per round, stop on a repeated failure, never edit the failing test in the round that fixes it.
