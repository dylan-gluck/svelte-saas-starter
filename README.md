# Svelte SaaS Starter

This is a starter template for building a SaaS application using Svelte and SvelteKit.

## Features

- **Authentication**: Supabase
- **Database**: Supabase
- **Payments**: Stripe + Webhooks
- **Styling**: Tailwind CSS
- **UI**: Shadcn UI
- **Testing**: Vitest
- **Deployment**: Docker

## Local Development

### Prerequisites

- Node.js >= 22.0.0
- PNPM >= 9.0.0
- Supabase CLI >= 2.22.6

### Run Project

Install dependencies:

```bash
pnpm install
```

Start local Supabase instance:

```bash
pnpm supabase start
```

Start development server:

```bash
pnpm run dev
```

---

## TODO:
- [x] Project structure and setup
- [ ] Supabase local + remote setup
- [ ] Add shadcn components
- [ ] Dark / Light mode
- [ ] Authentication flow
- [ ] SMTP Setup + Templates
- [ ] Notification Emails
- [ ] DB schema and seed
- [ ] Stripe checkout
- [ ] Stripe webhooks
