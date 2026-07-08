# SP Company — Mobile App Prototype

An interactive, self-contained prototype of the **SP Company** buyer app — a Japanese
used-vehicle **B2B export marketplace**. Every screen is real and tappable: browse and
bid, get a landed-cost (Total CIF) quote, pay, and track the ship to your port.

**▶ Live:** https://hgs-pro.github.io/sp-mobile-app/ &nbsp;·&nbsp; **Private link:** https://claude.ai/code/artifact/048e3f01-c10d-4327-9b5a-78742685971c

| | |
|---|---|
| **Screens** | 65 interactive screens |
| **Account types** | Buyer & Dealer (minor info differences) |
| **Theme** | Light & dark |
| **Frame** | iPhone 14 Pro Max (430×932) on desktop; full-screen on mobile |
| **Dependencies** | None — one self-contained `index.html` (+ `sp-lib.css`), images embedded as data-URIs |

## How to explore

- **⚏ All screens** — floating button opens a navigator grouped by area (fastest way to reach every screen).
- **Buyer ⇄ Dealer** — profile avatar → *Account type*. The dealer view adds Business Information + a company identity.
- **Dark mode / Language** — same account menu, Settings, or the navigator.

## Feature areas

- **Onboarding & Auth** — buyer/dealer sign-up (3 steps), email OTP, phone verify, 2FA login, password/email recovery.
- **Home & Search** — search, SP-vs-foreign stock, category filters, advanced-search sheet, featured / recently-viewed / heavy-equipment / live-auction rails, saved searches with alerts.
- **Vehicle & Detail** — gallery, Overview/Specs/Features tabs, FOB→Total-CIF breakdown, buyer protection, staff, reviews; heavy-equipment listings + detail.
- **Buying & Payment** — inquiry cart, checkout, reusable secure-payment sheet (card/bank/wallet), quotes + detail, negotiation threads.
- **Orders & Logistics** — 12-step order tracker (with the optional local-service branch), shipment tracking, **live vessel map**, invoices, consignee CRUD.
- **Auctions** — live lot list + bidding with **Max Auto-Bid (proxy)**, 11-field Japanese auction sheet, leaderboard, ¥/$ toggle, calendar, cost calculator, my bids, won lots, how-it-works.
- **Dashboard & Rewards** — membership ring, sparklines, spending/order charts, purchases, points, coupons, savings, referral, badges, redeem.
- **Account & Support** — wallet (add funds / withdraw / statement), profile & KYC + representative info, settings, full chat (typing, receipts, quick replies), notifications, buyer reviews.

## How it's built

- **Single-file screen router** — a small JS IIFE handles slide transitions, the tab bar, and bottom-sheets. No framework.
- **Design system** — components from SP's mobile library; brand `#276EF1`, embedded Uber Move type, a marketing accent palette (gradient section titles, multi-colour icons). Everything is CSS-variable themed, so dark mode is a one-class switch.
- **Grounded in the codebase** — the order process, auction sheet, proxy-bidding, buyer/dealer split, and consignee/representative fields mirror the real SP web product.

## Files

```
index.html    the app (screens + inline router + inline styles)
sp-lib.css    the SP mobile component library (extracted, with embedded fonts)
.nojekyll     serve as-is on GitHub Pages
```

This prototype makes **zero external requests** — car photos are baked in as data-URIs and
all styles are inlined, so it renders identically on the web and inside the private link.
