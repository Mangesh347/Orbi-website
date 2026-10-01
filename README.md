# Orbi website + API

Static pages (landing, features, pricing, checkout, legal, support, uninstall survey) and
zero-dependency Vercel functions in `api/` for Google sign-in, prices with tax, PayPal/Razorpay
checkout, webhooks, and the daily plan-expiry cron. Accounts and plans live in Supabase
(schema: `../supabase/migrations/`).

## Run locally

```bash
npm test                 # API tests with fake Supabase, PayPal and Razorpay
ORBI_DEV=1 npm run dev   # http://localhost:8765 (ORBI_DEV allows http cookies and ?country=IN)
```

Put local env vars in `.env.local` (gitignored). See `.env.example` for the list.

## Deploy

Vercel project with **Root Directory = `website`**. Environment variables come from
`documents/orbi/.env` (outside git). `vercel.json` adds the cron and security headers.
Full checklist: `../ARCHITECTURE.md`.

## Privacy source of truth

- Public policy: `privacy.html`
- Extension copy: `../extension/privacy-policy.html` — keep both in sync.
