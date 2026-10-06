# The Eight Golden Rules of Interface Design
Ben Shneiderman (2016 version, first list 1985). cs.umd.edu, from Designing the User Interface, 6th ed., Section 3.3.4. https://www.cs.umd.edu/users/ben/goldenrules.html
Type: blog · Read: 2026-10-06
Evidence: none cited

## What it says
- Eight principles "derived from experience and refined over three decades" that "require validation and tuning for specific design domains."
- Aim: raise productivity through simple data entry, clear displays and fast feedback that give users competence, mastery and control.

## Findings
- **Strive for consistency.** Same action sequences, terms, colours and layout in similar situations; keep exceptions few and understandable.
- **Seek universal usability.** Add explanations for novices and shortcuts and faster pacing for experts; plan for age, disability and international differences.
- **Offer informative feedback.** Every action gets a response: modest for frequent minor actions, substantial for rare major ones.
- **Design dialogs to yield closure.** Group actions into a beginning, middle and end, and confirm completion so users can drop contingency plans from their minds.
- **Prevent errors.** Grey out invalid options and block letters in numeric fields. After an error, let users repair only the faulty part and leave the state unchanged.
- **Permit easy reversal.** Undo relieves anxiety and encourages exploration; the unit can be one action, one data-entry task or a group of actions.
- **Keep users in control.** Experienced users dislike surprises, changes to familiar behaviour and tedious data entry.
- **Reduce short-term memory load.** Don't make users carry information from one screen to another; fit lengthy forms on a single display.

## For internal systems
- When a form fails validation, keep every entered value and flag only the bad field.
- End each workflow (submit, approve, import) with a confirmation that states what happened.
- Carry IDs and values between screens so staff never copy them by hand.
