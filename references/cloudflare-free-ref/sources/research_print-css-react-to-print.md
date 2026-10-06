# Printing from the Browser: @page and react-to-print
MDN (2026). https://developer.mozilla.org/en-US/docs/Web/CSS/@page · repo `MatthewHerbst/react-to-print` (MIT, 2.5k stars, pushed 2026-09-14)
Type: docs · Read: 2026-10-06

## What it says
- **`@page`** is "used to modify different aspects of printed pages. It targets and modifies the page's dimensions, orientation, and margins." Example: `@page { size: a4 landscape; margin: 2cm; }`.
- **Page breaks:** `break-before`, `break-after`, and `break-inside` control where pages split.
- **Support:** "Baseline 2024 - Newly available. Since December 2024, this feature works across the latest devices and browser versions." Some parts have varying support.
- **react-to-print:** "Print React components in the browser."

## For an internal system
- Print an invoice as a normal React component with print CSS; staff use the browser's "Save as PDF" for a file. Zero server cost.
- Set `@page { size: A4; margin: … }` and `break-inside: avoid` on line-item rows so no row splits across pages.
