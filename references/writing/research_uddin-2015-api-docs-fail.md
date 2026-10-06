# How API Documentation Fails
Gias Uddin, Martin P. Robillard (2015). IEEE Software 32(4). https://www.cs.mcgill.ca/~martin/papers/ieeesw2015.pdf
Type: research · Read: 2026-10-06

## What they did
- Two surveys of 323 IBM software professionals in Canada and the UK.
- Survey 1 (69 people) collected 179 good and bad doc examples from 72 APIs; 79 bad examples were card-sorted into 10 problem types.
- Survey 2 (254 developers and architects) rated each problem's frequency, severity, and fix priority.

## Findings
- **Content beats presentation.** 61 of 86 problem mentions were about content; respondents ranked five content problems above every presentation problem.
- **Most reported.** Incompleteness (20 examples), ambiguity (16), bloat (12), unexplained code examples (10).
- **Six problems make developers quit.** Incompleteness, ambiguity, obsoleteness, incorrectness, inconsistency, and unexplained examples were each rated "Blocker: I picked another API" at least once.
- **Ambiguity is the top fix.** 51.9% gave it top priority; 26.5% of those with an opinion saw it frequently in the past 3 months.
- **Errors are rare but costly.** Incorrect content was seen infrequently yet rated severe or blocking.
- **Layout still hurts.** Bloat (verbose text), fragmentation ("10s of clicks"), and tangled topics hid what readers needed.

## For writing docs
- Complete and disambiguate first: state exactly what each parameter and return value means.
- Explain every code example: its inputs, configuration, and where it runs.
- Keep one topic on one page, cut long intros, and don't mix scenarios in one description.
- Update docs with each API version; stale or wrong docs send developers to another API.
