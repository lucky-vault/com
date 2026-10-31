# Lucky Vault — Premium Website Foundation

This is a redesigned, premium black-and-gold website foundation for Lucky Vault. It includes original generated vault artwork, responsive layouts, SEO metadata, a PWA manifest, service worker, and dedicated account/game/rules/support pages.

## Important implementation status

This is a polished frontend foundation, not a live-money gambling service. It deliberately does not simulate cash balances, accept deposits, create wagers, generate browser-side cash outcomes, or claim that payments and withdrawals work.

The game, registration and sign-in pages explain when their secure services are not connected. This avoids collecting passwords or money through a static website with no verified backend.

## Files

- `index.html` — premium landing page
- `game.html` — vault game entry screen (requires secure game API)
- `login.html`, `register.html` — account UI (requires secure authentication)
- `rules.html`, `responsible-play.html`, `privacy.html`, `terms.html`, `support.html`
- `styles.css`, `app.js`
- `assets/royal-vault-hero.webp`, `assets/vault-card.webp`, `assets/favicon.svg`
- `manifest.webmanifest`, `service-worker.js`, `robots.txt`, `sitemap.xml`

## Before publishing

1. Replace `YOUR-DOMAIN.example` in `robots.txt` and `sitemap.xml` with the final HTTPS domain.
2. Update the canonical URL and Open Graph image URL in `index.html` to the final domain.
3. Add the final operator's legal name, contact details, privacy terms, and jurisdiction-specific notices.
4. Test on mobile and desktop over HTTPS.
5. Submit the real sitemap URL in Google Search Console. Indexing is not guaranteed and SEO does not guarantee traffic.

## Backend required before real-money functionality

The recommended architecture is a trusted server plus PostgreSQL (Nhost can be used for authentication and database hosting). Never calculate cash-game outcomes or wallet balances in browser JavaScript.

Minimum backend services:
- verified authentication, age/identity checks and jurisdiction checks;
- server-side game engine with cryptographically secure randomness, published odds and independently auditable outcome records;
- immutable wallet ledger, idempotent transaction processing and reconciliation;
- payment-provider webhooks with signature verification;
- deposit and withdrawal risk controls;
- admin roles with least-privilege permissions, audit trails and dual approval for sensitive actions;
- rate limiting, abuse monitoring, backups, incident response and security testing;
- responsible-gaming limits, time-outs and self-exclusion.

Do not activate deposits, withdrawals or real-money wagering until qualified legal counsel and the relevant regulator/payment providers confirm that the operator is authorised to offer the service in each target jurisdiction. Nigerian requirements may vary by the applicable federal/state framework and current court/regulatory position; obtain current local legal advice before launch.
