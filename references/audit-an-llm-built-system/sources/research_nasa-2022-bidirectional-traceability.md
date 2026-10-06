# SWE-052: Bidirectional Traceability
NASA (2022). NASA Software Engineering Handbook, guidance for NPR 7150.2. https://swehb.nasa.gov/x/x4AIAw
Type: research · Read: 2026-10-06
Evidence: none cited (standard guidance plus two NASA lessons learned)

## What it says
- NPR 7150.2 requires projects to "perform, record, and maintain bi-directional traceability" from higher-level requirements to software requirements, hazards, design, code, verifications and non-conformances.
- Bidirectional means each link reads both ways: forward finds what was dropped, backward finds what has no reason to exist.

## Findings
- **Only what is required.** The stated rationale: traceability ensures every requirement is designed and tested, and that "only what is required is developed".
- **Missing items.** A requirement with no design, code or test means the product "may not fully meet the goals and objectives" it was built for.
- **Extra items.** Extra requirements mean "unnecessary features and functionality, which add complexity and allow additional areas where problems could occur."
- **Orphans.** Code with no parent design element is extra functionality. "Ideally, the trace does not identify any elements that have no source." The team and assurance staff decide if each orphan is necessary; if it is, they add the missing source requirement.
- **Justify the untraceable.** Requirements that do not trace to a higher-level need must be justified "to show that they are included for a purpose".
- **Matrix rules.** Start at project start, use unique hierarchical IDs, list each requirement once, keep it sortable both ways, assign an owner, review it at each major phase.
- **Lesson 1504.** Contractor matrices that skipped requirement rationale and allocation hampered milestone reviews.

## For auditing an LLM-built system
- Build a two-way trace: every screen, route, field, job, status and setting on one side; the request, ticket or real task it serves on the other.
- Treat every element with no source as an orphan. If no user or owner claims it, list it for deletion.
- Trace backward too: a stated requirement with no element or test is a gap, not a done item.
- Anything kept without a source needs a written purpose, the same bar NASA sets.
