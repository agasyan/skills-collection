# React on Cloudflare Workers
Cloudflare (2026). Developer docs, framework guide. https://developers.cloudflare.com/workers/framework-guides/web-apps/react/
Type: docs · Read: 2026-10-06

## What it says
- **One build:** the Cloudflare Vite plugin compiles the React client and the Worker in one `vite build`.
- **Output:** the React bundle goes to `dist/client` as static assets; the Worker and a generated `wrangler.json` sit beside it. "The `directory` in the output configuration will automatically point to the client build output."
- **Routing:** requests match static files first; unmatched requests invoke the Worker. `"not_found_handling": "single-page-application"` plus `"run_worker_first": ["/api/*"]` sends API calls to the Worker.
- **Size:** the React bundle counts as static assets, not as Worker script size; the Worker (`worker/index.ts`) stays a thin API layer with the bindings.

## For an internal system
- Keep React and the API in one repo and one `vite build`; the React bundle never touches the Worker's 64 MiB size limit.
- Watch the asset limits instead: 20,000 files per version, 25 MiB per file.
- Keep all data access in the Worker under `/api/*`; React calls it with `fetch()`.
