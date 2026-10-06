# Workers Builds: Limits and Build Watch Paths
Cloudflare (2026). Developer docs. https://developers.cloudflare.com/workers/ci-cd/builds/limits-and-pricing/ · https://developers.cloudflare.com/workers/ci-cd/builds/build-watch-paths/
Type: docs · Read: 2026-10-06

## What it says
- **Free:** "3,000 per month" build minutes, "1" concurrent build, "20 minutes" timeout, 2 vCPU, 8 GB memory, 20 GB disk, 64 env vars of 5 KB.
- **Paid:** "6,000 per month (then, +$0.005 per minute)", 6 concurrent builds, 4 vCPU; same timeout, memory, and disk.
- **What counts:** build minutes are "the number of minutes that it takes to build a project". The page gives no split between install, build, and deploy.
- **Out of minutes:** the page does not say what happens when free minutes run out.
- **Watch paths:** "Paths satisfying excludes conditions are ignored first. Any remaining paths are checked against includes conditions. If any matching path is found, a build is triggered. Otherwise the build is skipped." Defaults: include `[*]`, exclude `[]`.
- **Overrides:** a push with 0 file changes, 3,000+ file changes, or 20+ commits always builds.

## For an internal system
- Every push to a one-repo app builds by default; exclude `docs/` and other non-code paths so those pushes cost no minutes.
- Keep a build well under the 20-minute timeout; cache dependencies and avoid building unused packages.
- Count builds per month, not per day: at 2 minutes per build, 3,000 minutes is 1,500 builds (derived).
