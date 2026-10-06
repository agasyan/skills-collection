# UI Internal System Design
Staff use the tool all day: design for fast, error-free, familiar work, not for a landing page.
Source: UI research and component notes in `sources/` (2026-10-06). A tag like `[Panko 2015]` names the note that backs the rule; an untagged rule is house style.

## Process: user-centered
- **Context first.** Write down who uses it, for which tasks, in what setting, before building. [ISO 2019]
- **Requirements, design, evaluate, repeat.** Evaluate every iteration with real staff plus an inspection pass; keep monitoring after launch. [ISO 2019]
- **Involve future users** in design, and name a peer champion per team. [Venkatesh 2008]

## Users who only know email, Word, and Excel
- **Prerequisite (assumed): their Excel is basic.** Lists plus `+`, `−`, and `SUM`; no `IF`, lookups, or pivots. The system replaces that math with computed totals and needs no formula features. Most spreadsheet users use fewer than 10 functions. [Nardi 1990]
- **Usefulness wins adoption.** It predicted use at every point; ease of use stopped mattering by month 3. Show each team, on their own data, the tedious step the system removes. [Venkatesh 2008]
- **Behave like Excel and Outlook.** Tables select, sort, filter, and copy like a sheet; notifications read like normal email; labels use the words in their sheets. [NN/g 2024]
- **Keep what Excel does well:** a dense editable table, instant feedback on every edit, and export to Excel. [Nardi 1990]
- **The inbox stays where work arrives.** Email each task or approval with a link to the record, show "waiting on you", send reminders, keep comments and decisions on the record. [Whittaker 1996]
- **One record, links not attachments.** 20.4% of spreadsheet emails were about versions or updates. [Hermans 2015]
- **The old sheets have errors.** 94% of 85 real spreadsheets did. Move decision math into tested code, validate at entry, reconcile totals before retiring a sheet. [Panko 2015]
- **Run both side by side** until totals reconcile. No documented migration case was found; this rule is built from [Panko 2015] and [Nardi 1990].
- **Front-load the familiar.** Today's columns and actions first, the rest one labeled level down, never more than 2 levels; a wizard only for one-off linear tasks like the first import. [NN/g 2006]

## Principles: judge every screen
- **Speak their words**, show the state of every record and job, give every flow a Cancel and every destructive action an undo or confirm. [NN/g 1994]
- **Close each workflow** with a confirmation of what happened; carry IDs between screens; on error, flag only the bad field and keep the values. [Shneiderman]

## Patterns
- **Forms.** Group related fields on one page for repeat work; one thing per page for rare or branching flows. Mark optional fields "(optional)". [GOV.UK]
- **Validation.** Check on submit, keep every input, write one message per failure type with the field's own label. [GOV.UK] Also check on leaving a field when its rules can't be guessed (codes, uniqueness): inline checks cut errors 22% and time 42%. [Wroblewski 2009]
- **Tables.** First column is what staff recognise, edit in a side panel, filters and hidden columns always visible, checkboxes plus a batch bar, at most 2 inline actions per row. [NN/g 2022] Rows 40 px by default, 32 or 24 px for heavy scanning. [Carbon]
- **States.** Loading, empty, and error look different. Show "no results" only after the query finishes, name the active filters, put the create or import action inside the empty state. [NN/g 2021] [Carbon]
- **Navigation.** Screens in a left sidebar grouped by job; search and create in a fixed top bar; Starred and Recent; one pattern across tools. [Atlassian]
- **Dashboards** only for repeated monitoring: every number with a comparison, strong color only for exceptions, one screen, each item linked to where the action happens. To find, edit, or act, use a table. [Few]

## Visual
- **Use an existing design system** (Carbon, GOV.UK, shadcn) instead of custom styling.
- **Calm and dense.** Little layout variety, minimal motion, high density; one accent, one radius; no gradients, glows, or decorative stat cards. From `../ai-best-practice/repo_taste-skill.md`.

## Components: reuse, don't reinvent
All MIT; notes in `sources/research_{shadcn-ui,ag-grid-community,refine,mantine,ant-design}.md`.
- **Default kit: Tailwind + shadcn/ui.** Copy-in components you own, nothing locked in a dependency, "AI-Ready" code an assistant can read and edit. [shadcn]
- **Tables: TanStack Table, following shadcn's data-table guide:** sorting, filtering, pagination, column visibility, and row selection for the batch bar. Add a totals row for the sums staff do today. [shadcn]
- **CRUD-heavy apps: add Refine (headless)** for auth, access control, forms, tables, and audit logs; point its REST data provider at `/api/*`. [Refine]
- **Skip Excel-grade grids for basic-Excel staff.** AG Grid Community gives editing, sorting, filtering, and CSV export for free; Excel export, range copy-paste, grouping, and pivots are paid. Add it only for a screen where staff edit many cells at once. [AG Grid]
- **Alternatives:** Mantine (120+ components with forms, dates, and notifications, no Tailwind) when you want everything ready-made; Ant Design for dense enterprise screens with its own look. Use one kit per app. [Mantine] [Ant Design]
- **Bootstrap** (not researched): a CSS framework, so tables, form state, and CRUD would still be built by hand.
- **All fit Cloudflare's free plan.** They ship as static assets, which are free and unlimited; a Vite build sits far below 20,000 files and 25 MiB per file (derived).

## Documents
- **Print, PDF, Word, and Excel downloads:** see `xlsx-word-support.md`, free libraries only, all in the browser.

## Hosting on Cloudflare's free plan
Numbers and sources: `system.md` and `stack.md` in this folder.
- **Static front end, one API Worker.** Build React (SPA mode) or Astro static into assets; serve the Hono API under `/api/*`. Asset requests are free and unlimited; only API calls count toward 100,000 a day.
- **Render on the client, not per request.** Server rendering every page makes each view a Worker request and spends the 10 ms CPU budget.
- **Design lists for 5M D1 rows read a day:** index every filter and sort column, paginate, never list an unindexed table in full.
- **Import old sheets in chunks:** 100,000 rows written a day, plus 1 per index.
- **Files live in R2**, served through the Worker with auth. Build Excel exports in the browser to stay under 10 ms CPU.
- **A limit hit stops the system until 00:00 UTC.** Show a clear message, and keep the manual way available during each migration phase.

## Evaluate on a budget
- **Heuristic pass** by you plus 1–2 colleagues: no single evaluator found more than 42 of 206 problems. [Jeffries 1991]
- **Test 5 staff from one role, fix, test 5 more**; 3–4 per role when roles differ. Small rounds still miss many problems. [NN/g 2000]
- **Per task, record** completion, time, and errors, then ask one satisfaction question; use SUS at the end. [Sauro 2009]
- **Walk through only the 3–5 core tasks**; a full walkthrough is too slow. [Jeffries 1991]
