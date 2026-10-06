# AG Grid Community vs Enterprise
AG Grid (2026). Docs. https://www.ag-grid.com/react-data-grid/community-vs-enterprise/ · https://www.ag-grid.com/react-data-grid/csv-export/ · https://www.ag-grid.com/react-data-grid/cell-editing/
Type: docs · Read: 2026-10-06

## What it says
- **Community is free:** "AG Grid Community is available under the MIT licence", with row and column configuration, sorting, filtering, and pagination.
- **CSV export is free:** "Community version supports api CSV Export but not Context Menu."
- **Cell editing:** the editing page (editable cells, validation, undo/redo, batch editing) shows no Enterprise badge.
- **Enterprise only (paid):** Excel export, Excel-like clipboard copy and paste, range selection, row grouping, pivot tables and aggregations.

## For an internal system
- Use it only on screens where staff edit many cells like a sheet; shadcn/TanStack tables cover the rest.
- Free gets you editing, sorting, filtering, and CSV export; real Excel files and range copy-paste need a paid license.
