# Patterns in confusing explanations
Julia Evans (2021). jvns.ca. https://jvns.ca/blog/confusing-explanations/
Type: blog · Read: 2026-10-06

## Core idea
Technical explanations confuse readers in 13 recurring ways; naming them helps writers catch the patterns in their own drafts, because positive rules like "avoid jargon" feel too obvious to check.
Evidence: none cited

## Points
- **Outdated assumptions.** Writers who learned a topic years ago assume readers share their old background; test drafts on people who don't know the concept.
- **Inconsistent reader level.** Explaining a for loop, then assuming malloc knowledge, loses everyone; pick one specific person and write for them.
- **Unrealistic examples.** Bicycle-style interface examples say nothing about real use; use examples from real code.
- **Meaningless jargon.** A term like "cryptographically secure" sounds specific but carries no information; drop jargon you don't need.
- **Missing key idea.** Readers can't spot a missing central idea, so an expert reviewer has to check for it.
- **Too many concepts at once.** A paragraph that introduces five new concepts is too much; give each concept space to breathe.
- **Starting abstract.** Start with something concrete the reader has done, then explain how it works.
- **Unsupported claims, no examples.** Show the claim with a program the reader can run instead of asserting it.
- **Wrong way without warning.** Say up front that an approach is a mistake before you show it.
- **"What" without "why".** A feature list doesn't tell readers whether the tool fits them; a weak, personal "why" beats none.

## For writing docs
- Name one target reader before drafting and hold every paragraph to their level.
- Introduce one new concept at a time, each with a concrete, realistic example.
- Have someone who doesn't know the topic read the draft.
