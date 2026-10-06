# Audit an LLM-Built System
An LLM guesses where it should ask, adds what nobody asked for, and drifts from how staff actually work. Audit the system against the real workflow, never against its own spec.
Source: 14 notes in `sources/` (2026-10-06). A tag like `[Wu 2025]` names the note that backs the rule; an untagged rule is house style.

## Why LLM-built systems drift
- **They guess instead of asking.** On deliberately flawed specs, over 60% of answers were code, not questions; ChatGPT asked 14.21% of the time. [Wu 2025]
- **They misread and add.** Misreading the task was the top bug (20.77%); 8.15% of bugs were features nobody asked for, most in the strongest model (11.76%). [Tambon 2025]
- **They overbuild by default:** extra files, needless abstractions, unrequested flexibility, and hard-coded values that pass tests. [Anthropic]
- **They duplicate.** Commits with duplicated blocks rose from 0.45% to 6.66% (2022–2024). [GitClear 2025]
- **They invent and weaken dependencies.** 19.7% of 2.23M package references didn't exist [Spracklen 2025]; about 40% of Copilot programs were vulnerable. [Pearce 2022]
- **They feel faster than they are.** Experienced developers were 19% slower with AI and believed they were 20% faster. [METR 2025]

## Audit steps
1. **Ground truth from observation, not descriptions.** In order of strength:
   - **Watch it done:** contextual inquiry, interview then watch on site, through one real run of the job the current way.
   - **Read the records:** last month's spreadsheets, email threads, and forms show the real fields, statuses, and exceptions.
   - **Sample the activity:** which tasks, how long, how often; or ask for critical incidents, the last time it went wrong.
   - **Interview to explain what you saw,** never as the only source: "do not rely solely on self-reported behavior".
   Write the task breakdown from these, conditional steps included. The builder's or the LLM's description is a simulation, not observation. [NN/g 2020] Assumptions surface "from documentation, interviews, and observation". [Dewar 1993]
2. **Pre-mortem with users.** "Six months from now nobody uses this tool. Why?" Two minutes, written, before discussion; each reason becomes an audit item. Reasons only users raise point at assumptions the build never tested. [Klein]
3. **Trace both ways.** Map every screen, field, status, job, and setting to the task or rule it serves. No source = orphan: delete it unless an owner claims it with a written purpose. A real step with no element = gap. [NASA 2022]
4. **Hunt assumptions.** List every assumption in the code, schema, and prompts: who approves, what a record holds, which order steps run. A business rule nobody can say who stated is a guess. [Wu 2025] Check the important ones with staff; one nobody confirms was invented. [Dewar 1993]
5. **Compare the flows.** Draw the same task in the system; count steps against the manual way; mark added steps, missing conditions, and forced order. [NN/g 2020] Log each misfit from end users as a deficiency (the tool lacks it) or an imposition (the tool forces it), and count workarounds: side sheets, admin overrides, re-keying. [Jegorova 2025]
6. **Replay real cases.** Export system logs, or a few weeks of the manual tracker, and replay them against the enforced flow. Cases finished through overrides mark a misfit; states no case reached are cut candidates. In one town hall, only 1 of 4 processes fully conformed. [Rozinat 2008]
7. **Check the code.** Run a clone detector and keep one place per business rule [GitClear 2025]; verify every dependency on the official registry (publisher, age, downloads) [Spracklen 2025]; run static analysis and hand-check SQL, file paths, hashing, and auth [Pearce 2022]; search for hard-coded values that match test data and scripts nothing calls. [Anthropic]
8. **Measure, don't trust impressions.** Use task timings and logs over the owners' sense of time saved. [METR 2025] Test 5 staff per role on real tasks (see `../cloudflare-free-ref/ui-internal-system-design.md`).
9. **Feature audit after launch.** Plot each feature by how many people use it and how often, over a full business cycle; ask non-users why, then kill the unclaimed ones. [Intercom]

## Decide
- **The real workflow is the baseline.** For each misfit, default to changing the tool, not the people's process. [Jegorova 2025]
- **Prefer the smallest flow that fits every real case.** [Rozinat 2008]
- **Sort every item:** Keep (traced and used), Fix (traced, but a misfit), Delete (orphan or unused), Ask (an assumption nobody can confirm).

## Prevent it next time
- **Make the builder ask.** Models rarely ask on their own [Wu 2025]; whether Claude asks or guesses depends on the prompt. [Anthropic] Give it the observed task breakdown and real records, and require an assumptions list before any code.
- **State the scope rule in the build prompt:** the minimal solution, no features or files beyond the request. [Anthropic]
