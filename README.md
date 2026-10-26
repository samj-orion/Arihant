# 🌾 Arihant — Modern Indian Purity

> **Premium FMCG Platform** — A full-stack React application for Arihant, India's trusted name in high-purity food staples since 1984. Features a customer-facing e-commerce site, distributor wholesale portal, and comprehensive admin dashboard — all powered by Supabase with native Android support via Capacitor.

[![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-8-646CFF?style=flat-square&logo=vite)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-38B2AC?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![Supabase](https://img.shields.io/badge/Supabase-2-3ECF8E?style=flat-square&logo=supabase)](https://supabase.com/)
[![Capacitor](https://img.shields.io/badge/Capacitor-8-119EFF?style=flat-square&logo=capacitor)](https://capacitorjs.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

---

## 📖 Overview

**Arihant** is a modern Indian FMCG brand delivering premium quality food products — flours (atta), grains, pulses, spices, roasted daliya, and rice varieties — sourced directly from heritage farms across India. This platform serves three distinct user roles:

| Portal | Audience | Key Features |
|--------|----------|--------------|
| 🛍️ **Customer Site** | End consumers | Product browsing, cart, checkout, orders, profile |
| 🏪 **Distributor Portal** | Wholesale buyers | Bulk ordering, inventory tracking, earnings analytics, delivery tracking |
| ⚙️ **Admin Dashboard** | Internal team | Full CMS: products, orders, users, categories, coupons, analytics, inventory |

---

## ✨ Features

### 🌐 Customer-Facing Website
- **Hero & Product Showcase** — Animated hero with featured products (Chakki Atta, Daliya, Besan)
- **Product Catalog** — Category filtering, search, pagination, product detail modal
- **Heritage & Promise Sections** — Brand storytelling with timeline (1984 → present)
- **Testimonials** — Social proof carousel
- **Contact & Bulk Inquiry** — EmailJS-powered forms
- **Auth Flow** — Supabase Auth (email/password, OAuth ready, password recovery)
- **Customer Dashboard** — Order history, profile, addresses, wishlist

### 🏪 Distributor Portal
- **Secure Login** — Role-based access with session management
- **Dashboard Home** — KPIs: pending orders, revenue, low-stock alerts
- **Bulk Order Portal** — Wholesale pricing (80% stock visibility buffer), cart, checkout
- **My Orders** — Status tracking, history, reorder
- **Inventory Availability** — Real-time stock levels with scarcity signaling
- **Delivery Tracking** — Live order fulfillment status
- **Earnings Analytics** — Revenue charts (Recharts), commission tracking
- **Documents & Invoices** — Auto-generated PDFs (pptxgenjs)
- **Support Center** — Ticket system
- **Profile Settings** — Business details, bank info, notifications

### ⚙️ Admin Dashboard (Comprehensive CMS)
- **Dashboard Home** — Revenue, orders, users, conversion metrics
- **Products Manager** — CRUD, images, categories, tags, stock, pricing
- **Orders Manager** — Full lifecycle: pending → confirmed → shipped → delivered
- **Customers Manager** — User profiles, order history, segmentation
- **Distributor Manager** — Approvals, commissions, payouts
- **Categories Manager** — Hierarchical category management
- **Coupons Manager** — Discount codes, usage limits, analytics
- **Inventory Manager** — Stock alerts, reorder points, batch tracking
- **Profit Analytics** — Margin analysis, COGS, profitability by SKU
- **Demand Intelligence** — AI-assisted forecasting (demandEngine.js)
- **Reviews Manager** — Moderation, responses
- **Newsletter Manager** — Campaigns, subscribers, templates
- **Workers Manager** — Warehouse staff, shifts, tasks
- **Settings Panel** — Site config, SEO, payments, shipping, taxes
- **Notifications Panel** — In-app + push (Capacitor)
- **Admin Users Panel** — Role-based access control (RBAC)

### 📱 Mobile App (Capacitor)
- Native Android build (`android/` directory)
- Geolocation for delivery tracking
- Push notifications
- Local notifications
- Hardware back-button handling
- Splash screen & app icons

### 🔒 Security & Performance
- **Helmet.js** — Security headers (CSP, HSTS, X-Frame-Options)
- **Rate Limiting** — Express-rate-limit on API routes
- **DOMPurify** — XSS prevention on user content
- **Session Inactivity Timeout** — 10-min admin, 1-hr distributor auto-logout
- **Row Level Security (RLS)** — Supabase policies per role
- **Crypto-JS** — Client-side encryption for sensitive fields
- **Optimized Fetching** — Pre-fetch promises, React.lazy code-splitting
- **Realtime Sync** — Supabase subscriptions for products, categories, settings

---

## 🛠 Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | React 19, Vite 8, Tailwind CSS 3.4 |
| **State** | React Context (CartContext), localStorage sessions |
| **Routing** | Hash-based SPA routing (`?page=`) + History API |
| **Backend/BaaS** | Supabase (PostgreSQL, Auth, Realtime, Storage) |
| **Database** | PostgreSQL with RLS, triggers, functions |
| **Auth** | Supabase Auth (email/password, MFA ready) |
| **Charts** | Recharts 3 |
| **Animations** | Framer Motion 12 |
| **Forms/Email** | EmailJS Browser |
| **PDF Generation** | pptxgenjs |
| **Mobile** | Capacitor 8 (Android) |
| **Icons** | Material Symbols Outlined |
| **Fonts** | Plus Jakarta Sans (display), Inter (body) |
| **Linting** | ESLint 10 + React Hooks + Refresh plugins |
| **Deployment** | Vercel (frontend), Supabase (backend), Play Store (mobile) |

---

## 📁 Project Structure

```
Arihant_V.1.0.0/
├── android/                    # Capacitor Android project
│   ├── app/src/main/
│   ├── gradle/
│   └── variables.gradle
├── public/                     # Static assets
│   ├── assets/images/          # Hero/product images (WebP)
│   ├── avatars/                # Testimonial avatars
│   ├── logo.png, favicon.svg
│   ├── robots.txt, sitemap.xml
│   └── icons.svg               # Sprite sheet
├── src/
│   ├── admin/                  # Admin Dashboard (lazy-loaded)
│   │   ├── AdminDashboard.jsx  # Main layout + sidebar
│   │   ├── AdminLogin.jsx
│   │   └── sections/           # 16 feature modules
│   │       ├── DashboardHome.jsx
│   │       ├── ProductsManager.jsx
│   │       ├── OrdersManager.jsx
│   │       ├── CustomersManager.jsx
│   │       ├── DistributorManager.jsx
│   │       ├── CategoriesManager.jsx
│   │       ├── CouponsManager.jsx
│   │       ├── InventoryManager.jsx
│   │       ├── ProfitAnalytics.jsx
│   │       ├── DemandIntelligence.jsx
│   │       ├── ReviewsManager.jsx
│   │       ├── NewsletterManager.jsx
│   │       ├── WorkersManager.jsx
│   │       ├── SettingsPanel.jsx
│   │       ├── NotificationsPanel.jsx
│   │       ├── AdminUsersPanel.jsx
│   │       └── AnalyticsView.jsx
│   ├── components/             # Customer site + shared UI
│   │   ├── Header.jsx, Footer.jsx
│   │   ├── Hero.jsx, ProductShowcase.jsx, Products.jsx
│   │   ├── ProductDetailsModal.jsx
│   │   ├── Promise.jsx, Heritage.jsx, Testimonials.jsx
│   │   ├── About.jsx, Contact.jsx
│   │   ├── CartDrawer.jsx
│   │   ├── Auth.jsx, Distributor.jsx, DistributorLogin.jsx
│   │   ├── DistributorDashboard.jsx
│   │   ├── CustomerDashboard.jsx
│   │   ├── ResetPassword.jsx, SEO.jsx
│   │   └── distributor-dashboard/   # 11 sub-components
│   ├── context/
│   │   └── CartContext.jsx     # Global cart state
│   ├── utils/
│   │   ├── security.js         # Helmet, rate-limit, DOMPurify config
│   │   ├── locationValidator.js # Delivery pincode validation
│   │   └── demandEngine.js     # ML-lite demand forecasting
│   ├── supabaseClient.js       # Supabase singleton + helpers
│   ├── lib/
│   │   └── supabaseClient.js   # Duplicate (legacy)
│   ├── App.jsx                 # Root: routing, auth, data fetching
│   ├── main.jsx                # Entry point
│   └── index.css               # Tailwind + custom design tokens
├── dist/                       # Production build output
├── .env.example                # Template (not committed)
├── .env                        # Local (gitignored)
├── vite.config.js
├── tailwind.config.js
├── postcss.config.js
├── eslint.config.js
├── capacitor.config.json
├── package.json
├── SECURITY_SETUP.md           # Enterprise hardening guide
└── README.md                   # This file
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** ≥ 18 (LTS recommended)
- **npm** ≥ 9 or **pnpm** ≥ 8
- **Supabase Account** — [Create a project](https://supabase.com/dashboard)
- **Android Studio** (for mobile builds)
- **Vercel CLI** (optional, for preview deployments)

### 1. Clone & Install
```bash
git clone https://github.com/your-username/arihant.git
cd arihant
npm install
```

### 2. Environment Variables
Copy the example and fill in your credentials:
```bash
cp .env.example .env
```

**Required `.env` variables:**
```env
# Supabase (get from Project Settings > API)
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

# Frontend URL (for CORS in Supabase & backend)
FRONTEND_URL=http://localhost:5173

# EmailJS (for contact forms)
VITE_EMAILJS_SERVICE_ID=your_service_id
VITE_EMAILJS_TEMPLATE_ID=your_template_id
VITE_EMAILJS_PUBLIC_KEY=your_public_key

# Optional: Analytics
VITE_VERCEL_ANALYTICS_ID=your_id
```

### 3. Supabase Setup
Run the SQL migrations in your Supabase SQL Editor (order matters):

```sql
-- 1. Core tables
-- products, product_categories, site_settings, orders, order_items
-- customers, distributors, admin_users

-- 2. Enable RLS on ALL tables
ALTER TABLE products ENABLE ROW LEVEL SECURITY;
-- ... repeat for each table

-- 3. Create policies (see SECURITY_SETUP.md for examples)
-- 4. Enable Realtime: supabase.realtime.subscribe()
```

See `SECURITY_SETUP.md` for complete RLS policies, MFA, and Cloudflare WAF configuration.

### 4. Development Server
```bash
npm run dev
# Opens http://localhost:5173
```

### 5. Build for Production
```bash
npm run build
# Output in dist/
```

### 6. Mobile Build (Android)
```bash
# Sync web assets to native project
npx cap sync android

# Open in Android Studio
npx cap open android

# Or build APK/AAB directly
cd android
./gradlew assembleRelease
```

---

## 🗄 Database Schema (Key Tables)

| Table | Purpose | RLS Policy |
|-------|---------|------------|
| `products` | Catalog items (name, price, stock, images, category) | Public read; admin write |
| `product_categories` | Hierarchical categories | Public read; admin write |
| `site_settings` | Key-value config (hero text, contacts, SEO) | Public read; admin write |
| `orders` | Customer + distributor orders | User owns; admin all |
| `order_items` | Line items per order | User owns; admin all |
| `customers` | Profiles, addresses, preferences | User owns; admin all |
| `distributors` | Business info, commission, status | Distributor owns; admin all |
| `admin_users` | Internal staff with roles | Admin only |
| `coupons` | Discount codes, rules, usage | Public validate; admin CRUD |
| `reviews` | Product ratings/comments | Public read; user write own; admin moderate |
| `newsletter_subscribers` | Email list | Admin only |
| `inventory_batches` | Lot tracking, expiry, COGS | Admin + warehouse |

---

## 🔐 Security Checklist (Production)

- [ ] Enable **RLS on every table** with least-privilege policies
- [ ] Enable **MFA** in Supabase Auth
- [ ] Configure **Cloudflare WAF** + **HSTS/TLS 1.3**
- [ ] Set `NODE_ENV=production` on backend
- [ ] Use **PM2** or systemd for process management
- [ ] Rotate `VITE_SUPABASE_ANON_KEY` periodically
- [ ] Enable **Point-in-Time Recovery (PITR)** in Supabase
- [ ] Run `npm audit` and fix vulnerabilities
- [ ] Set `VITE_SUPABASE_URL` to custom domain (optional)

---

## 📦 Deployment

### Frontend (Vercel — Recommended)
```bash
npm i -g vercel
vercel --prod
# Add env vars in Vercel dashboard
```

### Backend (Supabase — Serverless)
No separate backend deployment needed. Supabase handles:
- PostgreSQL + Realtime
- Auth (email, OAuth, MFA)
- Storage (product images)
- Edge Functions (if needed)

### Mobile (Google Play Console)
```bash
cd android
./gradlew bundleRelease
# Upload app/build/outputs/bundle/release/app-release.aab to Play Console
```

---

## 🧪 Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start Vite dev server |
| `npm run build` | Production build to `dist/` |
| `npm run build:mobile` | Build with mobile mode (Capacitor) |
| `npm run preview` | Preview production build locally |
| `npm run lint` | Run ESLint |
| `npx cap sync` | Sync web assets to native projects |
| `npx cap add android` | Add Android platform (first time) |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

**Code Style:** ESLint + Prettier (configured). Run `npm run lint` before committing.

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 🙏 Acknowledgments

- **Supabase** — Backend-as-a-Service that makes this possible
- **Capacitor** — Seamless web-to-native bridge
- **Tailwind CSS** — Utility-first styling at its finest
- **Framer Motion** — Delightful animations
- **Recharts** — Composable charting
- **Indian Farmers** — The true source of our purity

---

## 📞 Support

- **Email:** support@arihant-fmcg.com
- **Issues:** [GitHub Issues](https://github.com/your-username/arihant/issues)
- **Documentation:** `SECURITY_SETUP.md` for hardening guide

---

<div align="center">

**Made with 🌾 in India** — *Cultivating Purity Since 1984*

</div>