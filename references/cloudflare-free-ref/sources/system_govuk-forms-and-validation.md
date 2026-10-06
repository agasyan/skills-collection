# GOV.UK Design System: question pages, validation and error messages
Government Digital Service. GOV.UK Design System and Service Manual. https://design-system.service.gov.uk/patterns/validation/
Type: system · Read: 2026-10-06

## What it says
- Read: Recover from validation errors, Question pages (/patterns/question-pages/), Error message (/components/error-message/) and Service Manual "Structuring forms" (gov.uk/service-manual/design/form-structure, 2016, updated 2018).
- Start with one thing per page, ask only what you need, validate on submit, write one specific message per error.

## Findings
- **One thing per page, then merge.** One question or decision per page helps focus and error recovery and lets you save answers as users go. Merge pages when research says so; the named case is an internal service whose users "repeat and switch between tasks quickly".
- **Question protocol.** Ask only if you know why you need the answer, what you'll do with it, and how you'll check and secure it.
- **Validate on submit.** Not when the user leaves a field. Live validation only where research shows a need (example: character count). Always validate server side. This contradicts Wroblewski 2009, where on-blur won.
- **Prevent errors first.** Accept unambiguous formats; ignore stray spaces, hyphens and pasted characters.
- **Error display.** Re-show the page with every answer kept, an error summary at top with focus on it, a red message by each field, and "Error:" in the page title.
- **Error wording.** Reuse the label's words ("Enter how many hours you work a week"). No "invalid", "please", "sorry", "oops" or "This field is required". Same text inline and in the summary.
- **Not for system problems.** Eligibility, permission and outage problems get their own page, not a field error.
- **Evidence.** Messages tested in live services (incl. tax credits): users understood the problem, knew the fix and recovered. Carer's Allowance removed a 12-step progress bar with no effect on completion rate or time.

## For internal systems
- Group related fields on one page for repeat, expert work; split into one-thing-per-page for rare or branching flows.
- Never clear inputs on error; link each summary item to its field.
- Write one message per failure type (empty, too long, wrong format) using the field's own label.
- Mark optional fields "(optional)"; never mark required fields with asterisks.
