# Superpowers
A complete coding-agent workflow (brainstorm → spec → plan → TDD execution → verify) built from auto-triggering skills that are tested against real agent failures.
Source: github.com/obra/superpowers @ 8ca22db (2026-09-25)

## Writing skills (`writing-skills`)
- **Description is the trigger.** Start with "Use when..." and list situations. Leave the workflow out so agents read the body.
- **Baseline first.** Run the task without the skill, record the agent's exact excuses, then write only their fixes.
- **Match form to failure.** Skipped rules get a prohibition plus a red-flags table. Wrong-shaped output gets a positive recipe.
- **Exceptions get their own rule.** Keep a recipe binding by writing each exception as a separate conditional on something observable.
- **Ties go to shorter.** Between two equally good phrasings, ship the shorter. Keep frequently loaded skills under 200 words.

## Plans (`brainstorming`, `writing-plans`)
- **Pick the path.** Classify the task out loud as Spike, Bounded, or Architectural. When unsure, take the heavier path.
- **Plan the decisions, not the code.** Pin files, signatures, spec values, and tests until only one reasonable implementation remains.
- **Every command has `Expected:`.** Each step is one action: the command to run and the output that means it passed.
- **Interfaces per task.** Each task lists what it Consumes and Produces, with exact names and signatures.
- **Review Focus.** Name the five risky inputs the spec says nothing about, and add a test for each.

## Executing (`executing-plans`, `subagent-driven-development`, `verification-before-completion`)
- **Rulings, not stalls.** Decide ambiguities yourself, log `Ruling: <what> — <why> — <cost if wrong>`, and list every ruling at the end.
- **Four stops only.** Ask the human only before destructive, security-sensitive, or outside-worktree actions, or when every path is a guess.
- **Evidence before claims.** Run the command that proves the claim in this message, and read its output before saying done.
- **Turn count beats token price.** Cheap models take 2–3× the turns. Use mid-tier as the floor, and the cheapest only for plans with complete code.

## Steal this
- **Excuse | Reality table.** List the exact excuses agents use to skip a rule, each with a one-line answer.
- **Write-back note.** Restate goal, constraints, and success criteria, keeping what the user said apart from your assumptions.
- **`<HARD-GATE>` block.** Wrap the approval rule in a tag. A reply approves only the stage actually shown.
- **Self-review pass.** Scan for placeholders, contradictions, ambiguity, and scope, then fix inline and move on.
- **Status codes.** Subagents end with `DONE`, `DONE_WITH_CONCERNS`, `BLOCKED`, or `NEEDS_CONTEXT`.
