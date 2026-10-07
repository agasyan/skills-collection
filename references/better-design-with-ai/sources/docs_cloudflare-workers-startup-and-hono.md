# Workers Startup and Size, and Hono's Footprint
Cloudflare (2026). https://developers.cloudflare.com/workers/platform/limits/ · Hono (2026). https://hono.dev/docs/
Type: docs · Read: 2026-10-07

## What it says
- **Startup:** "A Worker must parse and execute its global scope (top-level code outside of handlers) within 1 second." Over it: "Script startup exceeded CPU time limit" (error 10021).
- **Startup fixes:** "avoid expensive work in global scope. Move initialization logic into your handler or to build time." "Generating or consuming a large schema at the top level is a common cause of exceeding this limit."
- **Size:** 64 MiB on Free and Paid; "Only the uncompressed bundle size counts."
- **Size fixes:** remove unnecessary dependencies; keep config files and static assets in KV, R2, or D1 instead of the bundle; split functionality across Workers with Service bindings.
- **Hono:** "Hono has zero dependencies and uses only the Web Standards"; "The `hono/tiny` preset is under 14kB"; it runs on Cloudflare Workers, Deno, Bun, Node.js, and others.

## For a fullstack repo on the free plan
- Keep the Worker to Hono plus validation and bindings; it parses fast and stays far below every limit.
- Build nothing large at module top level; create it inside the handler.
