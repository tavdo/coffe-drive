# Georgian Coffee Drive — ყავა

A premium drive-thru coffee experience, designed for Batumi, Georgia.

Single-file, vanilla HTML / CSS / JavaScript. No build step, no dependencies.

## What's inside

```
.
├── index.html       Customer-facing site (menu, pre-order, payment)
├── admin.html       Admin console (orders, price editor, locations)
├── hero-bg.png      Hero background photograph
└── README.md
```

## Features

### Customer site — `index.html`
- Full-screen hero with animated steam / rings / cup
- Tabbed menu (Espresso · Cold Brew · Georgian Specials · Pastries)
- Live cart with quick-buy overlay and fly-to-cart animation
- Pre-order form (name, phone, pickup time, location, note)
- Checkout modal with **Apple Pay**, **Google Pay**, and **card** (Visa / Mastercard / Amex / Discover)
- Client-side Luhn validation and card brand detection
- Three Batumi locations with live open/closed status
- Scroll-reveal micro-animations, Georgian accent typography

### Admin console — `admin.html`
- Passcode login (default `1234`)
- **Live dashboard** — today's orders, revenue, in-progress, ready
- **Orders queue** with one-click status workflow: `New → Preparing → Ready → Completed`
- **Menu editor** — edit prices inline, toggle availability, changes sync instantly to the customer site
- **Locations** — live open/closed + today's order count
- Bell notifications, chime on new order, optional desktop notifications
- CSV export of all orders

### Live sync
The customer page and admin console talk to each other in real time via the browser's `BroadcastChannel` + `localStorage`:

- Customer places an order → admin tab chimes and shows the new card instantly
- Admin edits a price → customer tab re-renders its menu with the new price
- Admin toggles an item off → it disappears from the customer menu

All state persists across reloads (per browser). When a real backend is added later, the same UI can be pointed at `fetch()` endpoints.

## Getting started

Just open the files in a browser. No server required.

```bash
# Windows
start index.html
start admin.html
```

Or serve them with any static server for `BroadcastChannel` to work across origins:

```bash
npx serve .
```

## Admin access

Default passcode: **`1234`** — change it in Admin → Settings.

## Brand

- Colors: espresso `#0F0800`, cream `#FDF9F0`, gold `#D4AF37`
- Typography: Cormorant Garamond (display) · Jost (sans) · JetBrains Mono (numerics)
- Tone: slow, warm, confident

---

Built in Batumi. ყავა გვიყვარს.
