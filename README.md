# Keys Chocolates & Ice Cream — Website Redesign

**Live site:** https://crossfiber.github.io/keys-chocolates/
**Repo:** https://github.com/crossfiber/keys-chocolates
**Built:** April 25, 2026
**Original target:** https://www.keylargochocolates.com/

---

## Brand basics

- **Brand name:** Keys Chocolates & Ice Cream (legacy URL keylargochocolates.com)
- **Owners:** Rich & Bronna Peterson, family-owned since 2010
- **Three locations:** Key Largo (flagship, MM 100), Islamorada, North Palm Beach
- **Tripadvisor:** 4.6 / 5 from 671 reviews · ranked #9 of 118 Key Largo restaurants

## Design direction (one paragraph)

A sixteen-year-old family chocolate-and-ice-cream business with three Florida storefronts — leaning into "Florida Keys family vacation chocolate" rather than the brown-and-gold Parisian luxury cliche. Sun-bleached cream-and-cocoa warmed by the brand's existing hot pink and coral. Signature: a "Three Stops, One Family" interactive map that doubles as a trip planner.

## Fonts

- **Shrikhand** (display headlines) — https://fonts.googleapis.com/css2?family=Shrikhand&display=swap
- **Chivo** (body, nav, buttons) — https://fonts.googleapis.com/css2?family=Chivo:wght@400;500;700;900&display=swap

Both are the live site's existing fonts — preserved for brand continuity.

## Color palette (with sources)

- `--espresso` `#1F1410` — derived dark for footer
- `--cocoa` `#3A2418` — primary cocoa brown
- `--sand` `#F5EAD8` — main background cream
- `--cream` `#FBF6EC` — alt-section background
- `--pink` `#E43880` — EXTRACTED from live site CSS (`--accent-hsl: 334.88, 76.78%, 56.07%`) — primary CTA
- `--coral` `#F0523D` — EXTRACTED from live site (11x in CSS) — trust band
- `--turquoise` `#4FB3A9` — Florida Keys ocean tone, supporting brand
- `--gold` `#D4A85B` — star ratings only

## Placeholders flagged for client to fill

| Placeholder | Section | What to fill |
|---|---|---|
| `[VERIFIED REVIEWER QUOTE NEEDED]` | Reviews | Featured-review quote with attribution |
| `[REVIEWER NAME NEEDED]` (×3) | Reviews carousel | Three real reviews with names |
| `[REVIEW QUOTE NEEDED]` (×3) | Reviews carousel | Three 2-sentence review quotes |
| North Palm Beach hours | Three Stops | Confirmed hours of operation |
| North Palm Beach phone | Three Stops + footer | Direct dial number |
| Wholesale email | Site-wide | Source has typo `wholesale@keylargochocolates@gmail.com` — confirm correct address |
| Events phone | FAQ | Source shows `(561) 561-2882`; build uses corrected `(561) 568-2882` — confirm |

## Hotlinking risks (Squarespace CDN)

Original site is Squarespace 7.1 (site ID `61f1d14f1e9e3625338b5a5e`). All 14 product/team photos were downloaded and committed to `assets/`. Squarespace can change asset URLs on republish, so re-hosting locally was the safe choice.

## Reference builds consulted

- **Hogan/Redline Golf Academy** (`/Builda/hogan-elite-golf/index.html`) — borrowed mobile-drawer + body-scroll-lock, accordion FAQ, sticky-nav scroll detection with `scroll-padding-top`, and horizontal scroll-snap testimonials. See `borrowed-patterns.md`.
- **Casa Cuevas Cigars** (handoff doc) — borrowed tiered card hierarchy and trust-strip-overlap pattern.

## Deploy / handoff

- Single-file build (`index.html`) — all CSS/JS inline. No build step.
- Assets live in `/assets/` and are committed to the repo.
- Dependencies: Google Fonts CDN + Font Awesome 6 CDN. No others.
- GitHub Pages serves from `main` branch root.
- Favicon currently uses `assets/logo-mobile.png`. For better tab rendering, replace with a true 32×32 / 192×192 PNG.
- The contact form `onsubmit` runs an inline `alert()` placeholder. Wire to Formspree, Netlify Forms, or a Zap to make it functional before launch.
