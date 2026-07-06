# Dentwise — AI-Powered Dental Booking Platform

A full-stack dental clinic platform for patients to book appointments and talk to an AI voice assistant, and for admins/dentists to manage the schedule — built to show what a production-style healthcare booking app looks like end to end.

**Live Demo:** [dent-wise-olive.vercel.app](https://dent-wise-olive.vercel.app)

<p align="center">
  <img src="/public/screenshot-for-readme.png" alt="Dentwise Screenshot" width="700"/>
</p>

## What problem does this solve?

Booking a dentist appointment is usually a phone call during business hours. This project explores replacing that with a guided self-service flow (pick a dentist → pick a service and time → confirm) plus an AI voice agent for patients who'd rather talk than click, while giving the clinic's admin side a single dashboard to see and manage everything that comes in. I built it to practice tying together auth, a relational database, transactional email, subscription billing, and a third-party voice AI SDK into one coherent app rather than a collection of isolated demos.

## Tech Stack

- **Frontend:** Next.js 15 (App Router), React 19, TailwindCSS 4, shadcn/ui, TanStack Query
- **Backend:** Next.js API routes / server actions, Clerk (auth + subscription billing)
- **Database:** PostgreSQL + Prisma ORM
- **AI:** Vapi voice assistant SDK (`@vapi-ai/web`) — real-time voice booking, gated behind the Pro plan
- **Email:** Resend + React Email components for booking confirmations
- **Deployment:** Vercel

## Architecture

- **Auth & billing** run through Clerk end-to-end: sign-in (Google/GitHub/email), role context, and the Pro subscription tier are all Clerk primitives — `middleware.ts` runs `clerkMiddleware()` on every route except static assets, and `/pro` renders Clerk's `PricingTable` component directly rather than a hand-rolled checkout flow.
- **Data model** (`prisma/schema.prisma`) is three tables: `User` (synced from Clerk via `clerkId`), `Doctor`, and `Appointment`, which foreign-keys to both with `onDelete: Cascade`. Server actions in `src/lib/actions/` (`appointments.ts`, `doctors.ts`, `users.ts`) are the only things that talk to Prisma — no direct DB calls from components.
- **Booking flow** lives under `src/app/appointments`, backed by `use-appointment.ts` and `use-doctors.ts` hooks with TanStack Query for caching/invalidation after a booking is created.
- **Admin dashboard** (`src/app/admin`) is a client component (`AdminDashboardClient.tsx`) that reads appointments via the same server actions patients' bookings write to — one data path, two consumers.
- **Voice assistant** (`src/app/voice`, `src/components/voice/VapiWidget.tsx`) instantiates the Vapi SDK client-side with a public API key and assistant ID, and is only shown to users on the Pro plan (`ProPlanRequired.tsx` gates the feature).
- **Email**: booking confirmations are rendered as React Email templates (`src/components/emails/`) and sent via Resend from `/api/send-appointment-email`.

## Key Features

- Multi-provider auth (Google, GitHub, email/password) via Clerk, with 6-digit email verification
- Guided 3-step appointment booking (dentist → service & time → confirmation)
- Automated booking confirmation emails via Resend + React Email
- Tiered subscriptions (free / Pro) managed entirely through Clerk's billing primitives
- AI voice agent (Vapi) for natural-language appointment booking, available on the Pro plan
- Admin dashboard for managing appointments, doctors, and patient records
- Typed, relational schema (Prisma + PostgreSQL) with cascading deletes between users, doctors, and appointments

## Interesting Engineering Decisions

- **Billing and pricing UI delegated to Clerk's `PricingTable` component** instead of building a custom Stripe checkout — fewer moving parts to get wrong on the payment side, at the cost of being tied to Clerk's billing feature set.
- **One set of server actions shared by both patient and admin views** — the admin dashboard doesn't have a separate "admin API," it calls the same `getAppointments()`-style actions patients' bookings write through, which keeps the data logic in one place instead of duplicating query logic per role.
- **Voice booking is explicitly plan-gated in the UI** (`ProPlanRequired.tsx`), not just documented as a "future feature" — the free vs. Pro boundary is enforced in the component tree.

## Running Locally

```bash
git clone https://github.com/vinay23is/Dent_Wise.git
cd Dent_Wise
npm install
```

Create a `.env` file:
```bash
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
DATABASE_URL=your_postgres_database_url
NEXT_PUBLIC_VAPI_ASSISTANT_ID=your_vapi_assistant_id
NEXT_PUBLIC_VAPI_API_KEY=your_vapi_api_key
ADMIN_EMAIL=your_admin_email
RESEND_API_KEY=your_resend_api_key
NEXT_PUBLIC_APP_URL=your_app_url
```

```bash
npx prisma migrate dev --name init   # set up the database schema
npm run dev                          # http://localhost:3000
```

Production build:
```bash
npm run build
npm start
```

## Author

**Vinay Dodla** — architected and built the full stack, including the booking flow, Prisma schema, Clerk auth/billing integration, and Vapi voice assistant integration.

[LinkedIn](https://www.linkedin.com/in/vinay-dodla-695232213/) · [GitHub](https://github.com/vinay23is)
