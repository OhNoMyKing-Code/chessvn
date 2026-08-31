# ChessVN 🇻🇳♟️

**ChessVN — Play. Improve. Compete.**

Production-ready Phase 1 foundation for a Vietnamese chess platform.

## Included

- Next.js + TypeScript
- Responsive ChessVN UI
- Chess board using chess.js
- PostgreSQL + Prisma schema
- Premium / Pro pricing
- Stripe Checkout abstraction
- Stripe webhook signature verification
- GitHub Actions CI/CD
- Environment-based app URL and Stripe Price IDs
- Vietnamese-first UX

## Local setup

```bash
npm install
cp .env.example .env
# Fill DATABASE_URL and Stripe variables
npx prisma generate
npx prisma db push
npm run dev
```

Open http://localhost:3000

## Stripe

Create four Stripe recurring Prices and put their IDs in `.env`.

Use Stripe CLI during development:

```bash
stripe listen --forward-to localhost:3000/api/stripe/webhook
```

Then copy the webhook signing secret to `STRIPE_WEBHOOK_SECRET`.

## GitHub Actions

Add these repository/environment secrets:

- DATABASE_URL
- NEXT_PUBLIC_APP_URL
- AUTH_SECRET
- STRIPE_SECRET_KEY
- STRIPE_WEBHOOK_SECRET
- STRIPE_PREMIUM_MONTHLY_PRICE_ID
- STRIPE_PREMIUM_YEARLY_PRICE_ID
- STRIPE_PRO_MONTHLY_PRICE_ID
- STRIPE_PRO_YEARLY_PRICE_ID

For production, deploy the Next.js app to a Node-compatible host. GitHub Actions builds/tests and performs deployment; it should not be treated as a permanent web server.

## Phase 2

- Auth.js real accounts
- Realtime WebSocket games
- matchmaking
- Redis
- persistent game state
- real Stockfish workers
- tournaments
- clubs
- social graph
- anti-cheat
- admin dashboard
- subscription reconciliation
- invoices and cancellation UI

All branding is ChessVN; no legacy brand names are used.
