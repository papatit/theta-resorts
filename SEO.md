# Getting thetaresorts.com to show up on Google

## 0. Blocker — the domain is currently suspended
`thetaresorts.com` resolves to Namecheap's `failed-whois-verification.namecheap.com` nameservers and
refuses connections. The ICANN registrant-email verification was never completed, so Namecheap
suspended the domain. Google cannot crawl or rank a site that does not resolve.

Fix: Namecheap Dashboard → Domain List → Manage → resend the "Verify your email address" mail, click
the link, then confirm the domain resolves again to the Vercel deployment (both `thetaresorts.com`
and `www.thetaresorts.com`, with the apex redirecting to `www` since that is the canonical host).

Everything below only takes effect after the domain is live again.

## 1. Google Search Console (indexing)
1. https://search.google.com/search-console → Add property → Domain → `thetaresorts.com`.
2. Verify with the TXT record Google gives you (Namecheap → Advanced DNS → Add New Record → TXT).
3. Sitemaps → submit `sitemap.xml`.
4. URL Inspection → paste `https://www.thetaresorts.com/` → Request Indexing. Repeat for
   `https://www.thetaresorts.com/?lang=el`.
5. Check the Page Indexing report after a few days; typical first indexing is 3–14 days.

## 2. Google Business Profile (maps + brand searches)
https://business.google.com → create a profile for "Theta Resorts", category *Vacation apartment
rental* / *Serviced accommodation*, address in Amarynthos, website `https://www.thetaresorts.com/`.
Verification is by postcard/video. This is what makes the business appear in the map pack and in the
knowledge panel for "Theta Resorts Amarynthos".

## 3. Links that make the brand findable
Point these at the site so Google has crawl paths and brand corroboration:
- Booking.com listing → website field
- Instagram `@thetaresorts` bio
- Facebook page
- Airbnb / other OTA listings
- Local directories (e.g. evia tourism portals)

## 4. On-site SEO already in the repo
- `robots.txt` + `sitemap.xml` (with hreflang and image entries)
- Canonical `https://www.thetaresorts.com/`, `?lang=el` for the Greek version with `hreflang`
  alternates and a localized `<title>` / meta description
- `LodgingBusiness` + `WebSite` JSON-LD (address, geo, amenities, booking action, `sameAs`)
- Open Graph / Twitter cards, favicon and apple-touch-icon
- `role="img"` + `aria-label` on every background image

Self-serving `aggregateRating` markup was removed: Google disallows ratings a business writes about
itself and can issue a structured-data manual action for it. Real ratings should come from the
Google Business Profile or Booking.com instead.

## 5. Verify after launch
- `https://search.google.com/test/rich-results` on the homepage
- `site:thetaresorts.com` in Google (should return the homepage once indexed)
- PageSpeed Insights — the hero images are large; convert to WebP if LCP is poor
