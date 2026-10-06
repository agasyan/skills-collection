# Documentation Best Practices
Google. Google Style Guides (docguide). https://google.github.io/styleguide/docguide/best_practices.html
Type: blog · Read: 2026-10-06

## Core idea
A small set of fresh, accurate docs beats a large set in disrepair; keep docs alive by changing them with the code and trimming them "like a bonsai tree."
Evidence: none cited

## Points
- **Minimum viable documentation.** Write short, useful docs and cut anything out of date, incorrect, or redundant.
- **Update docs with code.** Change the docs in the same change (CL) as the code; reviewers can insist on it.
- **Delete dead docs.** Dead docs misinform, slow engineers down, and set a precedent for leaving messes.
- **Clean up gradually.** Delete what is certainly wrong first, have the team mark each doc keep or delete, default to delete, iterate.
- **Good over perfect.** There is no perfect document, only proven methods and prudent guidelines.
- **Write for humans first.** Docs run from meaningful names and why-comments through API contracts and READMEs to design docs.
- **README orients.** A good README says what the directory holds, which files to read first, and who maintains it.
- **Simplest use first.** In class and module docs, list the simplest use case first.
- **Duplication is evil.** Link to the existing guide instead of writing your own; fix the original if it is stale.

## For writing docs
- Ship doc edits in the same commit or PR as the code they describe.
- Delete a doc you know is wrong rather than leave it.
- Link to the canonical guide; never copy it.
- Treat design docs as decision archives once the code ships, not as current docs.
