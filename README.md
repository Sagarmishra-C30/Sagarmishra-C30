# Sagar Mishra

Full stack engineer working in Python, Flask, and MySQL. Since 2023 I've been the only engineer at [Jaey](https://www.jaey.in), a D2C fashion brand in Mumbai, building and running its storefront, payments, accounting, inventory, and servers.

## Work

My day-to-day code lives in the company's private repositories ([5,000+ contributions since July 2023](https://github.com/SagarMishra-jaey) on my work account), so here's what I built there:

- **Payments.** Migrated from Razorpay to Cashfree with both gateways running side by side behind a switch, then added one-click checkout and a circuit breaker that falls back to Razorpay during a Cashfree outage. Webhooks and refunds are safe to retry: deduplication on the gateway's payment ID, and refund IDs reused as idempotency keys.
- **Money and accounting.** A wallet and gift cards built on expiring credit lots, with row-locked spends and a balance computed from the lots. GST invoicing with gapless numbering under concurrent workers, credit notes, and the exports the books are kept in.
- **Orders and operations.** The order and item status timeline, an audited status-reversal tool, Blue Dart shipping with returns and exchanges, and a barcode/QR inventory system with a Windows label-printing app (code signing, auto-update, CI releases).
- **Platform.** Exports and notifications run on workers on a second server with a MySQL read replica, draining a job queue built in the main database (`SKIP LOCKED` claims, leases, backoff); tuning cut the workers' database statement volume from 1M a day to 28K. Production MySQL upgraded from 8.0 to 8.4 with about six seconds of downtime. TLS and least-privilege database logins, nightly backups with a passed restore drill, and a watchdog that restarts or redeploys on failed health checks.
- **Performance.** Per-request query counting, then batching: admin order lists went from 2,136 queries a page to 14.
- **Storefront.** A redesign on a new design system, a made-to-measure flow, and side-cart checkout with OTP login.

## Personal projects

- **[aniknow](https://github.com/Sagarmishra-C30/aniknow)**: local-first anime tracking and discovery. Next.js, React, TypeScript, IndexedDB.
- **[AniNotch](https://github.com/Sagarmishra-C30/AniNotch)**: Python automation that keeps an anime watchlist in Notion up to date from the Jikan API.
- **paisa**: offline Android finance app that turns bank SMS and statements into a reconciled ledger. Expo/React Native, TypeScript. No network permission by design. Source private for now.

[LinkedIn](https://www.linkedin.com/in/sagar-mishra-developer) · sagarmishra.code@gmail.com
