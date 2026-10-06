# Inline Validation in Web Forms
Luke Wroblewski (2009). A List Apart. https://alistapart.com/article/inline-validation-in-web-forms/
Type: research · Read: 2026-10-06

## What it says
- Lab study run with Etre (London): 22 users aged 21 to 49, six versions of one registration form, shown in random order.
- Control validated only on "create account"; five versions validated inline. Measured success, errors, time, satisfaction and eye tracking.

## Findings
- **Inline beats submit-then-fix.** Best inline version vs control: success +22%, errors -22%, satisfaction +31%, completion time -42%, eye fixations -47%.
- **Validate after, not before.** "After" (on blur) was 7 to 10 s faster than "while typing" and "before and while"; users typed one character at a time, waiting for the error to clear.
- **Premature errors hurt most.** "Before and while" (error shown on focus) had more errors and lower satisfaction than the other inline versions: "flashing red at you" before typing.
- **Help where answers are hard.** Only 30 to 50% of users saw messages on easy fields (name, email, postal code); 80 to 100% saw them on username and password.
- **Ticks on easy fields confuse.** Users stopped to ask whether a green tick meant "valid format" or "my real postal code".
- **Keep messages on screen.** Fading success messages were missed by "hunt and peck" typists watching their keyboard and made users fear a field had turned invalid. Messages inside the field gave no benefit.
- **Hidden-rule fields.** Username availability and password rules used "while typing" with a short delay.

## For internal systems
- Validate a field when the user leaves it; never show an error on focus or mid-typing.
- Give live, delayed feedback only on fields whose rules users can't guess (unique codes, references, formats).
- Check uniqueness inline instead of after submit, so users don't loop through submit, error, retry.
- Skip success ticks on fields the system can't truly verify; keep errors visible until fixed.
