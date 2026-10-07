# frontend-design (Anthropic)
Anthropic's official one-file design skill (`skills/frontend-design`); core idea: act as a studio design lead whose client "has already rejected proposals that felt cliché or templated", then "plan, review against the brief, build, critique".
Source: github.com/anthropics/skills @ 683bc88 (2026-10-05) · Apache-2.0 (skill LICENSE.txt) · 180k stars (whole repo)

## Before coding
- **Name the subject.** If the brief lacks one, propose a concrete subject, audience, and primary job, then confirm with the client.
- **Mine the subject's world.** Take choices from industry, materials, and vernacular: a toy for girls aged 8–11 differs from a dashboard for financial analysts.
- **Token plan first.** Write 4–6 named hex colors, typefaces with roles, a layout concept with ASCII wireframes, alignment, and principles.
- **Review against defaults.** Revise any plan part that reads like the default for any similar page; state what changed and why.

## Design rules
- **Open with the subject.** The hero shows "the most characteristic thing in the subject's world": headline, image, animation, live demo, or interactive moment.
- **Deliberate type.** Use one or two clearly distinct families, a scale from The Elements of Typographic Style, and type as active design.
- **Line length.** Keep lines under 80 characters; give serif body text slightly more line-height and length than sans.
- **Structure is information.** Borders, numbering, eyebrows, dividers, and labels encode content; use 01 / 02 / 03 only for real sequences.
- **One motion moment.** Use one orchestrated page-load or reveal; motion that answers a person's action is welcome when it shows what changed.
- **Boldness in one place.** Make one element memorable, keep everything around it quiet, and cut decoration that does not serve the brief.
- **Quiet quality floor.** Build responsive to mobile, visible keyboard focus, reduced motion, visually accessible, harmonious palettes, without announcing it.
- **Interface words.** Name things as users understand them; "Publish" yields "Published"; errors name the problem and the fix in the interface's voice.

## Anti-patterns it names
- **Cream, serif, terracotta.** Warm cream near #F4F1EA, high-contrast serif display, terracotta near #D97757, Claude's own accent, so "it reads as a tell".
- **Dark or broadsheet defaults.** Near-black with one acid-green or vermilion accent; or hairline rules, zero border-radius, dense newspaper columns.
- **SaaS-card kit.** Identical rounded cards, one radius on everything, the same rgba(0,0,0,.1) shadow under each, gradient washes as decoration.
- **Template chrome.** Tracked ALL-CAPS eyebrow over every heading, 'A · B · C' meta strings, word-plus-spaced-dash labels, #0B0B0B or #111 as black, mono data labels, '→' on links.
- **Generated-page habits.** One accented word in a headline, all-caps labels, the big-number hero-metric block, fade-and-slide-up on every section, hover on every card.

## Libraries and tools it recommends
- The Elements of Typographic Style: the default guidance for the type scale, weights, widths, and spacing
- Screenshots of your own build, when the environment supports them: self-critique while building, since "a picture is worth 1000 tokens"; it names no code library

## Steal this
- **Calibration list.** Paste the five clusters into the prompt with "Where it leaves an axis free, don't spend that freedom on one of these defaults."
- **Similar-prompt check.** After the token plan, "work through a similar prompt to see if you arrive somewhere similar"; revise each match and say why.
- **Remove one accessory.** End every pass with Chanel's mirror rule, a screenshot review, and a notes file of what you tried, so later passes try something new.
