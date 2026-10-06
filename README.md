# skills-collection

Short Claude Code skills for personal projects: one context, no subagents, about 20 lines each.

## The chain

| Step | Command | Needs first | Writes | What it does |
|------|---------|-------------|--------|--------------|
| 0a | `/capture <workflow>` | nothing: standalone | `docs/flows/{slug}/capture.md` | Captures how a workflow runs today, exactly, even fully manual: manual steps first, then rules, exceptions, pain points, and "As me, I want to…" personas. Drafts from your brain dump, then asks only about gaps. |
| 0b | `/migrate` | `capture.md` from `/capture` | `docs/flows/{slug}/migration.md` | Plans the migration from manual to a system that follows the current approach: step map, data move, phases with side-by-side running and fallback, rules kept. |
| 1 | `/sharpen <ask>` | nothing: standalone (uses flow docs if present) | `.plans/{date}-{slug}/1-sharpen.md` | Separates what you want, what you need, and what is wrong today, from your docs and code, no web. Looks up facts itself; asks you only for decisions. |
| 1 | `/research <ask>` | nothing: standalone (uses flow docs if present) | `.plans/{date}-{slug}/1-sharpen.md` | Same, plus web research: how others solve it, best practice, and pitfalls, with links. |
| 2 | `/outline` | `1-sharpen.md` from `/sharpen` or `/research` | `2-outline.md` | Checks the code and picks a direction: today's flow, decision, behavior changes, slices. |
| 3 | `/steps [slice]` | `2-outline.md` from `/outline` | `3-steps.md` | Opens every file and writes red tests, line anchors, and steps per slice. |

**Standalone:** `/capture`, `/sharpen`, and `/research` start from your words alone, so each works on its own: document any process, or sharpen any ask with or without web research. **Not standalone:** `/migrate`, `/outline`, and `/steps` continue the file the previous step wrote; run that step first, or write the file by hand.

Run `/capture` and `/migrate` once per workflow; then build each phase through sharpen → outline → steps. Pick `/sharpen` for obvious changes (no web searches, cheaper) or `/research` when best practice matters. Each step reads the previous file, so edit a file to correct the next step. All of them run only when you type them.

## Install

```bash
for s in capture migrate sharpen research outline steps; do ln -s ~/personal/skills-collection/skills/$s ~/.claude/skills/$s; done
```

Add `.plans/` to a project's `.gitignore` to keep plans out of commits.

## References

Compact notes to read before writing a skill or a doc. No skill loads them.

- `references/ai-best-practice.md`: how to write skills, prompts, and agent instructions, grounded in the repo notes below.
- `references/ai-best-practice/`: one `repo_*.md` note per repo (ponytail, superpowers, mattpocock, oh-my-pi, pi, i-have-adhd, taste-skill), each pinned to the commit it was read at.
- `references/cloudflare-free-ref/`: everything for building an internal system on Cloudflare's free plan. Guides at the top; every research note and source result in `sources/` (`research_*`, `system_*`, `blog_*`):
  - `ui-internal-system-design.md`: UI design with user-centered design, including users who only know email, Word, and Excel.
  - `system.md`, `stack.md`: Workers, D1, R2, and build free limits; Hono, Astro, and React on Workers.
  - `xlsx-word-support.md`: printing invoices and PDF, Word, and Excel downloads with free libraries.
- `references/audit-an-llm-built-system/`: how to audit a system an LLM built (overbuilt flows, invented assumptions, drift from the real workflow). `audit-guide.md` at the top; 14 source notes in `sources/` (`research_*`, `docs_*`, `blog_*`).
- `references/writing-docs.md`: how to write readable docs, grounded in the sources below.
- `references/writing/`: one file per source on docs readability, found on the web: `research_*.md` for papers and studies, `blog_*.md` for practitioner posts.
