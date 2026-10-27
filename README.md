# Subscription Manager

A single-page web app for tracking your subscriptions. Add, edit, and delete subscriptions, see your weekly / monthly / yearly spend at a glance, browse payments on a calendar, and get a notification when something is due — through NTFY or Gotify.

> Based on the open-source [subscription-manager](https://github.com/dh1011/subscription-manager) project (MIT licensed), with my own fixes and cleanup on top.

## Features

- Add, edit, and delete subscriptions
- Calendar view of upcoming payments
- Weekly, monthly, and yearly cost totals
- Per-account summaries and cost trend charts
- Multi-currency support — each subscription stores its own currency
- Payment reminders via NTFY or Gotify
- Custom icons for each subscription (Iconify)

## Tech Stack

- Next.js (React + TypeScript)
- SQLite (local file database, no external services needed)
- Docker (optional)

## Getting Started

Requires Node.js 18+.

```bash
git clone https://github.com/MatrixWorkflows/subscription-manager.git
cd subscription-manager
npm install
npm run dev
```

Open `http://localhost:3000`. To load demo data, visit `/api/seed` once.

### Production build

```bash
npm run build
npm start
```

### Docker

```bash
docker-compose up -d
```

This builds the app from the included Dockerfile and serves it on port 3000, with data persisted to `./data`.

## Notifications

Open the Settings page, pick NTFY or Gotify, and enter your server details (NTFY topic and domain, or Gotify URL and app token). Reminders fire at midnight local time for any subscription that has Notify enabled and a payment due that day. The Test Notification button checks that delivery works from the app server before you rely on it.

## Changes in this fork

- Windows-friendly `dev` / `build` scripts — replaced Unix inline env vars with `cross-env`
- Next.js upgraded to 14.2.35 (patches a published security advisory)
- Removed an unused `CurrencySettingsModal` component and its styles

## License

MIT — see [LICENSE](LICENSE).
