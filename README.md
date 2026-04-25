# Keys Chocolates & Ice Cream — Website Redesign

**Live site:** https://crossfiber.github.io/keys-chocolates/
**Repo:** https://github.com/crossfiber/keys-chocolates
**Built:** April 25, 2026 · **v2** (pink + white + green palette)
**Original target:** https://www.keylargochocolates.com/

---

## v2 — what changed

- **Palette:** pink + white + green (the actual storefront colors). Removed the cocoa/espresso brown family entirely. Pink remains the CTA color (#E43880); brand green is now #5BB85B with a deep variant #2D8C3A and a forest #1A4D2E for dark surfaces.
- **Hero image:** swapped the interactive Florida Keys SVG map for the homepage hero image from the live site (Main Page Mockups composite). Added a "Hand-crafted on Mile Marker 100" pink badge overlay.
- **About / Peterson Story photo:** swapped the team photo for the first photo on `/our-story` (the inside-the-shop "since 2010" image).
- **Three Stops section:** removed the SVG map graphic. Each location is now a real photo card (with a numbered pin badge and location stamp) plus address, hours, and signature item.
- **Mobile — Beyond the Counter:** Weddings / Catering / Wholesale collapse into tap-to-open accordions on mobile (≤768px). Featured "Weddings & Events" gets the same treatment.
- **Mobile — Signature Sweets:** at ≤540px, each card shows just the title + price + a `+` toggle. Tap to expand description.
- **Reviews carousel:** prev/next arrow buttons added. Disabled-state styling at ends. Hidden behind the carousel on small mobile.

## Brand basics

- **Brand name:** Keys Chocolates & Ice Cream (legacy URL keylargochocolates.com)
- **Owners:** Rich & Bronna Peterson, family-owned since 2010
- **Three locations:** Key Largo (flagship, MM 100), Islamorada, North Palm Beach
- **Tripadvisor:** 4.6 / 5 from 671 reviews · ranked #9 of 118 Key Largo restaurants

## Design direction

A sixteen-year-old family chocolate-and-ice-cream business with three Florida storefronts — leaning into "Florida Keys family vacation chocolate" with the brand's actual storefront colors (the buildings are literally pink and green at MM 100). Family origin (Bronna's grandmother's bakery, Rich's family Ramer's Chocolates of Minnesota → Florida Keys, 2010) is the editorial spine.

## Fonts

- **Shrikhand** (display headlines) — https://fonts.googleapis.com/css2?family=Shrikhand&display=swap
- **Chivo** (400, 500, 700, 900) — https://fonts.googleapis.com/css2?family=Chivo:wght@400;500;700;900&display=swap

Both are the live site's existing fonts — preserved for brand continuity.

## Color palette (v2 — pink + white + green)

| Token | Hex | Source |
|---|---|---|
| `--pink` | `#E43880` | EXTRACTED from live site `--accent-hsl: 334.88, 76.78%, 56.07%` — primary CTA |
| `--pink-deep` | `#C42667` | Derived darker pink for hover states |
| `--green` | `#5BB85B` | Brand green (logo wordmark + storefront paint) |
| `--green-deep` | `#2D8C3A` | Deeper brand green for headlines |
| `--green-dark` | `#1A4D2E` | Forest green for footer + featured-card dark surfaces |
| `--mint` | `#E8F5E5` | Soft mint — alternating backgrounds |
| `--cream` | `#FBFBF7` | Off-white — secondary backgrounds |
| `--text-dark` | `#1F2D1F` | Body text, slightly green-tinted near-black |
| `--text-body` | `#4A5C4A` | Mid green-gray for body |
| `--gold` | `#D4A85B` | Star-rating accent only |

## Placeholders flagged for client

| Placeholder | Section | What to fill |
|---|---|---|
| `[VERIFIED REVIEWER QUOTE NEEDED]` | Reviews | Featured pull-quote with attribution |
| `[REVIEWER NAME NEEDED]` ×3 / `[REVIEW QUOTE NEEDED]` ×3 | Reviews carousel | Three real reviews |
| North Palm Beach hours | Three Stops + Contact | Confirmed hours |
| North Palm Beach phone | Three Stops + Contact + footer | Direct dial |
| Wholesale email | Site-wide | Source has typo `wholesale@keylargochocolates@gmail.com` — confirm |
| Events phone | FAQ | Source shows (561) 561-2882; build uses corrected (561) 568-2882 |
| **Real storefront exterior photos** | Three Stops location cards | Currently using lifestyle/product photos as placeholders. Recommend Yelp/Instagram-sourced exterior shots of the pink-and-green buildings at MM 100 + Islamorada + North Palm Beach to make these cards more powerful |

## Hotlinking risks

Original site is Squarespace 7.1 (site ID `61f1d14f1e9e3625338b5a5e`). All product photos, the hero image, and the about-section "since 2010" photo were downloaded and committed to `/assets/`. Squarespace can change asset URLs on republish, so re-hosting locally was the safe choice.

## Reference builds consulted

- **Hogan/Redline Golf Academy** (`/Builda/hogan-elite-golf/index.html`) — borrowed mobile-drawer + body-scroll-lock, accordion FAQ, sticky-nav scroll detection with `scroll-padding-top`, horizontal scroll-snap testimonials, and the carousel-arrow disabled-state pattern.
- **Casa Cuevas Cigars** (handoff doc) — borrowed tiered card hierarchy and trust-strip-overlap pattern.

## Mobile accordion behavior

- **Beyond the Counter cards** (`<768px`): summary row (icon + heading) is tappable. Tap the `+` toggle (top-right) or the summary itself to expand. CSS uses `max-height` transitions on `.svc-card-detail`.
- **Signature Sweets cards** (`<540px`): tap the bottom-right `+` toggle to expand the description. Title + price always visible.

## Reviews carousel

- Prev/next arrow buttons (`#revPrev`, `#revNext`) wired in JS. Each click scrolls by one card width. Buttons auto-disable when at the start or end of the scroll range.

## Deploy / handoff

- Single-file build (`index.html`) — all CSS/JS inline. No build step.
- Assets in `/assets/` are committed to the repo.
- Dependencies: Google Fonts CDN + Font Awesome 6 CDN. No others.
- GitHub Pages serves from `main` branch root.
- Favicon currently uses `assets/logo-mobile.png`. For better tab rendering, replace with a true 32×32 / 192×192 PNG.
- The contact form `onsubmit` runs an inline `alert()` placeholder. Wire to Formspree, Netlify Forms, or a Zap to make it functional before launch.
