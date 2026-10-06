# Resolving System-Organizational Misfits: Literature Review and a Framework
Anna Jegorova, Janis Grabis (2025). Complex Systems Informatics and Modeling Quarterly (CSIMQ), no. 45, pp. 123-135. https://doi.org/10.7250/csimq.2025-45.06
Type: research · Read: 2026-10-06

## What it says
- PRISMA review of peer-reviewed ERP studies from 2005 to 2025: 170 papers found, 120 screened, 23 read in full, 11 analysed. Single reviewer, not pre-registered.
- "Gap" is the practitioner fit-gap term for a functional mismatch between system and requirement; "misfit" also covers roles, routines, culture and power.

## Findings
- **Classic taxonomy.** Strong and Volkoff (MIS Quarterly, 2010; three-year case study) found six misfit domains (functionality, data, usability, role, control, organizational culture), each with two types: deficiencies and impositions.
- **Six classification axes.** Actual or perceived; imposed or voluntary; surface or deep; object (data, process, output, role, control, usability); before or after go-live; technical, organizational, cognitive or cultural.
- **Most common misfits.** Data (incompatible structures, missing fields, inconsistent meaning), usability, and role/control (system roles that do not match who is responsible).
- **Three fixes.** Change the organization (process redesign, training), change the system (customize, add-ons), or both; the hybrid is most advocated in practice.
- **Practices the review supports.** Fit-gap before building; participatory diagnosis "to avoid over-reliance on expert assumptions"; minimal customization; tracking workarounds early before harmful patterns set in.
- **Their process.** End users identify misfits, stakeholders agree the list, misfits are classified and ranked, unclear ones go to monitoring, then design, validate, implement, review.
- **Thin evidence.** Most studies are single cases; no study compares which fix works best, and "misfit" has no shared definition.

## For auditing an LLM-built system
- Walk each step of the real process with the people who do it; log every misfit with its object and whether the tool lacks something (deficiency) or forces something (imposition).
- Count workarounds (side spreadsheets, admin overrides, re-keyed data) as misfit evidence from day one.
- Take the misfit list from end users, not from the builder or the LLM's own spec.
- For each misfit choose: change the tool, change the process, or both. Here the real workflow is the baseline, so default to changing the tool.
