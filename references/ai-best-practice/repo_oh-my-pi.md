# oh-my-pi
Terminal coding agent (omp) whose prompts live in static Markdown; core idea: every prompt sentence must change what the agent does.
Source: github.com/can1357/oh-my-pi @ fc6c0c9 (2026-10-06)

## Writing prompts
- **RFC 2119 keywords.** Write MUST, NEVER, SHOULD, AVOID, MAY in full caps; define NEVER and AVOID once as MUST NOT, SHOULD NOT.
- **Literal tags.** Use tags that mean exactly their name, such as `<critical>`, `<completeness>`, `<yielding>`; ornamental tags dilute them.
- **Critical at both edges.** Open with `<critical>` rules and close with a 3–6 line `<critical>` recap; the middle loses attention.
- **Every sentence shifts a decision.** Teach when and why to act; leave internals, recovery logic, and history to code.
- **Pair bans with alternatives.** When the right move is not obvious, follow a NEVER with what to do instead.
- **Persist, never budget.** Tell the agent to continue until complete; "be efficient with tokens" causes premature abandonment.
- **Cut what is already covered.** Drop facts the model knows and rules a hook, schema, or script already enforces.

## Compressing text
- **Re-encode, don't strip.** Recast claims as frames like `Default 30s.` or `X? Y.` instead of deleting words from sentences.
- **Density gate.** If a trial pass saves under 10%, keep the original; dense text is all payload.
- **Protect the payload.** Keep modals, negations, numbers, conditions, exact strings, examples, and scar tissue (lines added after a real mistake).
- **Compress the body, not the trigger.** Keep the skill `description` natural and keyword-rich; it is matched against user phrasing.
- **One claim per bullet.** Keep tactical bullets to 5–12 words and never restate the bold lead in the body.

## Steal this
- **Facts vs. decisions.** "Facts: MUST discover with grep/read. Preferences: ask 2–4 options plus a recommended default; unanswered → default."
- **Unverified marker.** Tag any path or symbol not read this session `unverified — confirm first`.
- **Decision-complete bar.** A fresh implementer executes the plan top to bottom with zero design decisions; this beats brevity.
- **Step shape.** Group steps by behavior, not file: verb, exact target, new behavior, existing helper to reuse.
- **Proof by example.** Name the exact command and one concrete input → expected output; "review your work" proves nothing.
- **Pre-decided fallbacks.** Write "if reality is X, do Y instead" so the implementer never stalls.
- **No decision-free sections.** Leave out Non-Goals, Alternatives, Risks, Future Work, and "as discussed"; state each choice inline.
- **Self-contained handoff.** Give each subagent `# Target`, `# Change`, `# Acceptance` sections; children start with a blank context.
