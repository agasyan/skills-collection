# Assumption-Based Planning: A Planning Tool for Very Uncertain Times
James A. Dewar, Carl H. Builder, William M. Hix, Morlie H. Levin (1993). RAND Corporation, report MR-114, prepared for the US Army. https://www.rand.org/pubs/monograph_reports/MR114.html
Type: research · Read: 2026-10-06
Evidence: none cited (method report; success judged by Army planners finding it useful)

## What it says
- A method RAND developed over four years for Army long- and mid-range planning: start from the assumptions current plans rest on, not from a forecast of the most likely future.
- Notes cover the report's summary (pp. xi to xv); the scanned PDF has no text layer.

## Findings
- **Step 1: important assumptions.** An assumption is "important if its negation would lead to significant changes" in the plan. Few organizations write them down; find them "from documentation, interviews, and observation". Implicit ones appear "only upon reflection and study".
- **Step 2: vulnerabilities.** Set a time horizon first. An assumption is vulnerable when a plausible change within that horizon would break it; record every way it can fail.
- **Step 3: signposts.** An event or threshold that "clearly indicates" an assumption is weakening; it must be unambiguous.
- **Step 4: shaping actions.** Act to keep a vulnerable assumption true, or to make it fail when that helps.
- **Step 5: hedging actions.** Replan "as though" the assumption had failed, to keep options open now.
- **Order.** Steps 1 and 2 come first; steps 3 to 5 can run in any order. Stopping before step 5 still helps.
- **Where it pays.** More useful on mature, resource-constrained plans; tentative plans hide the critical trade-off assumptions.

## For auditing an LLM-built system
- Read the code, schema, prompts and specs; list every assumption about users, data and process (who approves, what a record holds, which order steps run in).
- Mark each one important if breaking it would change the design, then check it against interviews and observation of the people doing the work. An important assumption nobody can confirm was invented.
- For each vulnerable assumption you keep, name a signpost to watch (such as a count of manual overrides) and decide: shape it, hedge it, or remove the code that depends on it.
