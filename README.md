# Qlarify Health - Content Studio Landing Page

Production landing page for **Healthcare Content Studio** — the 12-month engine for hospital chains and 300+ bed single-units that runs written content, social media, and video as infrastructure off one editorial brief.

Live URL: **https://content.qlarify.health/** (after Vercel deploy)

## Stack

- Static HTML / CSS (single `index.html`, ~1,000 lines)
- Web3Forms for the audit lead-capture form (no backend required)
- Google Analytics 4 (GA4 ID: `G-61S9HK1N7X`)
- Vercel for hosting and custom subdomain

No build step. The page deploys as-is.

## Files

| File | Purpose |
|---|---|
| `index.html` | The full landing page |
| `qlarify-logo.svg` | Canonical logo, evenodd path for transparent Q |
| `qlarify-logo-revision.mp4` + `qlarify-logo-revision-poster.jpg` | Video infrastructure film embedded in hero / video-infra section |
| `vercel.json` | Security headers + caching config |
| `robots.txt` | Allows all crawlers |
| `sitemap.xml` | Sitemap for the single page |

## Deploy

1. Push to this repo. Vercel auto-deploys on push to `main`.
2. In Vercel, add custom domain `content.qlarify.health` and configure DNS (CNAME → `cname.vercel-dns.com`).
3. After SSL provisions, the page is live.

## Form backend

Web3Forms is wired to deliver submissions to `info@qlarify.health`. Access key is embedded in `index.html` (line ~545). To rotate, update the `access_key` value and redeploy.

## Brand

The page uses the Qlarify Health brand system locked from `video.qlarify.health`:

- Ink (navy) `#163460`
- Rust `#e8835f`
- Cream `#f5f5f0`
- Border / Mist `#c8d8e4`
- Type: Playfair Display (display) + DM Sans (body)

Sister landing page: `180days.qlarify.health` (180-Day OPD Sprint, single-unit hospitals).

## Page sections

1. Header + nav (sticky)
2. Hero with audit form card
3. Why content, not just social (3-up)
4. Video as Infrastructure (dark) — film, 4-stage patient journey, audit CTA, credentials
5. Seven content pillars
6. Pricing — three tiers (Content Studio / Studio+ / Engine)
7. Commitments (do / don't)
8. **Trust layer** — 4 anonymised customer testimonials + 4-stat credentials strip
9. About — three cards (Digitinize / Qlarify Health / Content Studio)
10. Audit CTA strip
11. Footer
