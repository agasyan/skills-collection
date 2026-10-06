# Designing Atlassian's new navigation
Brona O'Connor, Tarra van Amerongen and 6 others (2024). Atlassian blog, How We Build. https://www.atlassian.com/blog/how-we-build/designing-atlassians-new-navigation
Type: blog · Read: 2026-10-06

## What it says
- Design team's account of one navigation for 6 products, after per-team custom navigation made "finding work" a consistent pain point.
- Five test rounds: research with 16 Jira users, interactive prototype, Chrome plugin with 160 users (ease-of-use tests, interviews), low-code prototype, internal testing.

## Findings
- **Identical is not consistent.** A 2018 one-size-fits-all nav failed each product's needs; they aimed for shared patterns that adapt.
- **Principles.** Repeat patterns across products; let users show and hide what's relevant; disclose progressively for new users while keeping power-user features.
- **Sidebar for places, top bar for actions.** Product navigation moved to a sidebar for vertical space and density; the top bar holds search and create in the same spot everywhere.
- **Starred and Recent.** The 16-user study found two needs: customise navigation, and reach frequent items faster.
- **Customisation demand.** Plugin users wanted more: personal project navigation and easier hiding of sidebar items.
- **Familiar beats findable-at-first.** Settings were harder to find at first but made sense once found because they matched other tools; the team chose to onboard users to the location.
- **Three components.** An audit found hundreds of components and 23 major inconsistencies; menu button, flyout menu and expandable menu covered most needs. Item actions sit in one hover menu on the item.
- **Indentation shows hierarchy** but too much truncated labels; one spacing-token change fixed it everywhere.

## For internal systems
- Put screens in a left sidebar grouped by job; keep global search and create in a fixed top bar.
- Add Starred and Recent for the records and screens staff revisit daily.
- Let users hide sections they never use instead of hand-building menus per role.
- Use one navigation pattern across all internal tools so staff learn it once.
