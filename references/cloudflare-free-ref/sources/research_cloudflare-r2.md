# R2 Pricing, Limits, and Getting Started
Cloudflare (2026). Developer docs. https://developers.cloudflare.com/r2/pricing/ · https://developers.cloudflare.com/r2/platform/limits/ · https://developers.cloudflare.com/r2/get-started/
Type: docs · Read: 2026-10-06

## What it says
- **Free tier, per month:** "10 GB-month" storage, "1 million" Class A requests, "10 million" Class B requests; egress "Free".
- **Class A** (writes and lists): PutObject, CopyObject, ListObjects, multipart uploads, bucket changes. **Class B** (reads): GetObject, HeadObject, HeadBucket.
- **Paid rates:** $0.015/GB-month standard storage, $4.50 per million Class A. The page does not say what happens at the free limit.
- **Setup:** "You need a Cloudflare account with an R2 subscription." "R2 is free to get started with included free monthly usage." Third-party guides (not Cloudflare docs) say enabling R2 asks for a payment method.
- **Limits:** 5 TiB per object; 5 GiB per single-part upload, 4.995 TiB multipart; 10,000 parts; 1,024-byte keys; 8,192 bytes of metadata; "1 per second" concurrent writes to the same key; 1,000,000 buckets.
- **`r2.dev`:** has "a variable rate limit" and is "not intended for production usage".

## For an internal system
- Store attachments and exports in R2, not in D1 rows.
- Serve files through the Worker with an auth check, not through public `r2.dev` URLs.
- Budget reads and writes per month, not per day; expect a bill, not an outage, past the free tier.
