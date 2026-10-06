# Carbon Design System: data table, empty states and loading
IBM. Carbon Design System. https://carbondesignsystem.com/components/data-table/usage/
Type: system · Read: 2026-10-06

## What it says
- Read: Data table usage, Empty states pattern (/patterns/empty-states-pattern/) and Loading pattern (/patterns/loading-pattern/).
- Data table: toolbar for global actions, sortable headers, row selection, batch actions, expandable rows. Not a spreadsheet replacement.

## Findings
- **Five row heights.** 24, 32, 40 (default), 48, 64 px. Header, toolbar, batch bar and pagination match the row height.
- **Toolbar and row actions.** Up to five toolbar actions, the rest in overflow. Fewer than three row actions: show them as icon buttons, not an overflow menu.
- **Batch mode.** Selecting a row opens a batch action bar at the top; row-level actions are disabled while it is open. Select-all has an indeterminate state.
- **Scanning aids.** Row hover always on, even for non-clickable rows; optional zebra stripes. Only the sorted column shows a sort icon.
- **Loading.** Skeleton states, not spinners, for tables and cards. Full-screen loader when an action blocks the app or saves user input; inline loader for one component; progressive loading when filters change on large data sets.
- **Three empty-state types.** No data (first use), user action (no search results, task done), error (no permission, system issue, configuration needed, unsupported action), each saying why and what to do.
- **Replace, don't overlay.** An empty table replaces headers and footer with the message, so screen readers don't read an empty table first.
- **Wording.** Positive title ("Start by adding data assets"), one primary next step, no dead ends, no jokes in error states. Several empty states at once: text only, tertiary buttons.

## For internal systems
- Default to 40 px rows; offer 32 or 24 px for staff who scan many records.
- Show skeleton rows while a table loads or re-filters.
- Write each empty state for its cause (no data yet, no match for filters, no access, system down), each with one next action.
- Disable per-row actions while batch selection is active.
