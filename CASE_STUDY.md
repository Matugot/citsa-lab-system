# Case Study — CITSA Laboratory Management System

**Client:** CITSA, my family's laboratory (Argentina)  
**Type:** Internal tooling — Sample, budget & documentation management  
**Status:** ✅ In production, used day to day  
**Timeline:** 5 days from zero to deployment  

---

## The Context

CITSA is my family's laboratory. It needed its own system to organize the everyday work: tracking samples, building quotes, and no longer writing repetitive documentation by hand.

---

## The Solution

A full-stack web application that covers sample management, quotes, and documentation automation, and that is tailored to the needs of each business.

One of its features is an **AI-powered document analyzer**: it reads a client's analysis request or technical specification (PDF) and:
1. Identifies which analyses are requested
2. Matches them against the service catalog (even with different naming conventions)
3. Detects quantities and client information
4. Drafts a budget

Staff reviews and approves every budget.

---

## Key Features Built

- **Sample Management** — Tracking samples inside the laboratory
- **AI Document Analyzer** — Claude API reads PDFs and maps requirements to catalog services
- **Budget Management** — Full lifecycle: draft → sent → approved/rejected, with discounts and PDF export
- **Client Database** — Searchable, with budget history
- **Service Catalog** — Analyses with pricing, matrices, and methods
- **Dashboard** — Revenue trends, conversion rates, monthly KPIs
- **Role-based Auth** — Admin and operator roles, JWT-based sessions
- **Email Notifications** — Alerts for new budgets and password resets
- **Automated Backups** — Daily database copies

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18 + TypeScript + Vite + shadcn/ui |
| Backend | Node.js + TypeScript + Express |
| Database | PostgreSQL (Drizzle ORM) |
| AI | Anthropic Claude API |
| Demo | GitHub Pages |
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
