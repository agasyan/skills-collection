# Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity
Joel Becker, Nate Rush, Elizabeth Barnes, David Rein (2025). METR, arXiv:2507.09089. https://arxiv.org/abs/2507.09089
Type: research · Read: 2026-10-06

## What it says
- Randomized controlled trial: 16 experienced developers, 246 real issues (about 2 hours each) in repos they had worked on for 5 years on average; repos averaged 10 years old and over 1.1 million lines.
- Each issue was randomly assigned AI-allowed or AI-disallowed. AI meant mainly Cursor Pro with Claude 3.5/3.7 Sonnet, Feb to June 2025.

## Findings
- **Slower with AI.** AI-allowed issues took 19% longer (CI +2% to +39%).
- **Felt faster.** Developers forecast a 24% time saving and afterwards still believed AI had saved 20%. Economics and ML experts predicted 39% and 38% savings.
- **Low acceptance.** Developers accepted under 44% of AI generations and spent 9% of their time reviewing and cleaning AI output; 56% often made major changes to AI code.
- **Missing tacit knowledge.** Developers said AI lacks undocumented codebase knowledge: "AI doesn't pick the right location to make the edits," and it cannot know a backwards-compatibility case staff keep in their heads.
- **More code.** AI-allowed issues produced 47% more lines per forecasted hour (effect on slowdown unclear).
- **2026 update.** A late-2025 rerun estimated 18% less time for returning developers (CI -38% to +9%), but METR calls the data unreliable: 30–50% of developers withheld tasks they would not do without AI. https://metr.org/blog/2026-02-24-uplift-update/

## For auditing an LLM-built system
- Treat the owners' sense of time saved or quality as unverified; measure with logs, tickets, or task timings.
- List the unwritten rules staff follow (exceptions, legacy cases, workarounds) and check the system against each; this is the knowledge the model lacked.
- Check whether changes landed in the right layer or module, not only whether they work.
