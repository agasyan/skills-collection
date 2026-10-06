# How Developers Use API Documentation: An Observation Study
Michael Meng, Stephanie Steinhardt, Andreas Schubert (2019). Communication Design Quarterly (ACM SIGDOC). https://sigdoc.acm.org/cdq/how-developers-use-api-documentation-an-observation-study/
Type: research · Read: 2026-10-06

## What they did
- Observed 11 professional developers (under 1 to 25 years' experience, mean 9) solving 5 tasks with an unfamiliar REST API, using only its docs portal.
- Coded screen recordings (eye tracking as support) for time spent in each doc section; sessions capped at 70 minutes. Exploratory study.

## Findings
- **Docs fill half the working time.** Developers had the docs on screen 49% of the time (range 31–68%).
- **Reference and examples dominate.** The API reference and the example pages were each active about 21% of total time.
- **Concept pages split readers.** 5 of 11 spent 0–5.6% of doc time on the Concepts page; the other 6 spent 12.5–42.9%.
- **Two strategies.** Opportunistic developers started coding almost at once from an example and scanned for single facts; systematic ones oriented first and followed the docs closely.
- **Barriers.** Inconsistent navigation, no search, unclear section labels ("Samples" vs "Recipes"), and examples with placeholders that broke copy-paste.
- **Domain knowledge beat seniority.** All fast performers worked in e-commerce, the API's domain; years of experience did not predict speed.

## For writing docs
- Organise docs by task or feature ("Shipments"), not by content type ("Concepts", "Samples").
- Ship complete, copy-paste-ready code examples with no placeholders.
- Put concepts and domain background inside the task that needs them, and repeat critical facts in code comments.
- Provide search and consistent navigation, or one searchable page.
