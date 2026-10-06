# Asleep at the Keyboard? Assessing the Security of GitHub Copilot's Code Contributions
Hammond Pearce, Baleegh Ahmad, Benjamin Tan, Brendan Dolan-Gavitt, Ramesh Karri (2022). IEEE Symposium on Security and Privacy 2022. https://arxiv.org/abs/2108.09293
Type: research · Read: 2026-10-06

## What it says
- Prompted GitHub Copilot (2021) with 89 security-relevant scenarios built on MITRE's 2021 CWE Top 25, in Python, C, and Verilog, producing 1,689 programs.
- Judged each with GitHub CodeQL plus manual review, varying the weakness, the prompt wording, and the domain.

## Findings
- **About 40% vulnerable.** Across all scenarios, 40.73% of suggestions and 39.33% of top-ranked suggestions were vulnerable.
- **Top 25 weaknesses.** In 54 scenarios across 18 CWEs, 477 of 1,084 valid programs (44.00%) were vulnerable; C (50.29%) fared worse than Python (38.35%).
- **Uneven by weakness.** Cross-site scripting: 19% of options vulnerable. Path traversal: 60%, and every top suggestion was vulnerable.
- **Outdated practices.** For password storage it often produced MD5 or single-round SHA-256 hashing.
- **Context breeds copies.** Existing SQL in the file, safe or vulnerable, most shaped whether generated SQL was injectable; comment-only prompt changes shifted the safety of the top suggestion.
- **Confident and wrong.** Some vulnerable top suggestions carried very high confidence scores (0.92 to 0.96).
- **Advice.** Developers should "remain vigilant" and pair Copilot with security-aware tooling.

## For auditing an LLM-built system
- Run a static analysis scanner (CodeQL or equivalent) over the whole codebase before manual review.
- Hand-check the high-risk spots: SQL and shell construction, file paths from user input, password hashing, and auth checks.
- Where one insecure pattern exists, search for its copies; generated code repeats the context it sees.
