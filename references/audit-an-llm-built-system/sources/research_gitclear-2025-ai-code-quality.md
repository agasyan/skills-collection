# AI Copilot Code Quality: Evaluating 2024's Increased Defect Rate via Code Quality Metrics
William Harding, GitClear (2025). GitClear research report. https://www.gitclear.com/ai_assistant_code_quality_2025_research
Type: research · Read: 2026-10-06

## What it says
- Classified 211 million changed lines (Jan 2020 to Dec 2024) from commercial and large open-source repos as added, deleted, updated, moved, copy/pasted, or find/replaced, plus churn.
- Year-over-year trends timed against AI assistant adoption; lines are not tagged as AI or human. Full text: https://docs.google.com/document/d/1KFcI0M-UHTAGdSstqZ4XfHKYM80XcSERfTEl1tXPkj0

## Findings
- **Refactoring is disappearing.** Moved lines, the signature of reuse, fell from 24.8% of changes (2021) to 9.5% (2024).
- **Copy/paste overtook moves.** Copy/pasted lines rose from 8.3% (2020) to 12.3% (2024), the first year they exceeded moved lines.
- **Duplicate blocks surged.** Commits containing a duplicated block of 5+ lines went from 0.45% (2022) to 6.66% (2024).
- **More new code.** Added lines grew from 39.2% (2020) to 46.2% (2024) of all changes.
- **More rework.** Churn (lines reverted or rewritten within two weeks) rose from 3.3% (2021) to 5.7% (2024).
- **Old code left alone.** In 2024, about 20% of modified lines touched code older than a month, against 30% in 2020.
- **Defect link (cited).** Quotes Google DORA 2024: each 25% rise in AI adoption maps to a 7.2% drop in delivery stability.

## For auditing an LLM-built system
- Run a clone detector; count near-identical blocks and functions doing the same job in different places.
- Count how many places implement each business rule; more than one means every fix must land in all of them.
- Check git history for files rewritten within days of creation.
- Look for new parallel modules where an existing one could have been extended.
