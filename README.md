# first-website
Demo restaurant website built for practice.
"# Halal On Fire — Interactive Restaurant Website

## Original Problem Statement
Build an interactive website for **Halal On Fire**, a Mediterranean/halal restaurant in Austin, TX. 13201 Pond Springs Rd Ste 103. Phone (512) 291-2209. 4.7★ · 212 Google reviews. Women-owned. Serves Turkish/Arabic shawarma, lamb wraps, feta fries, baklava, rice pudding.

## User Choices (Feb 18, 2026)
- Scope: Full site — marketing + reservation booking + online ordering (demo cart, no payments)
- Visual: Modern minimalist
- Reviews: Real Google reviews seeded + About Us section
- Extras: Photo gallery / lightbox

## Architecture
- **Backend**: FastAPI + MongoDB (motor). Seeded menu/reviews/popular-times constants. Persists orders, reservations, newsletter.
- **Frontend**: React 19 (CRA + craco) single-page with anchor nav. Tailwind + custom \"Bone/Terracotta/Charcoal\" palette. Cormorant Garamond + Outfit typography. Sonner toasts, framer-motion available.
- **Endpoints**: `/api/menu`, `/api/reviews`, `/api/popular-times`, `/api/info`, `/api/orders` (POST/GET), `/api/reservations` (POST/GET), `/api/newsletter` (POST)

## Implemented (Feb 18, 2026)
- Hero with signature dish, rotating \"Slow · Fire · Halal · Fresh\" badge, live rating strip
- Marquee ribbon of menu items
- About section (women-owned story, stats)
- Interactive Menu — 15 items across 5 categories, sticky category tabs, add-to-cart with toast
- Cart drawer with qty controls, checkout form, tax calc, order confirmation (persists to Mongo)
- Bento-grid photo Gallery with lightbox (prev/next navigation)
- Popular Times chart — interactive day selector, live \"busy\" indicator based on real hour
- Reviews — 6 seeded (real Google reviews inc. Dharshini M, Marisa Perez, SamE)
- Reservation form with confirmation flow
- Contact — hours table (today highlighted), Google Maps embed, feature tags
- Footer with newsletter signup + oversized brand wordmark
- Custom scrollbar, noise overlay, ember pulse animation

## Backlog / Next Ideas (P1/P2)
- P1: Real payment integration (Stripe) — currently demo cart
- P1: Admin dashboard to view submitted orders + reservations
- P1: Instagram feed integration (proof of latest specials)
- P2: Loyalty punch card (\"6 wraps = 1 free\")
- P2: Multi-language (English/Turkish/Arabic)
- P2: SMS confirmation on order/reservation (Twilio)
- P2: Gift card purchase flow

## Test Credentials
None — public site, no auth.
"
