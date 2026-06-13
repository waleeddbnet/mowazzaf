# موظّفك الذكي — Mowazzaf AI

Landing page + waitlist for an Arabic-first, no-code AI agent builder aimed at
Sudanese SMEs. Businesses get a shareable **link + QR** to a branded web chat
agent (no app, no Meta verification). This repo is the demand-validation page.

## Files
- `index.html` — the full landing page (single self-contained file: HTML + CSS + JS).

## Local preview
Just open `index.html` in a browser, or:
```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Two values to fill before going live
Both are clearly marked in `index.html`:

1. **`STEP 1` — Formspree endpoint** (so signups reach you)
   - Create a free form at https://formspree.io → copy the URL (`formspree.io/f/xxxxxx`)
   - Replace `YOUR_FORM_ID` in the `<form action=...>` tag.
   - Until then the form runs in demo mode (shows success, stores nothing).

2. **`STEP 2` — QR target** (so the QR is scannable to your live page)
   - Set `const QR_TARGET` to your live URL.
   - If your Cloudflare Pages project is named `mowazzaf`, the URL is
     `https://mowazzaf.pages.dev` — which is already the default, so no edit needed.

## Deploy (Cloudflare Pages, Git-connected)
1. Push this repo to GitHub (see below).
2. Cloudflare dashboard → Workers & Pages → Create → Pages → **Connect to Git**.
3. Pick this repo. Build settings: **no build command**, output dir = `/` (root).
4. Deploy → you get `mowazzaf.pages.dev`. Every push auto-deploys after that.

## Validation goal
Track signup rate and the "willingness to pay" answers. Run a manual concierge
test for the first signups before building the real product.