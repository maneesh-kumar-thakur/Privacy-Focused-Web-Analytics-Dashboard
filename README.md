# PrivacyMetrics

> Privacy-Focused Web Analytics Dashboard

A self-hosted analytics solution designed with privacy at its core. Complete data ownership, no cookies, and transparent data collection practices.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status: Beta](https://img.shields.io/badge/Status-Beta%20v1.0.0-orange)](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/releases/tag/v1.0.0-beta.1)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9-blue)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-7.1-646CFF?logo=vite)](https://vitejs.dev)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=node.js)](https://nodejs.org)
[![Prisma](https://img.shields.io/badge/Prisma-5.16-2D3748?logo=prisma)](https://www.prisma.io)
[![SQLite](https://img.shields.io/badge/SQLite-3-003B57?logo=sqlite)](https://www.sqlite.org)

---

## �️ Dashboard Preview

![PrivacyMetrics Dashboard](docs/images/dashboard-preview.png)

> **Screenshot coming soon.** To see it live: run `pnpm dev` and open [http://localhost:8080](http://localhost:8080).

---

## �🚀 Quick Start

**Get started in minutes:** **[📖 DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md)**

Complete setup guide with:
- Installation & dependencies
- Local development setup
- Testing & validation
- Integration examples
- Deployment options (Docker, Railway, self-hosted)

---

## 💬 Did This Work for You?

If you cloned this repo and tried it out — we'd love to hear from you!

- ✅ **It worked great** → [Tell us what you built](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions/categories/show-and-tell)
- ❓ **Ran into a problem** → [Ask for help](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions/categories/q-a)
- 💡 **Have a feature idea** → [Share it](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions/categories/ideas)
- 🐛 **Found a bug** → [Open an issue](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/issues/new)

> Your feedback directly shapes what gets built next. Even a short "it worked!" helps.

---

## ✨ Current Features (v1.0.0-beta.1)

### ✅ Implemented & Tested
- **Multi-website dashboard** - Create, manage, and delete website tracking codes
- **Website isolation** - Each website's data is completely separate
- **Real-time event tracking** - Events tracked and stored immediately
- **Visitor tracking** - Unique visitor identification via IP hashing
- **Session management** - Session grouping and duration tracking
- **Authentication** - User registration and login with JWT tokens
- **Dashboard metrics** - View key metrics per website
- **Self-hosted option** - Full data ownership with SQLite database
- **Privacy-first approach** - Transparent data collection practices
- **CORS configured** - Proper cross-origin request handling

### 📋 Core Data Collected
- Page views
- Unique visitors (via hashed IP fingerprints)
- Session duration
- Referrer sources
- Request timestamps

### ❌ What is NOT Collected
- Cookies (never set)
- Browsing fingerprints beyond IP hash
- Personal identifiable information (names, emails from tracking)
- Cross-site user tracking
- Device details (browser, OS tracking not implemented yet)

---

## ⚖️ How it Compares

PrivacyMetrics vs the most popular privacy-focused analytics tools:

| Feature | PrivacyMetrics | Plausible CE | Umami | Fathom |
|---|:---:|:---:|:---:|:---:|
| Open Source | ✅ | ✅ | ✅ | ❌ |
| Self-Hosted | ✅ | ✅ | ✅ | ❌ |
| Completely Free | ✅ | ✅ | ✅ | 💰 |
| No Cookies | ✅ | ✅ | ✅ | ✅ |
| No PII Collected | ✅ | ✅ | ✅ | ✅ |
| GDPR Compliant | ✅ | ✅ | ✅ | ✅ |
| Multi-site Support | ✅ | ✅ | ✅ | ✅ |
| Tracking Script Size | **2KB** | ~1KB | ~2KB | ~1KB |
| Database | SQLite | PostgreSQL + ClickHouse | PostgreSQL / MySQL | Proprietary |
| Setup Time | **~5 min** | ~30 min | ~15 min | N/A |
| Tech Stack | Node.js + React | Elixir + Phoenix | Next.js | Ruby |
| Custom Events | ❌ (roadmap) | ✅ | ✅ | ✅ |
| Data Export | ❌ (roadmap) | ✅ | ✅ | ✅ |
| Email Reports | ❌ (roadmap) | ✅ | ❌ | ✅ |

> PrivacyMetrics is the **simplest to self-host** — SQLite means zero database server setup. Clone → install → run.

---

## 🏗️ Tech Stack

**Frontend Stack:**
- React 18.3 + TypeScript 5.9
- Vite 7.1 (fast build & dev server)
- Tailwind CSS 3.4 (styling)
- Radix UI (component library)
- React Router 6.30 (navigation)
- Recharts 2.12 (chart visualizations)
- React Hook Form (form handling)

**Backend Stack:**
- Express.js 5.1 (Node.js framework)
- TypeScript 5.9 (type safety)
- Prisma 5.16 (ORM)
- SQLite 3 (database)
- JWT (authentication)
- Bcryptjs (password hashing)

**Tracking Script:**
- Vanilla JavaScript (2KB, zero dependencies)
- Sendbeacon API (reliable event delivery)
- No external dependencies

---

## 📁 Project Structure

```
├── client/                 # React frontend (React components, pages, hooks)
│   ├── pages/             # Route pages (Dashboard, Login, Register, etc.)
│   ├── components/        # Reusable components (UI, dashboard, hero)
│   ├── hooks/             # Custom React hooks (useDashboardData, useTheme, etc.)
│   └── lib/               # Utilities and helpers
├── server/                # Express backend
│   ├── routes/            # API endpoints (auth, tracking, dashboard, websites)
│   ├── services/          # Business logic (tracking, aggregation, auth)
│   ├── middleware/        # Authentication middleware
│   └── schemas/           # Zod validation schemas
├── shared/                # Shared TypeScript types and API definitions
├── public/                # Static files and tracking script
│   ├── pm.js             # Production tracking script (2KB)
│   └── *.html            # Test HTML files
├── prisma/                # Database schema and migrations
│   ├── schema.prisma     # Data model definitions
│   └── migrations/       # Database version history
├── infrastructure/        # Deployment configs
│   ├── Dockerfile        # Docker container definition
│   └── *.config files    # Rail way, Netlify configs
├── scripts/               # Utility scripts
│   ├── validate-tracking.ps1  # Validation script
│   └── *.sh              # Shell scripts
├── config/                # Build configuration
│   ├── vite.config.ts    # Frontend build config
│   └── vite.config.server.ts  # Backend build config
├── config-tools/          # Tool configurations
│   ├── .eslintrc.json    # Linting rules
│   ├── tailwind.config.ts # Tailwind CSS config
│   └── tsconfig.json     # TypeScript config
└── docs/                  # Documentation (15+ guides)

---

## 🔧 Development

### Prerequisites
- Node.js 18.0 or higher
- pnpm (or npm/yarn)

### Installation & Setup

```bash
# 1. Install dependencies
pnpm install

# 2. Initialize database
pnpm db:push   # or: npx prisma db push

# 3. Start development servers
pnpm dev
```

**Access the application:**
- **Frontend Dashboard**: http://localhost:8080
- **Backend API**: http://localhost:3000
- **Database**: SQLite at `prisma/dev.db`

### Common Development Commands

```bash
# Development
pnpm dev              # Start both frontend and backend
pnpm dev:frontend     # Frontend only (hot reload)
pnpm dev:api          # Backend only (hot reload)

# Building
pnpm build            # Build client and server
pnpm build:client     # Frontend only
pnpm build:server     # Backend only

# Quality checks
pnpm test             # Run tests
pnpm typecheck        # TypeScript validation
pnpm lint             # Eslint check
pnpm format.fix       # Format code with Prettier
pnpm quality-check    # Run all checks

# Database
pnpm db:push          # Sync database schema
pnpm db:reset         # Reset database
pnpm db:seed          # Seed sample data (if configured)

# Production
pnpm start:prod       # Run production build
```

---

## 📖 Documentation

All technical documentation is located in the **`docs/`** folder:

| Document | Purpose | Audience |
|----------|---------|----------|
| [DEVELOPER_GUIDE.md](./docs/DEVELOPER_GUIDE.md) | Complete setup and development guide | All developers |
| [API_DOCUMENTATION.md](./docs/API_DOCUMENTATION.md) | REST API reference with examples | Backend developers |
| [BACKEND_SETUP_GUIDE.md](./docs/BACKEND_SETUP_GUIDE.md) | Backend configuration and setup | Backend developers |
| [FRONTEND_BACKEND_INTEGRATION_GUIDE.md](./docs/FRONTEND_BACKEND_INTEGRATION_GUIDE.md) | How frontend connects to API | Frontend developers |
| [TRACKING_SCRIPT_GUIDE.md](./docs/TRACKING_SCRIPT_GUIDE.md) | How to integrate tracking on websites | Website integrations |
| [TRACKING_QUICK_REFERENCE.md](./docs/TRACKING_QUICK_REFERENCE.md) | Quick tracking reference | Quick setup |
| [WEBSITE_MANAGEMENT_GUIDE.md](./docs/WEBSITE_MANAGEMENT_GUIDE.md) | Website CRUD operations | Website operations |
| [PROJECT_STRUCTURE.md](./docs/PROJECT_STRUCTURE.md) | Detailed project architecture | All developers |
| [CODE_QUALITY_SCANNING_GUIDE.md](./docs/CODE_QUALITY_SCANNING_GUIDE.md) | Code quality and CI/CD setup | DevOps/QA |
| [FREE_HOSTING_GUIDE.md](./docs/FREE_HOSTING_GUIDE.md) | Deployment options (free tier) | DevOps/Deployment |

**Quick Links:**
- 🚀 Getting started? → Read [DEVELOPER_GUIDE.md](./docs/DEVELOPER_GUIDE.md)
- 🔌 Want to integrate tracking? → See [TRACKING_SCRIPT_GUIDE.md](./docs/TRACKING_SCRIPT_GUIDE.md)
- 📡 Need API reference? → Check [API_DOCUMENTATION.md](./docs/API_DOCUMENTATION.md)
- 🌐 Ready to deploy? → Follow [FREE_HOSTING_GUIDE.md](./docs/FREE_HOSTING_GUIDE.md)

---

## 🔐 Security & Privacy

### Privacy by Design
✅ **No Cookies** - Never sets any tracking cookies  
✅ **No Fingerprinting** - Only uses hashed IP addresses for visitor identification  
✅ **Session-Based Storage** - Data expires with browser session  
✅ **No Cross-Site Tracking** - Each website is completely isolated  
✅ **Transparent Collection** - Clear documentation on what data is collected  
✅ **Self-Hosted Option** - Full control and data ownership  

### Backend Security
✅ **JWT Authentication** - Secure token-based API authentication  
✅ **Password Hashing** - Bcryptjs for secure password storage  
✅ **CORS Protection** - Proper cross-origin request validation  
✅ **Protected Routes** - Authentication middleware on API endpoints  
✅ **Input Validation** - Zod schemas for request validation  

### Data Protection
- All sensitive data (passwords, tokens) are hashed/encrypted
- SQLite database contains only aggregated visitor data
- No Personal Identifiable Information (PII) collected via tracking
- Data access requires authentication

---

## 📦 Deployment

Ready to deploy? Choose your platform:

### Quick Deployment Options
- **Railway.app** - [See infrastructure/railway.json](infrastructure/railway.json)
- **Docker** - [See infrastructure/Dockerfile](infrastructure/Dockerfile)
- **Netlify** - [See infrastructure/netlify.toml](infrastructure/netlify.toml)
- **Self-Hosted** - Run with Node.js and SQLite

**Detailed deployment guide:** [FREE_HOSTING_GUIDE.md](./docs/FREE_HOSTING_GUIDE.md)

---

## 🐛 Issues & Support

Found a bug? Have a feature request?

- **Report Issues**: [GitHub Issues](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/issues)
- **Ask Questions**: [GitHub Discussions](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions)
- **Check Documentation**: [docs/](./docs/) folder for comprehensive guides
- **Read Developer Guide**: [DEVELOPER_GUIDE.md](./docs/DEVELOPER_GUIDE.md)

---

## 📋 Project Status

### v1.0.0-beta.1 (Current)

**What's Working:**
- ✅ Multi-website tracking dashboard
- ✅ User authentication (registration, login)
- ✅ Real-time event tracking
- ✅ Website management (create, view, delete)
- ✅ Visitor & session tracking
- ✅ API endpoints (fully documented)
- ✅ Database persistence (SQLite)
- ✅ Docker deployment ready
- ✅ Self-hosted support

**Known Limitations:**
- 📝 Browser/OS detection not fully implemented
- 📝 Advanced analytics (funnels, cohorts, retention) not implemented
- 📝 Email reporting not implemented
- 📝 Advanced filtering/segmentation not yet available

**Future Roadmap:**
- [ ] Device and browser analytics
- [ ] Advanced filtering and segmentation
- [ ] Email digest reports
- [ ] Goal tracking
- [ ] Custom events
- [ ] API webhooks
- [ ] Data export (CSV/JSON)

---

## 📝 License

MIT License - See [LICENSE](./LICENSE) file for full details

**All documentation is in one place:** [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md)

**For internal notes and older docs:** See `confidential_docs/` folder

---

## 📣 Give Feedback

Discussions are open — this is the best place to share thoughts, ask questions, or suggest improvements.

| Channel | Use it for |
|---|---|
| [💡 Ideas](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions/categories/ideas) | Feature requests and suggestions |
| [🙋 Q&A](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions/categories/q-a) | Setup help and how-to questions |
| [🎉 Show & Tell](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions/categories/show-and-tell) | Share what you built with it |
| [💬 General](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions) | Anything else |

**[→ Open a Discussion](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions/new)**

---

## 🤝 Contributing

Contributions are welcome! Read the full guide: **[CONTRIBUTING.md](CONTRIBUTING.md)**

Quick steps:
1. Fork → create a branch → make changes → `pnpm quality-check` → open a PR

Please review our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

---

## 🔗 Links & Resources

**Repository:**
- [GitHub Repository](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard)
- [GitHub Releases](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/releases)
- [Changelog](CHANGELOG.md)
- [Contributing](CONTRIBUTING.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)

**Documentation:**
- [Documentation Index](./docs/INDEX.md)
- [Developer Guide](./docs/DEVELOPER_GUIDE.md)
- [API Reference](./docs/API_DOCUMENTATION.md)

**External Resources:**
- [React Documentation](https://react.dev)
- [Prisma Documentation](https://www.prisma.io/docs)
- [Express.js Guide](https://expressjs.com)
- [TypeScript Handbook](https://www.typescriptlang.org/docs)

---

## 💡 Philosophy

PrivacyMetrics is built on the principle that analytics don't require invasive tracking. We believe:

- **Privacy is a right** - Not a feature to be negotiated
- **Transparency matters** - Users deserve to know what data is collected
- **Data ownership** - Your data should be on your own servers
- **Open source** - Code should be auditable and trustworthy
- **Minimal data** - Collect only what's necessary

---

**Made with ❤️ for privacy-conscious developers**

Questions? Start with [DEVELOPER_GUIDE.md](./docs/DEVELOPER_GUIDE.md), [join the discussion](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/discussions), or [open an issue](https://github.com/maneesh-kumar-thakur/Privacy-Focused-Web-Analytics-Dashboard/issues). 🚀
