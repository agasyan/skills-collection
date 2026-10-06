# D1 Limits and Pricing
Cloudflare (2026). Developer docs. https://developers.cloudflare.com/d1/platform/limits/ · https://developers.cloudflare.com/d1/platform/pricing/
Type: docs · Read: 2026-10-06

## What it says
- **Free daily quota:** 5 million rows read, 100,000 rows written; 5 GB storage in total. Resets at 00:00 UTC.
- **Over the limit:** "you will not be able to run queries against D1. D1 API will return errors to your client indicating that your daily limits have been exceeded."
- **Rows read** count rows scanned: "A query that filters on an unindexed column may return fewer rows to your Worker, but is still required to read (scan) more rows."
- **Rows written** count each row an INSERT, UPDATE, or DELETE touches; a write to an indexed column adds one more row per index.
- **Indexes:** "The reduction in rows read is typically offset by the additional row written to update the index."
- **Size:** 10 databases, 500 MB each, on free (paid 50,000 and 10 GB). Time Travel 7 days (paid 30).
- **Queries:** 50 per Worker invocation on free (paid 1,000); 30 s max; 100 KB statement; 100 bound parameters; 100 columns; 2 MB per row; 6 connections per Worker.
- **Concurrency:** "Each individual D1 database is inherently single-threaded, and processes queries one at a time." 1 ms queries ≈ 1,000/s; 100 ms ≈ 10/s. Full queues return errors.
- **Bulk changes** of hundreds of thousands of rows must run in smaller chunks.

## For an internal system
- Index every column a list filters or sorts on; the free day is counted in rows scanned.
- Plan imports against 100,000 writes a day, counting one extra write per index.
- Treat a hit limit as downtime until 00:00 UTC, not as a slowdown.
