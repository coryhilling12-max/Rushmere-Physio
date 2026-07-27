# Handoff: Rushmere Physio — Homepage Redesign

## Overview
A full homepage redesign for Rushmere Physio, a physiotherapy clinic at 154 Colchester Road, Ipswich IP4 4RS. Goals: calm, professional, trustworthy; simplified navigation; credibility (Olympics/Paralympics, Ipswich Town FC) surfaced prominently; uniform pricing cards; always-visible "Book Online 24/7" CTA; working embedded map; fully mobile-responsive.

## About the Design Files
The files in this bundle are **design references created in HTML** — a prototype showing intended look and behavior, not production code to copy directly. The task is to **recreate this design in the target codebase's existing environment** (React, Vue, plain HTML/CSS, WordPress theme, etc.) using its established patterns — or, if no environment exists yet, choose the most appropriate stack (a static site or simple CMS template is ideal for this brochure site) and implement the design there.

Notes on the prototype's mechanics you should NOT replicate literally:
- `Rushmere Physio Homepage.dc.html` uses a proprietary streaming component runtime (`support.js`, `<x-dc>`, `{{ holes }}`, `<sc-for>` loops). Treat it as a template: the markup + inline styles are the design spec; the loops just repeat card markup over the data arrays listed at the bottom of the file.
- `image-slot.js` is a drag-and-drop image placeholder component. In production, replace every `<image-slot>` with a plain `<img>` (object-fit: cover) using the same `src`.

## Fidelity
**High-fidelity.** Colors, typography, spacing, copy and imagery are final-intent. Recreate pixel-perfectly.

## Page Structure (single page, top to bottom)

### 1. Top bar
- Background #1e3a4c, text #cfe1ec, 14px, padding 8px 24px, items centered, flex-wrap, gap 8px 28px.
- Content: address · phone link (white, 600) · email link.

### 2. Navigation (sticky)
- position: sticky; top: 0; z-index: 50; background #ffffff; border-bottom 1px solid #e3ecf2; padding 12px 24px; flex, space-between, wrap.
- Left: logo image 44×44 circle + "Rushmere Physio" (Manrope 800, 20px, #1e3a4c).
- Right: links Home / Our Team / Services / Pricing / Contact (Manrope 600, 15px, #46606f, gap 22px) + primary pill button "Book Online 24/7".
- All in-page links are anchor links (#top, #team, #services, #pricing, #contact).

### 3. Hero
- Container max-width 1140px, padding 64px 24px 56px; CSS grid `repeat(auto-fit, minmax(300px, 1fr))`, gap 48px, align-items center.
- Left column (flex column, gap 20px):
  - Eyebrow: "CHARTERED PHYSIOTHERAPY · IPSWICH" — Manrope 700, 14px, letter-spacing 0.08em, uppercase, #6ba54a.
  - H1: "Expert hands-on physiotherapy, close to home" — Manrope 800, clamp(34px, 5vw, 52px), line-height 1.1, #1e3a4c.
  - Sub: "From everyday aches to elite sport — we find what's wrong, and guide you back to doing what you love." — 19px, line-height 1.6, max-width 46ch.
  - Buttons row (gap 14px): primary "Book Online 24/7"; secondary outline "Call (01473) 718552" (border 2px solid #b9cfe4, text #1e3a4c, hover border/text #35789e).
  - Trust line: "HCPC registered · Wheelchair accessible · Free off-road parking" — 14px, #7b93a1.
- Right column: photo (uploads/back massage.avif), rounded 20px, min-height 380px, object-fit cover.

### 4. Credibility band
- Background #1e3a4c, padding 56px 24px. H2 centered white Manrope 800 30px: "Experience trusted at the highest level".
- 3 cards, grid auto-fit minmax(260px,1fr), gap 20px. Card: background rgba(255,255,255,0.06), border 1px solid rgba(255,255,255,0.12), radius 16px, padding 28px. Title Manrope 800 20px #b5e07f; body #cfe1ec, line-height 1.6.
- Cards: "Olympic & Paralympic Games", "Ipswich Town FC", "Athletes & everyday patients" (copy in the HTML file).

### 5. Our Team (#team)
- Max-width 1140px, padding 72px 24px. Centered H2 (Manrope 800 32px #1e3a4c) "Meet your physiotherapists" + sub "Every physiotherapist at Rushmere Physio is Chartered, HCPC registered, and qualified in acupuncture."
- Grid auto-fit minmax(170px,1fr), gap 28px. Each member: 140×140 circular photo, name (Manrope 700 17px #1e3a4c), role (14px #7b93a1).
- Members & photos:
  - James Lee-Barrett — Lead Physiotherapist — uploads/james.webp
  - Mark Alderton — Associate Physiotherapist — uploads/Mark Alderton Associate Physiotherapist.webp
  - Andrew Bannan — Associate Physiotherapist — uploads/Andrew Bannan Associate Physiotherapist.webp
  - Ryan Vicencio — Associate Physiotherapist — uploads/Ryan Vicencio Associate Physiotherapist.webp
  - Kimberley Maddalena — Associate Physiotherapist — uploads/kimber.webp

### 6. Services (#services)
- Background #edf4f9, padding 72px 24px. Centered H2 "How we can help" + sub.
- Grid auto-fit minmax(280px,1fr), gap 20px. Card: white, radius 16px, overflow hidden, shadow 0 1px 3px rgba(30,58,76,0.06); photo strip 170px tall (object-fit cover) + body padding 22px 24px 26px; title Manrope 700 19px #1e3a4c; body line-height 1.6.
- Cards (title — photo):
  - Physiotherapy & manipulation — uploads/neck pain.jpg
  - Sports injury rehabilitation — uploads/feet view running.jpg
  - Acupuncture — uploads/acupunc.jpg
  - Shockwave therapy — uploads/shock wave.avif
  - Ostenil® Plus injections — uploads/arthritis.jpg
  - Steroid & Arthrosamid injections — uploads/injection.jpg
  (Descriptions are in the HTML file's `services` array.)

### 7. Pricing (#pricing)
- Max-width 1140px, padding 72px 24px. Centered H2 "Appointments & pricing" + sub "Clear, upfront pricing. Book instantly online — no referral needed."
- Grid auto-fit minmax(215px,1fr), gap 20px, align-items stretch. Card: white, border 1px solid #e3ecf2, radius 16px, padding 28px 24px, centered flex column; name Manrope 700 18px (min-height 44px); price Manrope 800 30px #35789e; duration 14px #7b93a1 (min-height 20px); "Book Now" primary pill pinned to bottom via margin-top auto.
- Items: Initial Assessment — from £50 — 25–30 minutes; Follow-up Session — from £50 — 25–30 minutes; Corticosteroid Injection — £140; Ostenil® Plus — £260; Arthrosamid — £2400.

### 8. How does physiotherapy work?
- Background #f0f8e6, padding 72px 24px. Centered H2.
- 3 cards, grid auto-fit minmax(260px,1fr), gap 20px. Card: white, radius 16px, padding 32px 28px, centered; numbered badge 52px circle background #b5e07f, number Manrope 800 22px #2c4a12; title Manrope 700 19px; body line-height 1.65. Copy in `steps` array.

### 9. Booking CTA band
- Background #35789e, padding 64px 24px, centered column max-width 760px, gap 24px.
- H2 white Manrope 800 30px: "Not sure we can help? We're confident we will."
- Green CTA pill: background #b5e07f, text #1e3a4c, Manrope 800 17px, padding 16px 40px, hover background #ffffff.
- Hours card: rgba(255,255,255,0.1), radius 14px, padding 20px 32px, 2-col grid gap 6px 32px, white 16px: Mon–Fri 07:30–20:00; Saturday 07:30–15:30; Sunday Closed (#cfe1ec).

### 10. Contact (#contact)
- Max-width 1140px, padding 72px 24px, grid auto-fit minmax(300px,1fr), gap 40px.
- Left: H2 "Find us"; intro paragraph; labelled rows (label: Manrope 700 13px uppercase letter-spacing 0.06em #7b93a1) for Address / Phone / Email; areas-served line 15px #7b93a1.
- Right: embedded map, radius 20px, border 1px solid #e3ecf2, min-height 380px. Prototype uses an OpenStreetMap embed (no API key, no cookie wall):
  `https://www.openstreetmap.org/export/embed.html?bbox=1.16846%2C52.06403%2C1.18946%2C52.07603&layer=mapnik&marker=52.07003%2C1.17896`
  Google Maps embed is fine too if consent handling is in place — the current live site's consent-gated embed appears broken; whatever is used must load by default.

### 11. Footer
- Background #1e3a4c, padding 40px 24px, text #9fb8c7.
- Row 1: logo 36px circle + "Rushmere Physio" (white, Manrope 700 17px) | nav links + "Book Online" in #b5e07f.
- Row 2 (top border rgba(255,255,255,0.12)): copyright + Privacy Policy / Terms / Cookies links, 13px. Legal pages are folded into the footer per the brief (no nav items for them).

## Interactions & Behavior
- Every "Book Online" / "Book Now" button links to the live booking system: **https://physio.connect.tm3app.com/** (open in same tab or new tab per client preference). One consistent button style everywhere.
- Phone numbers use `tel:01473718552`; email uses `mailto:physio@ipswichphysio.com`.
- Nav is sticky so the Book Online CTA is always visible.
- Button hovers: primary #35789e → #1e3a4c; outline: border/text → #35789e; green CTA → white. No other animations.
- Responsive: all multi-column areas are `grid-template-columns: repeat(auto-fit, minmax(Npx, 1fr))` and flex-wrap — they collapse naturally to one column on phones with no media queries. Keep tap targets ≥ 44px.

## State Management
None — fully static page. No forms, no JS state required beyond whatever the target stack needs for the map embed.

## Design Tokens
Colors:
- Ink / deep blue: #1e3a4c (top bar, credibility band, footer, headings)
- Primary blue: #35789e (buttons, prices, links); hover: #1e3a4c
- Body text: #46606f; muted: #7b93a1; light-on-dark: #cfe1ec; footer text: #9fb8c7
- Accent green: #b5e07f (badges, green CTA, footer highlight); dark green text on green: #2c4a12; eyebrow green: #6ba54a
- Tints: page #fcfdfe; blue section #edf4f9; green section #f0f8e6; borders #e3ecf2; outline border #b9cfe4

Typography:
- Headings/buttons: Manrope (Google Fonts), weights 600–800
- Body: Source Sans 3 (Google Fonts), 400/600
- Scale: H1 clamp(34–52px)/1.1 · H2 30–32px · card titles 19–20px · body 16–17px/1.6 · small 13–15px

Radii: cards 16px, hero image/map 20px, hours card 14px, buttons 999px (pill).
Shadow: cards 0 1px 3px rgba(30,58,76,0.06).
Spacing: section padding 72px 24px (bands 56–64px); content max-width 1140px; grid gaps 20–48px.

## Assets (in this bundle, client-supplied)
- uploads/logo-1785192618979.jpg / uploads/Logo white background.jpg — clinic logo (white background; display in a circle or on white)
- Team headshots: james.webp, Mark Alderton…, Andrew Bannan…, Ryan Vicencio…, kimber.webp
- Photos: back massage.avif (hero), neck pain.jpg, feet view running.jpg, acupunc.jpg, shock wave.avif, arthritis.jpg, injection.jpg

## Files
- `Rushmere Physio Homepage.dc.html` — the full design (markup, inline styles, copy, data arrays)
- `image-slot.js` — prototype-only image placeholder component (replace with <img> in production)
- `uploads/` — all images
