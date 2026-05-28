# 📜 PROJECT CONSTITUTION

## Example: Online Bookstore (Web Application)

> This is a **filled example** of PROJECT_CONSTITUTION.template.md.
> Copy the template and fill it in for your own project.

AES Constitution Version: 1.2
Status: Active
Compliance Level: L2

---

## ⚖️ CONSTITUTION AUTHORITY

This document defines the **architectural and product authority** of the project.

All AI agents and contributors operating in this repository MUST:

- follow decisions defined in this constitution
- avoid architectural deviation
- request clarification when conflicts appear
- prioritize this document over assumptions

If implementation contradicts this constitution —
**the constitution prevails.**

---

## 🤖 AI EXECUTION CONTEXT

AI agents MUST:

1. Read this constitution before generating code
2. Produce a specification and implementation plan
3. Execute work incrementally
4. Validate changes against defined constraints

🚫 Implementation MUST NOT begin without alignment.

---

# 1. 🎯 PRODUCT SCOPE

## Project Description

Name: BookHaven
One-sentence description: Online bookstore where users browse, search, and purchase books.
Target user: Book readers who prefer buying online.

---

## MVP Scope (≤5 items)

1. Book catalog with search and filters (genre, author, price)
2. Book detail page with description, reviews, price
3. Shopping cart with add/remove/quantity
4. Checkout with order summary
5. User registration and login

---

## Non-Goals

❌ Payment processing (use mock for MVP)
❌ Admin panel for managing inventory
❌ Recommendation engine
❌ Mobile native app

---

## Success Metrics

| Metric | Target | Measurement |
| --- | --- | --- |
| Core flow works (browse → cart → checkout) | Yes | E2E test |
| Page load time | < 2 sec | Lighthouse |
| Test coverage | > 70% | CI |

---

# 2. 🛠️ TECHNOLOGY STACK

## Frontend

- Framework: React 18
- Language: TypeScript 5
- Styling: Tailwind CSS
- State Management: Zustand
- Routing: React Router v6
- HTTP Client: Axios
- UI Library: shadcn/ui
- Validation: Zod

## Backend

- Framework: Express.js
- Language: TypeScript 5
- Database: PostgreSQL 16
- ORM: Prisma
- Authentication: JWT + bcrypt

## Infrastructure

- Package Manager: pnpm
- Runtime: Node.js 20 LTS
- Deployment: Docker + docker-compose

---

# 3. 📐 ARCHITECTURE

## Architectural Approach

- Pattern: Feature-Sliced Design (frontend), Layered (backend)
- Layer separation: UI / Logic / Data / Utils
- API isolation: all API calls in `src/api/`
- Error handling: centralized error boundary (frontend), error middleware (backend)

---

## Project Structure

```
frontend/
├── src/
│   ├── app/           — app setup, providers, router
│   ├── features/      — feature modules (catalog, cart, auth)
│   ├── shared/        — reusable components, hooks, utils
│   ├── api/           — API client and endpoints
│   └── types/         — shared TypeScript types

backend/
├── src/
│   ├── routes/        — Express route handlers
│   ├── services/      — business logic
│   ├── repositories/  — database access (Prisma)
│   ├── middleware/     — auth, error handling, validation
│   └── types/         — shared types
```

---

# 4. 👤 USER FLOWS

FLOW 1: Browse & Search
User → opens catalog → filters by genre → sees book list → clicks book → sees detail page

FLOW 2: Purchase
User → adds book to cart → opens cart → adjusts quantity → proceeds to checkout → confirms order

FLOW 3: Authentication
User → clicks "Sign up" → fills form → receives confirmation → logs in

---

# 5. 📋 FUNCTIONAL REQUIREMENTS

## User Stories

P0 — Must Have:

As a user I want to search books by title or author so I can find what I need.
As a user I want to add books to cart so I can buy multiple books at once.
As a user I want to register and log in so my cart persists.

P1 — Should Have:

As a user I want to filter by genre and price range.
As a user I want to see book reviews and ratings.

P2 — Nice to Have:

As a user I want to save books to a wishlist.

---

# 6. ⚡ NON-FUNCTIONAL REQUIREMENTS

## Performance

- API latency P95: < 200ms
- Page load: < 2s (Lighthouse)
- Bundle size: < 300 KB gzipped

## Reliability

- Uptime target: 99.5%
- Healthcheck: /api/health → 200 OK

---

# 7. 🔒 SECURITY

## Forbidden in source code

- Secrets, tokens, API keys, passwords
- Personally identifiable information (PII)
- Internal IPs, hostnames, environment URLs
- Direct requests to production API from dev code

## Agent boundaries

- Push to main/master/release branches: FORBIDDEN
- Modify CI/CD pipelines: FORBIDDEN
- Access production data: FORBIDDEN
- Create/delete infrastructure: FORBIDDEN

---

# 8. 🗄️ DOMAIN MODEL

```
User 1:M Order
Order 1:M OrderItem
OrderItem M:1 Book
Book M:M Genre
Book 1:M Review
Review M:1 User
```

---

# 9. 🚀 DEPLOYMENT

- Platform: Docker (local), VPS (production)
- Environment variables: DATABASE_URL, JWT_SECRET, PORT
- CI/CD: GitHub Actions (lint → test → build → deploy)
- Rollback strategy: revert to previous Docker image tag

---

# 10. ✅ ACCEPTANCE CRITERIA

A feature is complete when:

- [ ] Happy path works
- [ ] Errors handled
- [ ] Zero type errors
- [ ] Loading / Empty / Error states implemented
- [ ] Destructive actions require confirmation
- [ ] No AES violations
- [ ] Code reviewed

---

*AES v1.3 — AI Engineering Standard*
