# Cloudflare Free Plan: How Many Libraries in a Fullstack Repo
The number of libraries matters less than where each one runs: browser libraries ship as free static assets, while Worker libraries face the free plan's CPU, startup, memory, and size limits.
Sources: `sources/docs_cloudflare-workers-startup-and-hono.md`, `sources/research_npm-2026-10-library-stats.md`, and the limits in `../cloudflare-free-ref/system.md` and `stack.md` (2026-10-07). Worked numbers are marked (derived).

## Where each library runs
| Side | Free-plan limits that apply | Library rule |
|---|---|---|
| Browser (React app as static assets) | Requests free and unlimited; 20,000 files and 25 MiB per file per version | Use the picks in `design-guide.md`; load heavy ones on the screen that needs them |
| Worker (Hono API under `/api/*`) | 10 ms CPU per request; 1 s startup; 128 MB memory; 64 MiB uncompressed; 50 subrequests | Hono, validation, and bindings only; nothing UI-related |
| Build (Workers Builds) | 3,000 minutes a month; 20 minutes per build | Every dependency adds install and build time |

## Keep the Worker lean
- **Hono is the whole framework:** zero dependencies, Web Standards only, `hono/tiny` under 14 kB.
- **Nothing heavy at startup.** The global scope must parse and run within 1 s; build large schemas or clients inside the handler, not at module top level.
- **No heavy compute in a request:** PDF, Word, and Excel builders, image work, chart rendering, and React server rendering belong in the browser (derived from the 10 ms CPU limit).
- **Waiting is free.** D1, R2, KV, and fetch waits don't count toward CPU time, so data access stays cheap.
- **When the bundle grows:** remove unused dependencies, move config and files to KV, R2, or D1, or split into Workers joined by Service bindings.

## Use browser libraries, but load late
- **The browser side costs nothing on Cloudflare.** A Vite build sits far below 20,000 files and 25 MiB per file (derived); bundle size costs the staff's load time, not quota.
- **Split heavy screens.** Charts, export libraries (react-pdf, ExcelJS, docxtemplater), and rich editors load through dynamic `import()` on the screen that uses them.
- **One library per job:** one component kit, one icon set, one motion library. Two kits mean two looks and twice the updates.

## A fullstack set that fits
- **Browser:** React, Tailwind CSS 4, shadcn/ui (on Radix or Base UI), Tabler icons, TanStack Query and Table, react-hook-form, zod, sonner; recharts and export libraries loaded late; `motion` only when a transition carries state.
- **Worker:** Hono, zod (the same schemas the browser uses), and the D1 and R2 bindings.
- **That's about a dozen direct browser dependencies and two in the Worker (derived).** All are widely used and released in the last six months, except the stable utilities.

## Before adding a library
- **Does the platform, the standard library, or a library already installed do it?** Stop at the first that does; add a dependency only when it replaces code you would otherwise write.
- **Is it fresh?** Released in the last six months and not deprecated or renamed; check the registry name before installing.
- **Which side runs it?** Browser: load it late if it's heavy. Worker: keep it only if it's small and does no heavy work per request.
