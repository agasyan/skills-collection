# wait-what: ASD-STE100 as a Register for an Agent
Matt Pocock (2026). mattpocock/skills, `docs/productivity/wait-what.md` and `skills/productivity/wait-what/SKILL.md`, read from a fresh clone at 4588b32. https://github.com/mattpocock/skills
Type: blog · Read: 2026-10-06
Evidence: none cited

## Core idea
A three-line skill: when a message doesn't land, the agent re-pitches it "in ASD-STE100 Simplified Technical English" with the project's glossary words.

## Points
- **Name the register, not the length.** "Be concise" makes the model clip words; "the model over-corrects into clipped fragments that are shorter and no clearer."
- **Short beats long for anti-verbosity skills.** "A four-hundred-line concision skill still leaves the model verbose, because the model copies the length of the skill."
- **STE sets the register; the glossary supplies the nouns.**
- **Working if:** the re-pitch is "shorter and clearer, not shorter and blunter", and adds the missing premise.

## For writing docs
- Prompt an LLM with the name "ASD-STE100" instead of "be concise".
- Pair it with the project's own terms so domain nouns survive the simplification.
