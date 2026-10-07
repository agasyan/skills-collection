# DESIGN.md Format Spec
Google Labs (2026). github.com/google-labs-code/design.md, `docs/spec.md` · Apache-2.0 · 28k stars · pushed 2026-10-01 · spec version "alpha"
Type: docs · Read: 2026-10-07

## What it says
- **Purpose:** "a self-contained, plain-text representation of a design system", so "stylistic choices can be followed across design sessions and between different AI agents and tools."
- **Two parts:** optional YAML frontmatter with machine-readable tokens, then a markdown body. "The tokens are the normative values; the prose provides context for how to apply them."
- **Section order (all `##`):** Overview (Brand & Style), Colors, Typography, Layout, Elevation & Depth, Shapes, Components, Do's and Don'ts. Omit sections that don't apply; keep the order of the rest.
- **Overview** sets personality, audience, and feel ("playful or professional, dense or spacious"); it guides the agent when no token covers a case.
- **Do's and Don'ts** are guardrails, e.g. "Do use the primary color only for the single most important action per screen".
- **Used by:** Google Stitch reads it; impeccable's `document` command writes it to this spec.

## For better design with AI
- Put one DESIGN.md at the repo root of every project with a UI.
- Keep tokens real: extract them from the code, never invent a palette the app doesn't use.
