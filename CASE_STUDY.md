# Case Study — CITSA Laboratory Management System

**Client:** CITSA (Centro de Investigaciones Toxicológicas), Argentina  
**Type:** Internal tooling — Budget & workflow management  
**Status:** ✅ In production, actively used  
**Timeline:** 5 days from zero to deployment  

---

## The Problem

CITSA is a toxicological research center that provides laboratory analysis services to municipalities, government agencies, universities, and private companies across Argentina.

Their quotation process was fully manual:
- Staff reviewed technical documents and public tenders by hand
- Manually matched each required analysis against a catalog of 300+ services
- Built quotes in spreadsheets, one line at a time
- The entire process took **1–2 hours per quote**

With a high volume of incoming requests, this was eating a significant portion of the team's productive time every week.

---

## The Solution

A full-stack web application that automates the entire pipeline — from document intake to final quote.

The core feature: an **AI-powered document analyzer** that reads any PDF (tender, technical spec, regulation) and automatically:
1. Identifies which toxicological analyses are required
2. Matches them against the service catalog (even with different naming conventions)
3. Detects quantities and client information
4. Generates a complete budget draft in seconds

Staff just reviews and approves — no manual lookup required.

---

## Key Features Built

- **AI Document Analyzer** — Claude API reads PDFs and maps requirements to catalog services
- **Budget Management** — Full lifecycle: draft → sent → approved/rejected, with discounts and PDF export
- **Client Database** — 390+ clients imported, searchable, with full budget history
- **Service Catalog** — 300+ toxicological analyses with pricing, matrices, and methods
- **Predictive Dashboard** — Revenue trends, conversion rates, monthly KPIs
- **Role-based Auth** — Admin and operator roles, JWT-based sessions
- **Email Notifications** — Automated alerts for new budgets and password resets
- **Automated Backups** — Daily database snapshots sent via email

---

## Results

| Metric | Before | After |
|--------|--------|-------|
| Time per quote | ~2 hours | < 5 minutes |
| Manual errors | Frequent | Near zero |
| Staff using system | 0 | 10 |
| Time to build & deploy | — | 5 days |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18 + TypeScript + Vite + shadcn/ui |
| Backend | Node.js + TypeScript + Express |
| Database | PostgreSQL (Drizzle ORM) |
| AI | Anthropic Claude API |
| Deploy | Replit |
| Auth | JWT + bcrypt |

---

## Technical Highlights

**AI Integration** — The document analyzer uses Claude with a carefully engineered prompt that forces structured JSON output, validates service IDs against the live database, and handles edge cases like image-only PDFs or ambiguous terminology.

**Monorepo Architecture** — Frontend, API server, and shared packages (DB schema, Zod validators, API client) organized as a pnpm workspace for clean separation of concerns.

**Production-ready from day one** — Activity logging, error handling, automated backups, and session management built in from the start — not bolted on after.

---

## Live Demo

🔗 [citsa-lab-system demo](https://matugot.github.io/citsa-lab-system) — Interactive frontend demo with mock data.

---

*Built by **Mateo Gotelli** — AI Automation & Full-Stack Developer*  
*[GitHub](https://github.com/Matugot) · [Upwork](https://www.upwork.com)*
