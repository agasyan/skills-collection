# Writing Docs
The reader glances, scans, and leaves; the first screen must let them act.
Source: 14 sources in `writing/` (2026-10-06).
A tag like `[Morkes 1997]` names the `writing/` file that backs the rule. An untagged rule is house style with no source found.

## What readers do
- **Glance.** 52% of page visits last under 10 s; readers see about 20–28% of the words. [Weinreich 2008]
- **Scan.** 15 of 19 users scanned before reading; concise text tested +58%, scannable +47%, both plus no hype +124%. [Morkes 1997]
- **Live in reference and examples.** Developers spent about 21% of their time in each and nearly skipped the Concepts page. [Meng 2019]
- **Leave over bad content.** 93% hit incomplete or outdated docs [GitHub 2017]; ambiguity tops the fix list and stale docs drive developers to another API. [Uddin 2015]
- **Pick simple words.** Simplified headlines won 34.8% vs 15.3%, and writers can't spot the winner. [Shulman 2024]

## Page
- **Answer first.** The first screen says what the page is for and what to do; conclusion before detail. [Weinreich 2008] [Morkes 1997]
- **One kind per page.** Tutorial, how-to, reference, or explanation; split a page that serves two. [Diátaxis]
- **Organize by task**, not content type; put concepts inside the task that needs them. [Meng 2019]
- **Scannable.** Headings that name the content, bullets, bold keywords, one idea per paragraph. [Morkes 1997]
- **Lists and tables.** Three or more items make a list (cap 5); comparisons make a table.

## Sentences
- **Half the words.** Cut first; concision was the largest single gain. [Morkes 1997] [Graham]
- **Ordinary words.** A hard topic still gets easy words. [Shulman 2024] [Graham]
- **Short sentences.** Cap steps at 20 words and descriptions at 25, the ASD-STE100 limits (⚠️ from summaries of the spec). [STE] [Google global]
- **Condition first, actor named.** "If X, then do Y"; "You must X", not "X is required". [Google global]
- **One word, one meaning**, same capitalization; never swap synonyms; spell out abbreviations on first use. [STE] [Google global]
- **No hype.** Promotional wording cost 27%. [Morkes 1997] Cut hedges too; flag real doubt `⚠️ Unverified`.
- **Zero em-dashes.** Use a period, colon, or parentheses.

## Write about 80% of the way to ASD-STE100
- **What it is.** A controlled language for aircraft maintenance docs: writing rules plus a dictionary with one word per meaning ("start", never "begin" or "commence"). Issue 9, January 2025; free on request. [STE]
- **Why it works.** Simplified English made complex procedures easier to understand and to search, at no time cost; non-native readers gained most. [Shubert 1995]
- **Prompt with the name.** LLMs know the spec, so "ASD-STE100" works as one leading word. The full spec is strict; ask for "about 80% of the way to ASD-STE100" (a shared practitioner tip, source not linked).
- **Name the register, not the length.** "Be concise" makes a model clip into fragments that are shorter and no clearer. [wait-what]
- **Keep the domain's words.** STE allows project technical names and verbs; simplify the grammar around them, not the nouns. [STE]

## Content
- **Precise first.** State exactly what each parameter and return value means. [Uddin 2015]
- **Examples that run.** Complete and copy-paste-ready, with inputs and setup explained. [Meng 2019] [Uddin 2015]
- **One reader, one concept at a time**, each with a concrete example. [Evans 2021]
- **Plain English.** About a quarter of open-source readers aren't fluent. [GitHub 2017] [Google global]
- **Real numbers only.** A measured, sourced number, or none.

## Keep it true
- **Docs change with the code** in the same commit; delete a doc you know is wrong; link the canonical page instead of copying it. [Google docguide] [Uddin 2015]

## Length, diagrams, and LLM output
- **Budget first.** Name a line or word cap before writing; over budget means unclear, so rewrite instead of compressing.
- **Keep every deliverable.** "For brevity" and "the rest follows the same pattern" are banned.
- **Diagram only spatial answers:** flow, calls, states. One level, 7±2 nodes, every edge labeled.
- **Numeric caps beat "be concise"** when prompting an LLM; past ~100 lines, restate the verdict at the end.

## Check
- **Fresh reader.** Someone new to the topic reads the draft; writers can't judge their own clarity. [Shulman 2024] [Evans 2021]
- **First-line/last-line test.** Those two lines alone say what happened and what to do next. Cut announcing openers and recap closers.
