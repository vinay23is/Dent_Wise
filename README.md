# 🦷 Dentwise – AI-Powered Dental Platform

<p align="center">
  <img src="/public/screenshot-for-readme.png" alt="Dentwise Screenshot" width="700"/>
</p>  

Dentwise is a **comprehensive full-stack dental management platform** I designed and built to demonstrate how modern web applications can transform healthcare workflows.
It combines **appointment scheduling, patient communication, subscription billing, and AI voice assistance** into a seamless experience for both **patients** and **administrators**.

This project was engineered as a showcase of **end-to-end software architecture**: from UI/UX design to backend APIs, database schemas, deployment, and DevOps.

---

## ✨ Features

### Patient-Facing Features

* 🏠 **Landing Page**: Responsive, gradient-driven design optimized for accessibility and modern aesthetics.
* 🔐 **Authentication**: Multi-provider login (Google, GitHub, Email & Password) with Clerk + secure email verification via 6-digit code.
* 📅 **Appointment Booking**: A guided **3-step booking flow** (Dentist → Service & Time → Confirmation).
* 📩 **Notifications**: Automated booking confirmation and reminders sent via email (Resend).
* 💳 **Payments & Subscriptions**: Free tier plus paid plans, with Clerk managing billing and subscription status.

### Admin/Dentist Features

* 📊 **Admin Dashboard**: Manage appointments, services, patient records, and subscriptions from a centralized view.
* 🧾 **Invoices**: Automatic PDF invoice generation and delivery by email.
* 💸 **Smart Upgrades**: Users only pay the difference when upgrading their subscription tier.

### Advanced Features

* 🗣️ **AI Voice Agent**: Vapi-powered voice assistant that allows patients to book and interact using natural speech (Pro plan).
* 📂 **Persistent Database**: PostgreSQL + Prisma for relational data integrity and schema management.
* ⚡ **Realtime Updates**: TanStack Query ensures fast client-side data fetching, caching, and invalidation.
* 🤖 **AI-Assisted Development**: CodeRabbit integrated for pull-request optimization and code quality.
* 🚀 **Deployment**: Configured for free-tier friendly hosting on **Sevalla** with GitHub Actions CI/CD pipelines.

---

## 🛠️ Tech Stack

* **Frontend:** Next.js 14, React 18, TailwindCSS, Shadcn, TanStack Query
* **Backend:** Next.js API Routes, Clerk Authentication, Resend for email notifications, Vapi integration
* **Database:** PostgreSQL with Prisma ORM (typed schema, migrations, relationships)
* **Authentication & Authorization:** Clerk with role-based access (Admin, Dentist, Patient)
* **AI Integration:** Vapi Voice Assistant (assistant IDs + API key integration)
* **Payments:** Clerk subscriptions (tiered plans with upgrade/downgrade handling)
* **DevOps:** GitHub Actions (CI/CD), CodeRabbit for automated code review feedback
* **Deployment:** Sevalla (scalable, cost-efficient hosting)
* **Testing:** Jest (unit + integration), snapshot testing for UI components

---

## ⚙️ Environment Setup

Create a `.env` file in the project root:

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

---

## 🚀 Run Locally

```bash
# 1. Clone repository
git clone https://github.com/vinay23is/Dent_Wise.git
cd Dent_Wise

# 2. Install dependencies
npm install

# 3. Run database migrations (if Prisma is used)
npx prisma migrate dev --name init

# 4. Start development server
npm run dev

# 5. Build for production
npm run build
npm start
```

---

## 🧪 Testing

```bash
# Run all tests
npm test

# Run only backend tests
npm run test:api

# Run frontend component tests
npm run test:ui
```

**Test Coverage Includes:**

* ✅ Unit tests for booking logic and invoice generation
* ✅ Integration tests for Clerk authentication, Vapi AI agent, and Resend email service
* ✅ Snapshot tests for React UI components

---



## 📂 Project Structure

```
Dent_Wise/
│── public/                 # Static assets
│── src/
│   ├── components/         # Reusable UI components
│   ├── pages/              # Next.js routes
│   ├── services/           # API calls & business logic
│   ├── prisma/             # Prisma schema & migrations
│   └── utils/              # Helper functions
│── tests/                  # Unit & integration tests
│── .env.example            # Environment variables template
│── package.json            # Dependencies & scripts
│── README.md               # Documentation
```

---

## 🧑‍💻 Author

**Vinay Dodla – Developer & Architect**

* Architected and implemented the **entire stack** from scratch
* Integrated **AI voice technology** with real-time booking flows
* Designed a **scalable database schema** with Prisma + PostgreSQL
* Built a **CI/CD-ready workflow** with GitHub Actions + CodeRabbit
* Deployed on **Sevalla** for a cost-efficient, production-style setup

**Connect with me:** [LinkedIn](https://www.linkedin.com/in/vinay-dodla-695232213/) · [GitHub](https://github.com/vinay23is)

---

## 🤝 Contributions

Contributions are welcome!

1. Fork the repo
2. Create a feature branch (`git checkout -b feature-xyz`)
3. Commit your changes (`git commit -m "Add feature xyz"`)
4. Push to your branch (`git push origin feature-xyz`)
5. Open a Pull Request

---
