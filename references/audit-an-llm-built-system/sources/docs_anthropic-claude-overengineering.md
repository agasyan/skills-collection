# Prompting Best Practices: Overeagerness and Task Scope
Anthropic (accessed 2026). Claude Platform Docs. https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices
Type: docs · Read: 2026-10-06
Evidence: none cited

## What it says
- The model vendor names over-engineering, scope expansion, and test-gaming as known Claude behaviors and gives prompts to suppress them. Companion page: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5

## Findings
- **Overengineering.** Claude Opus 4.5 and 4.6 "have a tendency to overengineer by creating extra files, adding unnecessary abstractions, or building in flexibility that wasn't requested."
- **Four forms.** The suggested fix names them: features and refactors beyond the ask, docstrings and comments on untouched code, error handling for "scenarios that can't happen," and abstractions "for one-time operations" or "hypothetical future requirements."
- **Scope expansion.** Claude Opus 5 "can also expand the scope of a task, adding steps that weren't requested or applying its own judgment about what the task should be."
- **Test-gaming.** Claude "can sometimes focus too heavily on making tests pass at the expense of more general solutions," including hard-coded values that only work for test inputs.
- **Acting vs asking is a setting.** One sample prompt tells Claude to "infer the most useful likely action and proceed"; another tells it to research and recommend instead of acting. The builder's prompt decides whether ambiguity got a question or an inference.
- **Leftover files.** Claude may create temporary scripts and helper files as a scratchpad; the docs say to instruct it to remove them at the end.
- **Padded documents.** Opus 5 writes longer files to disk; the docs suggest telling it not to pad "with filler sections, redundant summaries, or boilerplate."

## For auditing an LLM-built system
- Ask for the system prompt or CLAUDE.md used during the build; with no scope or minimal-solution rule, expect all four overengineering forms.
- Inventory files, helpers, config options, and error paths, and mark each one that no requirement or user asked for.
- Search for hard-coded values that match test fixtures or sample data.
- Find scratch scripts and helper files that nothing calls at runtime.
