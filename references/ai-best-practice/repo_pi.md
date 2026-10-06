# Pi
Minimal, extensible coding-agent harness: a tiny core prompt, with everything else added on demand.
Source: github.com/earendil-works/pi @ 28dcce2 (2026-10-05)

## Philosophy
- **Minimal core.** The system prompt is one identity line, one-line tool snippets, a few rules, AGENTS.md, and a skill index.
- **Rules ride with tools.** Each tool adds its own guideline lines only while that tool is enabled.
- **Load on demand.** The prompt lists each skill's name, description, and path; the model reads the file when needed.
- **Least powerful mechanism.** Reach for AGENTS.md first, then a prompt template, then a skill, then an extension.

## Prompts and skills
- **Description routes.** State what the skill does and when it applies; "Helps with PDFs" gives no routing signal.
- **Templates are plain prompts.** The filename becomes the command; `$ARGUMENTS` or `${1:-default}` fills user input.
- **Fixed output shape.** `pr` fixes its sections: What it does, Good, Bad, Ugly, Tests, Open questions for you.
- **Analyze, then act.** `is` and `pr` analyze and propose only; `wr` handles changelog, commit, and push.
- **Chain by name.** `release` asks whether `/cl` ran first; `wr` reuses context already gathered by `/is` or `/pr`.
- **Gate only what matters.** `deslop` lists which removals need approval and lets routine cleanup proceed without asking.

## Steal this
- **Read in full.** `is`: "Read all related code files in full (no truncation)."
- **Verify claims yourself.** `is`: "Ignore any root cause analysis in the issue (likely wrong)." Then trace the code path.
- **Hard stop.** `is`: "Do NOT implement unless explicitly asked. Analyze and propose only."
- **Ask only when blocked.** `pr`: "only things blocking a merge decision... Omit the section entirely if there are none."
- **One decision per ask.** `deslop`: "Do not bundle approval for multiple independent decisions."
- **Scope in one line.** `deslop`: "simplify its implementation without changing its intended behavior." Then: "Do not perform unrelated cleanup."
- **Define done.** `interactive-testing`: "startup alone is not a passing smoke test."
- **Admit what you skipped.** `sa`: "Never pretend comments were read."
- **Explain with a trace.** AGENTS.md: explain designs as problem, concrete example or short trace, then solution.
