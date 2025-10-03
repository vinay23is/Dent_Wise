

````markdown
<h1 align="center">🦷 Dentwise – AI-Powered Dental Platform 🦷</h1>  

<p align="center">
  <img src="/public/screenshot-for-readme.png" alt="Dentwise Screenshot" width="700"/>
</p>  

Dentwise is a **full-stack dental management platform** I engineered to modernize how dental practices interact with patients.  
It combines **appointment scheduling, billing, and subscriptions** with an **AI-driven voice agent** for next-generation patient engagement.  

The platform is built with scalability, security, and developer best practices in mind — ready to handle real-world use cases while being free-tier deployment friendly.  

---

## ✨ Core Highlights  

- 🏠 **Modern Landing Page** with gradients, responsive design, and professional visuals  
- 🔐 **Authentication** via Clerk (Google, GitHub, Email & Password) + 6-digit Email Verification  
- 📅 **Smart Appointment Booking** with a guided 3-step flow (Dentist → Service & Time → Confirm)  
- 📩 **Email Notifications** for every booking and confirmation (via Resend)  
- 📊 **Admin Dashboard** to manage appointments, subscriptions, and users  
- 🗣️ **AI Voice Agent** powered by Vapi for real-time patient interaction (Pro feature)  
- 💳 **Subscriptions & Payments** with Clerk (Free plan + 2 Paid tiers)  
- 🧾 **Automatic Invoices** sent to user inboxes  
- 💸 **Smart Subscription Upgrades** (pay only the difference when upgrading)  
- 📂 **Persistent Database Layer** with PostgreSQL + Prisma  
- 🎨 **Tailwind CSS + Shadcn** for sleek, responsive styling  
- ⚡ **TanStack Query** for reactive and efficient data fetching  
- 🤖 **CodeRabbit** for AI-assisted PR feedback and optimization  
- 🧑‍💻 **GitHub Workflow** with feature branches, PR reviews, and clean merges  
- 🚀 **Deployment** on Sevalla (optimized for free-tier hosting and scaling)  

---

## 🛠️ Tech Stack  

- **Frontend:** Next.js 14, React 18, TailwindCSS, Shadcn, TanStack Query  
- **Backend:** Next.js API routes, Clerk authentication, Vapi integration, Resend for email  
- **Database:** PostgreSQL + Prisma ORM  
- **Authentication:** Clerk (multi-provider login, JWT sessions, email code verification)  
- **AI Integration:** Vapi Voice Assistant (custom agent IDs + API keys)  
- **Payments:** Clerk subscriptions with upgrade/downgrade support  
- **DevOps & Deployment:** GitHub Actions + Sevalla Hosting  
- **Testing/Review:** Jest + CodeRabbit (PR-level optimization feedback)  

---

## ⚙️ Environment Setup  

Create a `.env` file in the root:  

```bash
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

DATABASE_URL=your_postgres_database_url

NEXT_PUBLIC_VAPI_ASSISTANT_ID=your_vapi_assistant_id
NEXT_PUBLIC_VAPI_API_KEY=your_vapi_api_key

ADMIN_EMAIL=your_admin_email

RESEND_API_KEY=your_resend_api_key

NEXT_PUBLIC_APP_URL=your_app_url
````

---

## 🚀 Run Locally

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build
npm start
```

---

## 🧪 Testing

```bash
npm test
```

Includes:

* Unit tests for appointment booking logic
* API integration tests for Clerk + Vapi
* Snapshot tests for UI components

---

## 📸 Screenshots

(Add GIFs or screenshots of:

* Landing page
* Booking flow
* Admin dashboard
* AI voice agent interaction)

---

## 🧑‍💻 Author

**Vinay Dodla – Developer & Architect**

* Architected and implemented the **entire stack** (frontend, backend, database, deployment).
* Integrated **AI voice technology** into a real-world appointment flow.
* Designed a **scalable PostgreSQL schema** with Prisma.
* Built **CI/CD-ready workflows** with GitHub Actions.
* Deployed on **Sevalla** for cost-efficient hosting.

🔗 [LinkedIn](https://www.linkedin.com/in/vinay-dodla-695232213/) | [GitHub](https://github.com/vinay23is)

---

## 🤝 Contributions

Open to contributions and improvements:

1. Fork the repo
2. Create a branch (`git checkout -b feature-xyz`)
3. Commit changes (`git commit -m "Add feature xyz"`)
4. Push to branch (`git push origin feature-xyz`)
5. Open a Pull Request

---

## 📜 License

Licensed under the **MIT License**.

```

---

✅ Just copy-paste this into your `README.md`.  

Would you like me to also write a **“Why I built this project / Case Study”** section so it looks like you’re documenting your design decisions for recruiters? That would make it stand out even more.
```
dev
```
