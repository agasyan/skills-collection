# Workers Limits and Pricing
Cloudflare (2026). Developer docs. https://developers.cloudflare.com/workers/platform/limits/ · https://developers.cloudflare.com/workers/platform/pricing/
Type: docs · Read: 2026-10-06

## What it says
- **Requests:** 100,000 per day on free, "resetting at midnight UTC". Over the limit, Cloudflare returns Error 1027, with fail open (bypass the Worker) or fail closed (error page).
- **CPU time:** 10 ms per HTTP request and per cron run on free; 5 min on paid (default 30 s).
- **CPU excludes waiting:** "Waiting on network requests (such as `fetch()` calls, KV reads, or database queries) does not count toward CPU time." Over the limit → Error 1102, "Worker exceeded resource limits".
- **Size and memory:** "Worker size (uncompressed) | 64 MiB | 64 MiB"; "There is no compressed size limit." Memory 128 MB per isolate; startup 1 s.
- **Per request:** 50 subrequests (paid 10,000), 6 simultaneous connections, 100 MB request body, 16 KB URL, 256 KB logs.
- **Per account:** 100 Workers (paid 500), 5 cron triggers, 64 env vars of 5 KB each.
- **Static assets:** 20,000 files per Worker version (paid 100,000), 25 MiB each.
- **Duration:** no limit for HTTP; 15 min for cron, queues, and alarms.
- **Paid plan:** $5/month minimum, 10M requests and 30M CPU ms included per month.
- **Other free quotas:** KV 100,000 reads, 1,000 writes, 1,000 deletes, 1,000 lists per day, 1 GB; Durable Objects 100,000 requests/day; Queues 10,000 operations/day.

## For an internal system
- Count only requests that run Worker code against the 100,000; static assets are counted separately (see `research_cloudflare-static-assets.md`).
- Keep each request under 10 ms of compute; time spent waiting on D1, KV, or R2 is free.
- Decide fail open or fail closed before launch, so staff know what they see when the day runs out.
