# Cloudflare Free Plan: System Limits
The hard limits of Workers, D1, and R2 on the free plan.
Source: official docs, read 2026-10-06. Limits change; recheck a number at its link before relying on it.
Research notes: `sources/research_*.md`, one per source.
[Workers limits](https://developers.cloudflare.com/workers/platform/limits/) · [Workers pricing](https://developers.cloudflare.com/workers/platform/pricing/) · [Static assets billing](https://developers.cloudflare.com/workers/static-assets/billing-and-limitations/) · [D1 limits](https://developers.cloudflare.com/d1/platform/limits/) · [D1 pricing](https://developers.cloudflare.com/d1/platform/pricing/) · [R2 pricing](https://developers.cloudflare.com/r2/pricing/) · [R2 limits](https://developers.cloudflare.com/r2/platform/limits/) · [R2 get started](https://developers.cloudflare.com/r2/get-started/) · [Builds limits](https://developers.cloudflare.com/workers/ci-cd/builds/limits-and-pricing/) · [Build watch paths](https://developers.cloudflare.com/workers/ci-cd/builds/build-watch-paths/)

## Workers
| Limit | Free |
|---|---|
| Requests | 100,000/day, reset 00:00 UTC; over the limit → Error 1027 (fail open or fail closed) |
| Static asset requests | free and unlimited; they don't count toward the 100,000 |
| CPU time | 10 ms per request, cron too; over → Error 1102. Waiting on fetch, KV, D1, or R2 does not count |
| Memory | 128 MB per isolate |
| Subrequests | 50 per request; 6 simultaneous connections |
| Worker size | 64 MiB uncompressed; startup 1 s |
| Workers / cron triggers | 100 per account / 5 |
| Static assets | 20,000 files per version, 25 MiB each |
| Request body / URL | 100 MB / 16 KB |

## Workers Builds (CI)
| Limit | Free |
|---|---|
| Build minutes | 3,000 per month; the whole build of the project counts |
| Concurrency / timeout | 1 build at a time / 20 minutes |
| Machine | 2 vCPU, 8 GB memory, 20 GB disk |
| Watch paths | default builds on every push; excluded paths skip the build |
| Out of minutes | not stated in the docs ⚠️ |

## D1
| Limit | Free |
|---|---|
| Rows read / written | 5,000,000 / 100,000 per day |
| Storage | 5 GB per account; 500 MB per database; 10 databases |
| Queries | 50 per Worker invocation; 30 s max each |
| Query shape | 100 KB SQL, 100 bound parameters, 100 columns per table, 2 MB per row |
| Time Travel | 7 days |
| Over a daily limit | every query errors until 00:00 UTC |

- **Rows read = rows scanned, not returned.** A filter on an unindexed column scans the table.
- **Rows written = each changed row**, plus 1 for each index the write touches.
- **One database runs one query at a time.** 1 ms queries ≈ 1,000/s; 100 ms ≈ 10/s.

## R2
| Limit | Free |
|---|---|
| Storage | 10 GB-month per month |
| Class A ops (writes, lists: PutObject, ListObjects) | 1,000,000 per month |
| Class B ops (reads: GetObject, HeadObject) | 10,000,000 per month |
| Egress | free |
| Objects | 5 GiB per single upload, 5 TiB per object; 1 write per second to the same key |

- **R2 needs an R2 subscription** with free monthly usage included. Third-party guides say enabling it asks for a payment method. ⚠️ secondary sources.
- **Beyond the free tier, R2 is priced** ($0.015/GB-month storage, $4.50 per million Class A). Treat overage as a bill, unlike Workers and D1, which stop (derived).
- **`r2.dev` URLs are rate limited and "not intended for production usage".**

## Other free quotas
KV: 100,000 reads, 1,000 writes/day, 1 GB · Durable Objects: 100,000 requests/day · Queues: 10,000 operations/day.

## Paid, for comparison
$5/month: 10M requests and 30M CPU ms per month, CPU up to 5 min per request. D1: 25B rows read and 50M written per month, 10 GB per database, 1,000 queries per invocation.
