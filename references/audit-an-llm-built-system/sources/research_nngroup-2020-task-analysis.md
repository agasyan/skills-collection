# Task Analysis: Support Users in Achieving Their Goals
Maria Rosala (2020). Nielsen Norman Group. https://www.nngroup.com/articles/task-analysis/
Type: research · Read: 2026-10-06
Evidence: none cited

## What it says
- Task analysis is "the systematic study of how users complete tasks to achieve their goals"; a task is observable and has a start and an end.
- It covers one user and her goal. Workflow analysis covers "how work gets done across multiple people"; job analysis covers a role over weeks or months.

## Findings
- **Wrong problem.** "a design that solves the wrong problem (i.e., doesn't support users' tasks) will fail, no matter how good its UI."
- **Data sources.** Contextual inquiry (interview, then watch on site), critical-incident interviews, diaries and records, activity sampling (which tasks, how long, how often), simulations.
- **Observe, do not simulate.** "do not rely solely on self-reported behavior (i.e., through interviews or surveys) or simulations (remember: you are not the user!)".
- **HTA diagram.** Goal at the top, operations below, subtasks below those. "Plans" record step order and conditional steps, such as a reset only when a password is forgotten.
- **What to check.** Number of tasks ("Are there too many?"), frequency, cognitive complexity, physical demands, time taken.
- **Experts skip steps.** "a novice user might perform more tasks than an expert user"; one fixed sequence does not suit both.

## For auditing an LLM-built system
- Before opening the tool, watch people do the job the current way (spreadsheet, email, paper) and draw the HTA of the real task, including its conditional plans.
- Draw the HTA for the same goal in the built system. Compare step counts and mark added steps, missing conditions and steps forced into a fixed order.
- For handoffs and approvals, add a workflow analysis; task analysis covers one person only.
- Do not accept the builder's or the LLM's description of the task as the model; that is a simulation, not observation.
