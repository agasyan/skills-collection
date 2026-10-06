# We Have a Package for You! A Comprehensive Analysis of Package Hallucinations by Code Generating LLMs
Joseph Spracklen, Raveen Wijewickrama, A H M Nazmus Sakib, Anindya Maiti, Bimal Viswanath, Murtuza Jadliwala (2025). USENIX Security Symposium 2025. https://arxiv.org/abs/2406.10279
Type: research · Read: 2026-10-06

## What it says
- 16 code LLMs (GPT-3.5, GPT-4, GPT-4 Turbo, and open-source models) generated 576,000 Python and JavaScript samples from Stack Overflow questions and package descriptions.
- Every package the code installed, or the model listed as needed, was checked against PyPI and npm master lists.

## Findings
- **One in five packages is fake.** Of 2.23 million package references, 440,445 (19.7%) did not exist, covering 205,474 unique fake names.
- **Commercial models do better.** Averages were at least 5.2% for commercial models and 21.7% for open-source; GPT-4 Turbo was lowest at 3.59%. JavaScript (21.3%) fared worse than Python (15.8%).
- **Fakes repeat.** Re-running 500 hallucinating prompts 10 times, 43% of fake names came back every time and 58% more than once, so attackers can predict and register them.
- **Not typos.** Only 13.4% of fake names were within 1–2 characters of a real package.
- **Newer topics, more fakes.** Prompts about packages popular in the past year raised rates about 10%; higher temperature raised them too.
- **Detectable.** Three of four models flagged their own fake names with over 75% accuracy; fine-tuning cut DeepSeek's rate by 83%, to 2.66%.

## For auditing an LLM-built system
- Check every dependency in the manifest and lockfile against the official registry, with its publisher, age, and download count.
- Flag packages that are new, rarely downloaded, or unknown to the team; a squatted hallucinated name looks exactly like this.
- Grep code, READMEs, and setup scripts for install commands that add packages outside the manifest.
