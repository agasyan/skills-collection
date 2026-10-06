# Cloudflare Browser Rendering (PDF on the server)
Cloudflare (2026). Developer docs. https://developers.cloudflare.com/browser-rendering/pricing/ · https://developers.cloudflare.com/browser-rendering/rest-api/pdf-endpoint/
Type: docs · Read: 2026-10-06

## What it says
- **Free plan:** "10 minutes per day" of browser time, "3 browsers" at once. Paid: 10 hours a month, then $0.09 per hour.
- **`/pdf` endpoint:** "instructs the browser to generate a PDF of a webpage or custom HTML". Request bodies up to 50 MB.
- **Free availability of `/pdf`:** not stated on the page ⚠️.

## For an internal system
- Keep it as a fallback; browser-side PDF costs nothing and has no daily cap.
- 10 browser-minutes a day suits a few documents, not batch invoicing (derived).
