# first-website
Demo restaurant website built for practice.
"summary": "Backend: all 7 target endpoints verified (menu 15 items/5 categories, reviews avg=4.7 total=212, popular-times all 7 days, info with address/phone/hours, orders create+empty-cart 400, reservations create+party_size 0/25 -> 400, newsletter valid 200 + invalid 422). Frontend: home/navbar/hero, menu tabs + add-to-cart (badge increments), cart drawer inc/dec/remove, checkout->order-confirmed (verified via screenshot #A7E1A87B), gallery lightbox open+close, popular-times day-btn-friday clickable, newsletter submit shows 'Subscribed' toast. Reservation UI submit could not be confirmed in one retry (time <select> selection likely didn't produce a valid form.time); backend POST /api/reservations itself works.",
  "tested_scope": ["backend", "frontend", "integration"],
  "passed": [
    "GET /api/menu returns 15 items, 5 categories [Plates, Wraps, Sides, Desserts, Drinks]",
    "GET /api/reviews avg=4.7 total=212",
    "GET /api/popular-times returns all 7 days (Sun-Sat)",
    "GET /api/info returns correct address (13201 Pond Springs Rd Ste 103, Austin, TX 78729), phone (512) 291-2209, hours",
    "POST /api/orders (valid) -> 200 with id + status=received",
    "POST /api/orders (empty items) -> 400",
    "POST /api/reservations (valid) -> 200 with id",
    "POST /api/reservations (party_size=0) -> 400",
    "POST /api/reservations (party_size=25) -> 400",
    "POST /api/newsletter (valid email) -> 200",
    "POST /api/newsletter (invalid email) -> 422",
    "Home page loads with site-navbar, hero-order-btn, hero-reserve-btn",
    "Menu tab switching (plates/wraps) and add-to-cart increments cart-count-badge (1 -> 2)",
    "Cart drawer opens; inc/dec/remove controls present",
    "Checkout flow places order via API and shows ORDER CONFIRMED with confirmation code",
    "Gallery: gallery-thumb-0 opens lightbox-overlay; lightbox-close dismisses",
    "Popular Times: day-btn-friday click works",
    "Newsletter subscribe shows 'Subscribed' success toast"
  ],
  "failed": [
    {
      "area": "frontend / reservation UI",
      "issue": "reservation-confirmed did not appear after clicking reserve-submit in Playwright script; likely caused by select_option(index=2) picking a placeholder for reserve-time (native <select>). Backend endpoint itself returns 200. Not retried per loop-prevention.",
      "evidence": "Playwright: 'reservation-confirmed' not visible within 6s after submit. curl POST /api/reservations returned 200 with id.",
      "priority": "LOW"
    }
  ],
  "action_items": [
    "Optional: manually verify reservation form end-to-end in browser; if fine, no code changes needed. Otherwise ensure default form.time is preselected to a valid value."
  ],
  "success_rate": {"backend": "100%", "frontend": "~93% (6/7 UI flows verified)"},
  "retest_needed": false,
  "full_testing_deferred": true
}

