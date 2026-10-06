# Astro on Cloudflare Workers
Cloudflare (2026). Developer docs, framework guide. https://developers.cloudflare.com/workers/framework-guides/web-apps/astro/
Type: docs · Read: 2026-10-06

## What it says
- **Static sites:** fully prerendered projects serve from `./dist` as static assets; no Worker code runs.
- **On-demand rendering:** `npx astro add cloudflare` "sets the build output configuration to `output: 'server'`, which server renders all your pages by default". It builds a Worker entry at `./dist/_worker.js/index.js`.
- **Routing:** images, CSS, and JS bundles serve from Workers Assets; dynamic routes run in the Worker. `export const prerender = true` prerenders a page in server mode.
- **Bindings:** server-rendered Astro can use D1, R2, and other bindings; "Static-only sites cannot use bindings."
- **Sessions:** "Wrangler automatically provisions a KV namespace named `SESSION` when you deploy."
- **Requirements:** server rendering needs the `nodejs_compat` flag; Astro 5.x needs Node 18.20.8+, Astro 6.x and 7.x need 22.12.0+.
- **Context:** Cloudflare acquired the Astro company in January 2026 and said Astro stays open source.

## For an internal system
- Prerender every page that doesn't need per-request data; each server-rendered view counts as a Worker request.
- Keep data access in an API (Hono) when pages stay static, since static pages get no bindings.
- Watch session writes: KV allows 1,000 writes a day on free.
