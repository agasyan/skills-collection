# DESIGN.md for Each Repo
Yes: every repo with a UI gets one `DESIGN.md` at its root, so every AI session builds screens in the same visual system instead of reinventing it.
Sources: `sources/docs_google-labs-design-md-spec.md`, `sources/docs_impeccable-product-and-design-md.md` (2026-10-07).

## Rules
- **Follow the Google Labs DESIGN.md spec.** YAML tokens on top (normative), prose below (how to apply them), eight sections in a fixed order.
- **Extract, don't invent.** Write it from the code and screens that exist; omit any section the project doesn't use.
- **Product facts live elsewhere.** Users, purpose, workflow, and constraints go in a separate product file (impeccable's `PRODUCT.md`, or the workflow's `capture.md`). DESIGN.md holds only the visual system.
- **Refresh, never overwrite silently.** Update it when the design drifts or before a redesign; show the old version first.
- **Internal tools are operate surfaces.** Style changes only type, palette, density, and one signature move; navigation and controls stay standard.

## Template for an internal system
```markdown
---
name: <system name>
description: <one line: who uses it, for what>
colors:
  primary: "#2f5bea"        # the one accent: primary action, focus, selection
  neutral-bg: "#f7f7f8"
  surface: "#ffffff"
  text: "#18181b"
  text-muted: "#71717a"
  border: "#e4e4e7"
  success: "#15803d"
  warning: "#b45309"
  danger: "#b91c1c"
typography:
  body: { fontFamily: "Geist, system-ui, sans-serif", fontSize: "14px", fontWeight: 400, lineHeight: 1.5 }
  label: { fontFamily: "Geist, system-ui, sans-serif", fontSize: "12px", fontWeight: 500, lineHeight: 1.4 }
  heading: { fontFamily: "Geist, system-ui, sans-serif", fontSize: "20px", fontWeight: 600, lineHeight: 1.3 }
  mono: { fontFamily: "Geist Mono, ui-monospace, monospace", fontSize: "13px", fontWeight: 400, lineHeight: 1.5 }
rounded: { sm: "4px", md: "6px" }
spacing: { xs: "4px", sm: "8px", md: "16px", lg: "24px" }
components:
  button-primary: { backgroundColor: "{colors.primary}", textColor: "{colors.surface}", rounded: "{rounded.sm}", padding: "8px 14px" }
  table-row: { height: "40px" }
  input: { backgroundColor: "{colors.surface}", rounded: "{rounded.sm}", height: "36px" }
---
# Design System: <system name>

## Overview
Calm, dense, familiar. Staff use it all day to <job>; it should feel like a better spreadsheet, not a website.

## Colors
One accent for the main action, focus, and selection. State colors only for status. Never color for decoration.

## Typography
One family, four sizes. Numbers in tables use tabular figures; IDs and amounts may use mono.

## Layout
Left sidebar grouped by job, search and create in the top bar. Tables first; edit in a side panel. 40 px rows by default.

## Elevation & Depth
Borders and background tints, not shadows. One shadow level for popovers and side panels.

## Shapes
4 px radius on controls, 6 px on panels. Never mix sharp and rounded in one view.

## Components
Built from <kit, e.g. shadcn/ui + Tailwind>. Tables: first column is what staff recognise, visible filters, checkboxes plus a batch bar. Forms: label above, error below, one message per failure. Every list has loading, empty, and error states.

## Do's and Don'ts
- Do label everything with the staff's own words.
- Do keep the primary color for the single most important action per screen.
- Don't add gradients, glows, decorative stat cards, or emoji.
- Don't invent data: show real labels and plausible values in every mock.
```
The template's colors and fonts are placeholders; replace them with the project's real tokens.
