# 🛋️ Swagne Interior Design Marketplace

> Swagne is a interior design marketplace that connects homeowners, interior designers, and service providers on a single platform.

---

## 🎯 Overcoming Market Fragmentation

> The interior design industry lacks a unified digital space. Homeowners struggle to find trusted designers, designers manage scattered requests manually, and contractors receive unstructured briefs. **Swagne solves this** by giving each party a structured, tailored experience all working toward one goal: bringing the client's vision to life.

---

## 🛠️ Features

| Feature | Client | Designer | Contractor |
| :--- | :---: | :---: | :---: |
| Browse designer profiles | ✅ | | |
| Request a designer | ✅ | | |
| Track project progress | ✅ | | |
| Manage client requests | | ✅ | |
| Build design plans | | ✅ | |
| Publish contractor offers | | ✅ | |
| Receive & review offers | | | ✅ |
| Respond to offers | | | ✅ |

---

## 💻 Tech Stack

| Frontend | Backend | Dev Tools |
| :--- | :--- | :--- |
| 🌐 **React.js** | 🐍 **Python** | 🛠️ **Git & GitHub** |
| ⚡ **Vite** | ⚙️ **Flask** | 📋 **Git project** |
| | 🔒 **Flask-JWT-Extended** | 🎨 **Figma** |
| | 🐘 **PostgreSQL** | 💻 **Visual Studio Code** |
| | ☁️ **Railway** | 🔍 **Console, Network Tab** |
| | 💳 **Stripe** | |

---

## 👥 Team

| Name | Role |
| :--- | :--- |
| **Khulood Alqarni** | Backend Lead, UI/UX Designer, Frontend Developer |
| **Banan Aleid** | Database Lead, Backend Developer, Frontend Team |
| **Layan Aldossari** | QA Lead, Database Team, Frontend Team |
| **Raghad Naseef** | Developer |

---

## 🌐 Live Demo

🔗 **[Visit Swagne](https://adventurous-inspiration-production-938b.up.railway.app )**

---

## 📈 Results

By the end of this project, Swagne was successfully built and deployed as a fully functional platform. Here is a summary of what we achieved:

| Goal | Status |
| :--- | :--- |
| Three role-based user journeys (Client, Designer, Contractor) | ✅ Completed |
| Designer profile browsing and request flow | ✅ Completed |
| Design plan creation with 3-step stepper | ✅ Completed |
| Contractor offer system | ✅ Completed |
| Stripe payment integration | ✅ Completed |
| JWT authentication with protected routes | ✅ Completed |
| Full deployment on Railway (Frontend + Backend + DB) | ✅ Completed |
| Responsive UI across devices | ⚠️ Partial — Landing Page only |

### 📊 Key Metrics

> * 👥 **3** user roles fully implemented
> * 💎 **10+** core features delivered
> * 🚀 **3** deployment services running in production (Frontend, Backend, PostgreSQL)
> * 💳 **1** integrated payment gateway (Stripe)
> * 🤝 **4** team members across frontend, backend, and QA

---

## 🧠 Challenges & Lessons Learned

### 🛠️ Challenges

| Challenge | Solution |
| :--- | :--- |
| **JWT authentication returning 401 errors** | Fixed via `@jwt.user_identity_loader` decorator |
| **Python 3.14 incompatibility on a teammate's machine** | Downgraded to Python 3.11.9 across all machines |
| **Hardcoded localhost URLs breaking production** | Migrated all URLs to `VITE_API_URL` environment variable |
| **Role-based routing across three user types** | Rebuilt `ProtectedRoute` with role-specific logic |

### 💡 Lessons Learned

**Technical**

* A successful server response doesn't mean the problem is solved — we learned to always verify the full flow from backend to frontend.
* Storing tokens correctly (`localStorage`) is essential for maintaining user sessions across the app.
* Any value that changes between environments should never be hardcoded. Separating configuration into `.env` files keeps the codebase flexible and production-ready without touching the code itself.
* Authentication is not just a backend concern — it depends on the full integration between backend and frontend.
* The browser's console and Network tab are powerful debugging tools that saved us hours of guesswork.
* Role-based routing must be defined early — knowing the user type from the start shapes the entire user flow.

**Team & Process**

* **Commitment matters:** When every team member takes ownership of their part, the whole product moves forward with less friction.
* **Collaboration:** It isn't just about dividing tasks — it's about supporting each other when things get hard and sharing knowledge openly.
* **Continuous learning:** Every bug we faced taught us something we couldn't have learned from a tutorial.
* **Growth mindset:** A mistake is not failure. Some of our best technical decisions came directly from understanding why something went wrong.

---

## 🙏 Acknowledgements

> This project would not have been possible without the people who walked this journey with us.
>
> **To our mentors at Holberton School and Tuwaiq Academy** — thank you for believing that learning is not a sprint. You taught us that knowledge is built slowly, with intention, and that the struggle is part of the process.
>
> **To everyone who tested Swagne, gave feedback, and took the time to understand what we were building** — your trust in the idea meant more than you know.
>
> **To our peers who stayed up late, debugged alongside us, and never made us feel alone in the hard moments** — this is as much yours as it is ours.
>
> ---
>
> 💡 **"The only way to do great work is to love what you do. If you haven't found it yet, keep looking. Don't settle."**
> — *Steve Jobs*

***
