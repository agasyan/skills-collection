# Designing Empty States in Complex Applications: 3 Guidelines
Kate Kaplan (2021). Nielsen Norman Group. https://www.nngroup.com/articles/empty-state-interface-design/
Type: research · Read: 2026-10-06
Evidence: NN/g observations and screenshots from enterprise apps; no study data given

## What it says
- Empty states (screens, panels or containers with no content yet, or none to show) are common in complex apps during setup and after filters or searches return nothing.
- Leaving them blank saves build time but confuses users and lowers their confidence.

## Findings
- **Blank looks broken.** After a filter returns nothing, users can't tell if the system is loading, failed, or got the wrong parameters; they re-run the query several times.
- **False "No records" is worst.** An employee-management app showed "No records" while loading, then swapped in data seconds later. Trigger-happy users ("that is, most users") leave before content appears and can't finish their work; the rest learn to distrust the app.
- **One line fixes it.** "There are no records to display for the selected date range."
- **Teach in place.** Empty panels can explain the feature (Datadog: "Star your favorites to list them here"). In-context cues stick better than upfront tutorials.
- **Give a direct path.** Link the action that fills the space: a Create button plus Learn more link; Loggly offers "add log sources" or "use demo data".
- **Running process.** Use a progress indicator while work is in progress; show the empty message only after it completes.

## For internal systems
- Give every list three distinct states: loading (progress indicator), empty (message), error (what failed).
- Show "no results" only after the query finishes, and name the active filters or date range in it.
- Put the create or import action inside the empty state.
