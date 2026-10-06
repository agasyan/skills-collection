# Data Tables: Four Major User Tasks
Page Laubheimer (2022). Nielsen Norman Group. https://www.nngroup.com/articles/data-tables/
Type: research · Read: 2026-10-06
Evidence: NN/g usability testing and eyetracking observations; no sample size given

## What it says
- Large workplace tables must support four tasks: find records that fit criteria, compare data, view/edit/add one row, act on records.
- Tables beat cards for multivariate data: they scale in rows and columns, and adjacent values can be compared without holding them in working memory.

## Findings
- **Find.** Users mix filters, sort, search, Ctrl-F and scanning in ways that are hard to predict. First column: a human-readable identifier, not a "mystery meat" ID. Order columns by importance, related ones adjacent.
- **Show filter state.** Filters must be discoverable, quick and powerful, with a clear visual sign that the data is filtered.
- **Compare.** Freeze the header row and first column on big tables; borders, zebra stripes and row hover help users keep their place.
- **Hide and reorder cheaply.** Column hide/reorder must be easy, not drag-only, and show state ("15 columns hidden"). Users should be able to hide rows too.
- **Edit one row.** Inline edit only for narrow tables, with a visibly different edit mode. Avoid modals: users look at other rows for reference values while editing. Prefer a nonmodal side panel; accordions pile up clutter.
- **Act.** One or two inline row actions fit; more get crowded, unlabeled or hidden behind hover. Use checkboxes plus batch actions above or below the table, with Select All when whole-set actions are common.

## For internal systems
- Make the first column the thing staff recognise (booking reference, partner name), not a database ID.
- Edit records in a side panel that keeps the table visible.
- Keep active filters and hidden columns visible at all times.
- Put multi-row actions in a batch bar driven by checkboxes; keep at most two inline actions per row.
