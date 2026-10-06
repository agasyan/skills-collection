# Cloudflare Free Plan: Hono, Astro, and React on Workers
How each part of the stack runs on Workers, and which requests count toward the free limits.
Source: official docs, read 2026-10-06. "Honu" is read as Hono: no framework named Honu turned up.
Research notes: `sources/research_*.md`, one per source.
[Hono on Workers](https://hono.dev/docs/getting-started/cloudflare-workers) · [Astro on Workers](https://developers.cloudflare.com/workers/framework-guides/web-apps/astro/) · [SPA routing](https://developers.cloudflare.com/workers/static-assets/routing/single-page-application/) · [Static assets billing](https://developers.cloudflare.com/workers/static-assets/billing-and-limitations/) · [React on Workers](https://developers.cloudflare.com/workers/framework-guides/web-apps/react/)

## Hono
- **Hono is the Worker.** Every request it handles counts toward 100,000 a day.
- **Bindings arrive on `c.env`** with a typed `Bindings` generic: `new Hono<{ Bindings: Bindings }>()`. `wrangler types` generates the types.
- **`assets.directory`** in the wrangler config serves static files beside the API.
- **Local vars live in `.dev.vars`**; production secrets go in the Workers dashboard.

## Astro
- **Static output runs no Worker code.** Pages come from assets, free. Static-only sites can't use bindings.
- **The Cloudflare adapter defaults to `output: 'server'`:** every page renders in the Worker, so each page view counts as a request and spends CPU.
- **`export const prerender = true`** serves that page as a static asset again.
- **Server rendering needs `nodejs_compat`.** Astro 6 and 7 need Node 22.12.0 or later.
- **Astro sessions provision a KV namespace** (`SESSION`); KV allows 1,000 writes a day on free.

## React single-page app
- **One `vite build` builds both.** The Cloudflare Vite plugin compiles React to `dist/client` as static assets and the Worker beside it. The React bundle never counts as Worker script size.
- **`"not_found_handling": "single-page-application"`** serves `index.html` for navigation requests (`/orders/123`) without invoking the Worker. Needs compatibility date 2025-04-01 or later.
- **`"run_worker_first": ["/api/*"]`** sends only API calls to the Worker.
- **On free, a `run_worker_first` request over the daily limit gets 429** instead of falling back to assets.

```jsonc
{
  "main": "./src/index.ts",
  "compatibility_date": "2026-10-06",
  "assets": {
    "directory": "./dist/",
    "not_found_handling": "single-page-application",
    "run_worker_first": ["/api/*"]
  }
}
```
