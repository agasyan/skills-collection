# Enron's Spreadsheets and Related Emails: A Dataset and Analysis
Felienne Hermans, Emerson Murphy-Hill (2015). ICSE 2015, Florence; read as TU Delft report TUD-SERG-2014-021. https://repository.tudelft.nl/file/File_6407791c-a000-4062-acaf-63e04502dfdc
Type: research · Read: 2026-10-06

## What it says
- Mined the Enron email archive (717,102 emails over about 15 months, 2000 to 2001) and the 15,770 analyzable unique spreadsheets attached to them.

## Findings
- **Email is the file server.** 44,214 emails (6.2%) carried a spreadsheet, about 100 a day; with mentions included, 9.6% of all emails concerned spreadsheets.
- **Versions travel by email.** 20.4% of spreadsheet emails used change words (new version, update, revised), which points to no version control. Requests such as "Can you please send us your excel spreadsheets" show sheets lived on local drives.
- **Wrong-file risk is real.** The paper cites Kern County, California, misjudging taxable property by $1.26 billion because a "wrong spreadsheet" was used.
- **Errors are routine.** 24% of spreadsheets with formulas showed an Excel error (#REF!, #DIV/0! and others); each erroneous cell fed 9.6 other formulas on average. 6.0% of spreadsheet emails discussed errors or problems.
- **Simple functions, long chains.** 76% of sheets used only the same 15 functions, led by SUM, arithmetic, IF, NOW, and VLOOKUP; 9,471 unique formulas had chains over 7 steps, and one reached 1,205 cells.
- **Little testing.** Only 9.6% of files contained test formulas.
- **Email is the documentation.** Emails often explained how the attached sheet calculated its numbers.

## For internal systems
- Make one shared record the source of truth and send links in notifications, never attachments, so no one works from an old copy.
- Keep version history and discussion on the record itself, since today both live in email threads.
- Support natively the few calculations teams actually use (sums, lookups, conditions) and log who changed what.
