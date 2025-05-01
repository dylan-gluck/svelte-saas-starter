# Svelte SaaS Starter

This is a starter template for building a SaaS application using Svelte and SvelteKit.

## Features

- **DB + Auth**: Supabase
- **Payments**: Stripe
- **Styling**: Tailwind
- **UI**: Shadcn UI

## Local Development

### Prerequisites

- Node.js >= 22.0.0
- PNPM >= 9.0.0
- Stripe CLI >= 1.26.1

Stripe CLI:

```bash
stripe login
```

Supabase Local Setup (Optional):

```bash
pnpm supabase init
pnpm supabase start
```

## Setup

Create .env.local file:

```bash
pnpm run db:setup
```

### Run Project

Install dependencies:

```bash
pnpm install
```

Start development server:

```bash
pnpm run dev
```

---

## TODO:
- [x] Project structure and setup
- [x] Supabase local + remote setup
- [x] Add Shadcn UI
- [x] Dark / Light mode
- [x] Authentication flow
- [ ] Homepage UI
- [ ] Pricing Page UI
- [ ] DB schema and seed
- [ ] Stripe checkout
- [ ] Stripe webhooks
- [ ] Paywall
- [ ] User Settings
- [ ] SMTP Setup + Templates
- [ ] Notification Emails
