# Hono on Cloudflare Workers
Hono (2026). Docs, getting started. https://hono.dev/docs/getting-started/cloudflare-workers
Type: docs · Read: 2026-10-06

## What it says
- **Scaffold:** `npm create hono@latest my-app`, pick the `cloudflare-workers` template; `npm run dev` serves on port 8787.
- **App:** `const app = new Hono()`, routes like `app.get('/', (c) => c.text('...'))`, `export default app`.
- **Bindings:** declare a type and pass it in: `new Hono<{ Bindings: Bindings }>()`; read D1, R2, or KV from `c.env`. `wrangler types --env-interface CloudflareBindings` generates the types.
- **Static assets:** `"assets": { "directory": "public" }` in the wrangler config serves files beside the API.
- **Config:** local vars in `.dev.vars`; read them from `c.env`, not `process.env`; set production secrets in the Workers dashboard.
- **Deploy:** `npm run deploy`, or GitHub Actions with `cloudflare/wrangler-action` and an API token secret.

## For an internal system
- Run the API as one Hono Worker under `/api/*`; every request it handles counts toward the 100,000 a day.
- Type the bindings so a missing D1 or R2 binding fails at build time.
- Keep secrets out of the repo: `.dev.vars` locally, dashboard secrets in production.
