# What We Don't Know About Spreadsheet Errors Today: The Facts, Why We Don't Believe Them, and What We Need to Do
Raymond R. Panko (2015). EuSpRIG 2015 Conference Proceedings. https://arxiv.org/pdf/1602.02601
Type: research · Read: 2026-10-06

## What it says
- Review of spreadsheet error research (lab experiments and field inspections) set against human error research from software, writing, and other fields.

## Findings
- **Small per cell, near certain per sheet.** 14 lab studies with 967 people working alone averaged a 3.9% cell error rate, inside the 1% to 5% range seen for writing, calculating, and coding. With 100 cells in cascades, the chance of a wrong bottom line is "overwhelming."
- **Real sheets are wrong.** Intensive inspections of 85 operational spreadsheets found errors in 94% of them.
- **Errors are hard to find.** Nine experiments with over 1,000 participants found a 60% average detection rate. In one study individuals caught 63% of errors and teams of three 83%. Audit software caught 27% of seeded errors.
- **Error types.** One experiment found 45% logic errors, 23% mechanical (wrong cell, typo), and 31% omission (a needed part left out).
- **Experience barely helps.** Novices err at most about twice as often as experienced staff, and error rates stop falling after about six months.
- **Overconfidence.** Developers and firms are highly overconfident because people notice few of their own errors.
- **Testing is the fix.** Software projects spend 27% to 34% of resources on testing (40% to 60% at Microsoft); detailed spreadsheet inspection is rare.

## For internal systems
- Move calculations that feed decisions into tested system code; users enter inputs, not formulas.
- Validate at entry (types, ranges, required fields) to block the mechanical and omission errors that reviewers miss.
- Expect errors in the sheets being migrated: reconcile totals between sheet and system before retiring the sheet.
- Do not accept "the sheet has worked for years" as proof; confidence is not accuracy.
