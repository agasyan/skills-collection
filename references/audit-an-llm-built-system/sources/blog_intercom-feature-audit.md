# Before You Plan Your Product Roadmap
Des Traynor (2014). Intercom blog. https://www.intercom.com/blog/before-you-plan-your-product-roadmap/
Type: blog · Read: 2026-10-06
Evidence: none cited (argued from a hypothetical product)

## What it says
- Before planning work, ask "How many people are actually using each of our product's features?"; a few minutes of SQL answers it.
- Plot every feature on two axes: how many people use it and how often. "The core of your product is buried in the top right."

## Findings
- **Exclude plumbing.** Leave out account creation, password reset and similar; they are "simply a cost of having a product in the first place".
- **Simpler view.** A bar chart of the percentage of users who adopted each feature.
- **How sprawl happens.** In his example, messaging, files and document editing succeed; then a chat room flops, a calendar fails ("no one created more than one event") and time tracking suits one user type.
- **Four choices per weak feature.** "Kill it", increase adoption, increase frequency, or "deliberately improve it" for the people who use it.
- **Diagnose first.** Ask five whys, with more than one user, to find what blocks use; then "fish or cut bait".
- **Focus risk.** A product excellent for "one precise workflow" plus unused extras is open to a simpler competitor.

## For auditing an LLM-built system
- Pull use per feature (screen views, actions, API calls) over a full business cycle, leaving out login and admin plumbing.
- Plot users against frequency. Features in the bottom left that no requirement or owner claims are deletion candidates; default to "kill it".
- Ask non-users why before cutting. "We do that in the spreadsheet" is a fit problem in the feature, not proof the feature is needed.
