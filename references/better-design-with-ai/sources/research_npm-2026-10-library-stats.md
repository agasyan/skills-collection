# UI Library Usage and Freshness (npm)
npm registry and npm downloads API, queried 2026-10-07. https://api.npmjs.org/downloads/point/last-week/{pkg} · https://registry.npmjs.org/{pkg}
Type: research (measured) · Read: 2026-10-07

## Method
- **Used:** downloads in the last week. Counts include installs pulled in by other packages, so they measure reach, not direct choice.
- **Updated:** the latest version and its publish date. "Fresh" here means a release since 2026-04.

## Results
| Area | Package | Weekly downloads | Latest | Released | License |
|---|---|---|---|---|---|
| Styling | tailwindcss | 163,032,225 | 4.3.3 | 2026-07-16 | MIT |
| Components | shadcn (CLI) | 13,356,686 | 4.21.3 | 2026-10-06 | MIT |
| Primitives | radix-ui | 19,064,097 | 1.7.0 | 2026-10-05 | MIT |
| Primitives | @base-ui/react | 19,271,066 | 1.8.0 | 2026-09-04 | MIT |
| Primitives | react-aria-components | 5,869,802 | 1.21.1 | 2026-09-04 | Apache-2.0 |
| Full kit | @mui/material | 12,503,562 | 9.4.0 | 2026-08-27 | MIT |
| Full kit | antd | 4,517,087 | 6.6.5 | 2026-09-20 | MIT |
| Full kit | @mantine/core | 3,305,015 | 9.7.1 | 2026-10-06 | MIT |
| Full kit | @chakra-ui/react | 2,006,693 | 3.37.0 | 2026-08-28 | MIT |
| Icons | lucide-react | 134,583,738 | 1.52.0 | 2026-10-04 | ISC |
| Icons | @tabler/icons-react | 4,168,768 | 3.49.0 | 2026-10-05 | MIT |
| Icons | @phosphor-icons/react | 6,195,297 | 2.1.10 | 2025-05-22 ⚠️ | MIT |
| Icons | @heroicons/react | 5,022,557 | 2.2.0 | 2024-11-18 ⚠️ | MIT |
| Motion | motion (renamed from framer-motion) | 28,260,335 | 14.0.0 | 2026-10-02 | MIT |
| Motion | gsap | 7,084,295 | 3.15.0 | 2026-04-13 | "no charge" standard license, not OSI |
| Feedback | sonner | 63,500,483 | 2.0.8 | 2026-08-09 | MIT |
| Feedback | cmdk | 54,820,725 | 1.1.1 | 2025-03-14 ⚠️ | MIT |
| Feedback | vaul | 46,589,021 | 1.1.2 | 2024-12-14 ⚠️ | MIT |
| Data | @tanstack/react-query | 82,757,109 | 5.104.1 | 2026-10-02 | MIT |
| Data | @tanstack/react-table | 26,587,277 | 9.2.6 | 2026-10-04 | MIT |
| Forms | react-hook-form | 70,255,177 | 7.89.0 | 2026-09-26 | MIT |
| Forms | zod | 387,371,526 | 4.6.5 | 2026-09-13 | MIT |
| Charts | recharts | 71,292,254 | 3.10.1 | 2026-07-25 | MIT |
| Charts | echarts | 6,777,064 | 6.1.0 | 2026-05-19 | Apache-2.0 |
| Charts | chart.js | 15,712,249 | 4.5.1 | 2025-10-13 ⚠️ | MIT |
| Fonts | @fontsource-variable/inter | 6,284,869 | 5.3.0 | 2026-07-19 | OFL-1.1 |
| Fonts | geist | 3,079,426 | 1.7.2 | 2026-06-01 | OFL |
| Utils | tailwind-merge | 107,067,280 | 3.7.0 | 2026-09-12 | MIT |
| Utils | clsx | 155,831,150 | 2.1.1 | 2024-04-23 | MIT |
| Utils | class-variance-authority | 83,559,474 | 0.7.1 | 2024-11-26 | Apache-2.0 |

⚠️ = no release since 2026-04. Small, stable utilities (clsx, class-variance-authority) need few releases; for UI components and icons, a stale release means slower fixes.

## Renamed or deprecated
- `@base-ui-components/react` is deprecated: "Package was renamed to @base-ui/react".
- `framer-motion` and `motion` both ship 14.0.0; `motion` is the current name.

## For choosing libraries
- Prefer packages that are both widely used and released in the last 6 months.
- Check the package name in the registry before installing; renamed packages linger with high download counts.
