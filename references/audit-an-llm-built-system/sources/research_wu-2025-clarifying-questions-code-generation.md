# HumanEvalComm: Benchmarking the Communication Competence of Code Generation for LLMs and LLM Agent
Jie JW Wu, Fatemeh H. Fard (2025). ACM Transactions on Software Engineering and Methodology. https://arxiv.org/abs/2406.00215
Type: research · Read: 2026-10-06

## What it says
- Two annotators rewrote all 164 HumanEval problems six ways (ambiguous, inconsistent, incomplete, and pairs of these) so correct code needs a clarifying question first.
- Tested ChatGPT (gpt-3.5-turbo-0125), CodeLlama-13B, CodeQwen1.5 Chat, DeepSeek Coder 7B, DeepSeek Chat 7B, and the authors' agent Okanagan. The prompt allowed either code or questions; an LLM evaluator rated question quality.

## Findings
- **Models code instead of asking.** More than 60% of responses were code, not questions, on deliberately flawed specs.
- **Question rates by model.** ChatGPT 14.21%, CodeLlama 10.16%, CodeQwen1.5 Chat 4.82%, DeepSeek Coder 30.76%, DeepSeek Chat 37.93%.
- **Guesses fail.** ChatGPT's Pass@1 fell from 65.58% on the original problems to 31.34% on the modified ones; most models dropped 35–52% (relative).
- **Missing information hurts most.** Incomplete descriptions gave the lowest Pass@1 of any category (12.8% to 46.95%).
- **Asking can be built in.** Okanagan, a multi-round agent designed to ask first, raised the question rate by an absolute 58 points and Pass@1 by 8 points.
- **Limits.** Models are 2024 generation; question quality comes from an LLM evaluator the authors found makes some mistakes.

## For auditing an LLM-built system
- For each business rule in the code, find who stated it; a rule with no source in tickets, chats, or docs is a guess.
- Check the build transcript or prompts for clarifying questions; none on a vague brief means gaps were filled silently.
- Test first the cases the original brief left out; incomplete specs produced the lowest pass rates.
