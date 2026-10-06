# Common Pitfalls in Dashboard Design
Stephen Few (2006). Perceptual Edge white paper, sponsored by ProClarity. https://www.perceptualedge.com/articles/Whitepapers/Common_Pitfalls.pdf
Type: blog · Read: 2026-10-06
Evidence: none cited (argued from vendor dashboard examples)

## What it says
- A dashboard is "a visual display of the most important information needed to achieve one or more objectives, consolidated and arranged on a single screen so the information can be monitored at a glance."
- It serves monitoring: see the big picture, spot what needs attention, drill in to act. It shows what is happening, not why, and must be tailored to one person, group or function ("Dashboard Confusion", 2004: https://www.perceptualedge.com/articles/ie/dashboard_confusion.pdf).

## Findings
- **One screen.** Scrolling, or slicing metrics behind tabs and radio buttons, stops comparison; working memory holds only a few chunks.
- **Context.** "$736,502 quarter-to-date" means little alone; add a target or history and a good/bad state.
- **Right precision and directness.** $3.8M, not $3,848,305.93. Show the variance (-10% vs budget) instead of making viewers subtract.
- **Right medium.** If a pie needs its labels to be read, use a bar chart or a table. Repeat one chart type rather than adding variety.
- **Arrange by use.** Most important data gets the prominent spots; the top-left wasted on logo and nav is a named error. Related data sits together.
- **Highlight one thing.** When everything is bold and colourful, nothing stands out. Keep colour neutral except for what needs attention; Few cites 10% of men and 1% of women as colour blind, so red/green alone fails.
- **No decoration.** Control-panel styling (fake LED meters, switch-like selectors) and 3-D bars cost attention and say little. Few's warning: users "ooooo and ahhhhhh" on day one, then stop looking by week's end if the data isn't clear.

## For internal systems
- Build a dashboard only for a repeated monitoring job; if users need to find, edit or act on records, give them a table.
- Give every number a comparison (target, last period); reserve strong colour for exceptions.
- Fit it on one screen and link each item to the screen where the action happens.
