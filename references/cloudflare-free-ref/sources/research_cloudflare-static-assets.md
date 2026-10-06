# Static Assets: Billing and Single-Page Apps
Cloudflare (2026). Developer docs. https://developers.cloudflare.com/workers/static-assets/billing-and-limitations/ · https://developers.cloudflare.com/workers/static-assets/routing/single-page-application/
Type: docs · Read: 2026-10-06

## What it says
- **Assets are free:** "Requests to static assets are free and unlimited. Requests to the Worker script (for example, in the case of SSR content) are billed according to Workers pricing."
- **When the Worker runs:** on any request matching a `run_worker_first` pattern, and on any request that matches no static asset.
- **Free-tier catch:** with `run_worker_first`, requests over the free limit "will receive a 429 (Too Many Requests) response instead of falling back to static asset serving".
- **SPA mode:** with `not_found_handling = "single-page-application"`, "navigation requests will not invoke the Worker script". A navigation request carries `Sec-Fetch-Mode: navigate`; this needs compatibility date 2025-04-01 or later.
- **API routes:** `"run_worker_first": ["/api/*"]` sends API calls to the Worker while other navigation requests still get the SPA shell.

## For an internal system
- Ship the front end as static assets; page loads, JS, and CSS then cost nothing against the daily limit.
- Route only `/api/*` to the Worker, and expect 429s on those routes once the free day runs out.
- Set the compatibility date to 2025-04-01 or later so client-side routes never wake the Worker.
