# Theta Development — Website

Resort apartments in Amarynthos, Evia, Greece. Bilingual (EN/ΕΛ) single-page site.

## Files

| File | Purpose |
|---|---|
| `index.html` | The complete website — HTML, CSS, JS, translations, all in one file |
| `images/` | Web-optimized photos (12 files, ~4MB total) |
| `CONTENT.md` | All site text in English & Greek for review/editing |
| `LAUNCH-CHECKLIST.md` | What's left before going live |

## Run locally
Double-click `index.html`. No server or build step needed.

## How to edit

**Text (both languages):** open `index.html`, find `const I18N = {` near the bottom. Every string lives there twice — under `en:` and `el:`. Edit and save.

**Booking / Map links:** find `/* ====== CONFIG ====== */` near the bottom:
```js
const BOOKING_URL = "";   // paste Booking.com property URL
const MAPS_URL    = "";   // paste Google Maps share link (maps.app.goo.gl/...)
const MAPS_EMBED  = "";   // optional: Maps embed URL for the inline map
```
Filling these automatically wires every "Book" button and map link on the page.

**Swap a photo:** replace the file in `images/` keeping the same name (hero.jpg, about.jpg, apt-a/b/c.jpg, gal1–6.jpg, cta.jpg). Recommended max width ~2200px for hero/cta, ~1400px for the rest.

## Deploy
Upload `index.html` + `images/` to any static host (Netlify, Vercel, GitHub Pages, or classic hosting). Point the domain at it. Nothing else required.
