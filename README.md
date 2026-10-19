# Thunder Car Logistics — website

Static site built to mirror shipguy.com, focused on California, with the Ship Guy pricing tool embedded.

## Files
- `index.html` — homepage with the pricing tool in the hero (embed is verbatim from the plug-and-play package; only PQ_CONFIG was edited)
- `privacy.html`, `terms.html` — legal pages
- `assets/logo.png` — logo
- `functions/api/quote/[[path]].js` — Cloudflare Pages Function that proxies leads to BeRocker with this site's Lead Source key `6ad674b186b38`

## Deploy (Cloudflare Pages)
1. Create a Pages project and upload this folder (or connect a repo containing it).
2. Optional but recommended: Settings → Environment variables → `BEROCKER_LEAD_KEY = 6ad674b186b38` (the file already defaults to that key).
3. Add the site's domain to the Google Maps API key referrer restrictions (ZIP suggestions), or paste a new key in `PQ_CONFIG`.

## Before go-live — edit in `index.html`
- `PQ_CONFIG` (near the bottom): `phoneDisplay` / `phoneTel` — (619) 473-7795. Every phone link on the page reads from PQ_CONFIG, so changing it there changes the whole site.
- Footer email `info@thundercarlogistics.com` (placeholder domain).
- `siteUrl` / `siteLabel` in PQ_CONFIG if the real domain is different.
- USDOT / MC numbers are intentionally not printed (unknown). Add them to the hero `.hero-cred` line and the footer when available.
- No customer-review section is included yet — add real reviews when you have them.

## Test after deploy
Follow section 3 of the pricing-tool README: ZIP validation, Year→Make→Model loading, consent check, submit → price → booking redirect, and confirm the lead lands in BeRocker under **Thunder Car Logistics** (lead source id 42).
