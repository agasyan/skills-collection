# Conformance Checking of Processes Based on Monitoring Real Behavior
A. Rozinat, W.M.P. van der Aalst (2008). Information Systems 33(1), 64-95. https://vdaalst.com/publications/p436.pdf
Type: research · Read: 2026-10-06

## What it says
- Replays an event log (case ID and activity per event) through a process model to measure and locate mismatches; built as the Conformance Checker in ProM.
- Tested on artificial logs and on real logs of four administrative processes at a Dutch town hall that ran a workflow system.

## Findings
- **Fitness.** Can the model replay every observed trace? Scored 0 to 1; a log and model "may have a fitness of 0.66".
- **Fitness alone misleads.** A "flower" model that allows any order fits 100% and says nothing; a model that lists each observed sequence also fits and explains nothing.
- **Behavioral appropriateness.** Penalizes behavior the model allows but the log never shows; an over-general model "may allow for unwanted execution sequences".
- **Structural appropriateness.** Occam's razor: "if a simple model can explain the log, why choose a complicated one". Duplicate tasks, invisible tasks and implicit places inflate a model.
- **Real work deviates.** Only 1 of 4 processes was fully compliant (358 cases). Building permits: 80% of 407 cases (a misconfiguration). One complaint process: 51% of 35 cases; staff had the administrator re-edit closed cases or jump tasks, working "behind the back" of the system.
- **Unused paths.** A cancel step allowed in almost every state was only used early. Even when everything fits, check how often each part runs and "remove obsolete parts".
- **Two readings.** A deviation means people broke the process, or the model is "outdated or just not tailored to the needs of the employees". A domain expert decides which.

## For auditing an LLM-built system
- Export the system's own logs, or a few weeks of the manual tracker, as case, step and time; replay them against the flow the system enforces.
- Count cases finished only through admin overrides, re-edits or off-system steps; each one marks a flow the system does not fit.
- List states, branches and statuses that no real case reached; they are cut candidates.
- Prefer the smallest flow that still fits every real case.
