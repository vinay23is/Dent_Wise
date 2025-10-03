<h1 align="center">🦷 Dentwise – AI-Powered Dental Platform 🦷</h1>  

<p align="center">
  <img src="/public/screenshot-for-readme.png" alt="Dentwise Screenshot" width="700"/>
</p>  

Dentwise is a **full-stack dental management platform** I engineered to modernize how dental practices interact with patients.  
It combines **appointment scheduling, billing, subscriptions**, and an **AI-driven voice agent**, delivering a platform that is professional, reliable, and future-ready.  

---

## ✨ Features  

- 🏠 Modern landing page with gradients, images, and responsive design  
- 🔐 Authentication via Clerk (Google, GitHub, Email & Password) with 6-digit email verification  
- 📅 Appointment booking system with a 3-step flow (Dentist → Service & Time → Confirm)  
- 📩 Automated email notifications for bookings and invoices (Resend)  
- 📊 Admin dashboard for managing appointments, services, and subscriptions  
- 🗣️ AI voice agent powered by Vapi (Pro feature)  
- 💳 Subscription payments with Clerk (Free + 2 Paid Plans)  
- 🧾 Automatic invoices delivered via email  
- 💸 Smart subscription upgrades (pay only the difference)  
- 📂 PostgreSQL with Prisma ORM for robust persistence  
- 🎨 TailwindCSS + Shadcn for sleek and consistent styling  
- ⚡ TanStack Query for efficient client-side data fetching  
- 🤖 CodeRabbit for AI-assisted PR optimization  
- 🧑‍💻 Clean GitHub workflow with feature branches, PR reviews, and merges  
- 🚀 Deployment on Sevalla (free-tier friendly, scalable hosting)  

---

## 🛠️ Tech Stack  

- **Frontend:** Next.js 14, React 18, TailwindCSS, Shadcn, TanStack Query  
- **Backend:** Next.js API routes, Clerk Auth, Vapi integration, Resend for email  
- **Database:** PostgreSQL + Prisma ORM  
- **Authentication:** Clerk (multi-provider login, JWT sessions, 6-digit code verification)  
- **AI Integration:** Vapi Voice Agent (custom assistant ID + API key)  
- **Payments:** Clerk subscriptions with upgrade/downgrade support  
- **Deployment:** GitHub Actions + Sevalla  
- **Testing/Review:** Jest + CodeRabbit  

---

## ⚙️ Environment Setup  

Create a `.env` file in the root directory:  

```bash
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

DATABASE_URL=your_postgres_database_url

NEXT_PUBLIC_VAPI_ASSISTANT_ID=your_vapi_assistant_id
NEXT_PUBLIC_VAPI_API_KEY=your_vapi_api_key

ADMIN_EMAIL=your_admin_email

RESEND_API_KEY=your_resend_api_key

NEXT_PUBLIC_APP_URL=your_app_url
