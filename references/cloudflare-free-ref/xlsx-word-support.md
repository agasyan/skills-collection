# Print, PDF, Word, and Excel: Free Options
How a small internal system prints documents (invoices) and offers Word and Excel downloads with free libraries only.
Source: notes in `sources/` (2026-10-06): `research_print-css-react-to-print`, `research_react-pdf`, `research_pdf-lib-jspdf`, `research_docxtemplater-docx`, `research_exceljs-sheetjs`, `research_cloudflare-browser-rendering`.

Everything here runs in the browser, so the Worker's 10 ms CPU limit never applies and Cloudflare's free plan costs nothing extra.

## Recommended free set
| Need | Use | License | Paid parts to avoid |
|---|---|---|---|
| Print an invoice | React component + print CSS (`@page`), react-to-print | MIT | none |
| PDF file to email or store | `@react-pdf/renderer` | MIT | none |
| Word from a Word template | `docxtemplater` core | MIT or GPLv3 | images, HTML, tables, styling, xlsx modules |
| Word built in code | `docx` | MIT | none |
| Styled Excel | ExcelJS | MIT | none |
| Data-only Excel or CSV | SheetJS CE or plain CSV | Apache-2.0 | SheetJS Pro styling |

## How to use them
- **Print first.** `@page { size: A4; margin: 2cm }` plus `break-inside: avoid` on line items; staff print or "Save as PDF" from the browser. `@page` is Baseline 2024.
- **PDF when a file must exist:** build it with react-pdf in the browser and upload it to R2 through the Worker as the issued copy.
- **Word from staff's own template.** Staff design the invoice in Word with `{tags}`; the free core fills tags, loops (line items), and conditions in `.docx`. Images and xlsx templates need paid modules.
- **Word without a template:** `docx` builds tables, headers and footers, images, and page numbers in code; `Packer.toBlob` downloads it.
- **Excel with formatting:** ExcelJS writes fonts, borders, fills, number formats, and formulas to `.xlsx`. Basic-Excel staff only need data plus a totals row.
- **Excel as data only:** CSV opens in Excel; SheetJS CE must come from the SheetJS CDN, since npm stops at 0.18.5.
- **One record, every format.** Generate print, PDF, Word, and Excel from the same invoice data; never retype it.
- **Load these libraries only on the screen that uses them** (dynamic `import()`), so the main app stays light.

## Watch
- **Maintenance:** pdf-lib has had no push since July 2024 and ExcelJS since January 2025; react-pdf, docx, docxtemplater, and jsPDF were active in 2026.
- **Server-side PDF:** Cloudflare Browser Rendering gives 10 browser-minutes a day and 3 browsers on free; whether its `/pdf` endpoint is on free is not stated ⚠️. Keep it as a fallback.
- **Official forms:** to fill an existing PDF form exactly, pdf-lib fills its fields.
