# Phase 1 MVP — Feature Comparison & Scope

Based on research of leading systems across all four verticals, here's what the market offers and what we should include in Phase 1.

---

## Reference Systems Analyzed

| Industry | Leading Systems | Key Players |
|----------|-----------------|-------------|
| **Legal** | Clio, PracticePanther, MyCase, Amicus | ~15+ competitors |
| **Accounting** | Karbon, Method, QuickBooks CRM, Double | ~10+ competitors |
| **Investments** | Black Diamond, Morningstar Direct, Advent | ~8 major players |
| **Insurance** | Applied Systems, AgencyMatrix, QuickBooks (Ins) | ~12 competitors |

---

## Common Features Across All Verticals (Phase 1 Baseline)

| Feature Category | Must Have (MVP) | Nice to Have |
|-----------------|-----------------|--------------|
| **Client/Contact Management** | Create, edit, delete contacts; basic profiles; tags | Custom fields; pipeline stages; lead scoring |
| **Organization/Company Records** | Business vs. individual distinction | Multiple contacts per client |
| **Activity Logging** | Log calls, emails, meetings; notes | Automated activity capture; email sync |
| **User Management** | Create users; assign roles; basic permissions | SSO; granular permissions |
| **Search & Filtering** | Global search; filter by client/type | Advanced queries; saved searches |
| **Dashboard** | Basic KPI overview; recent activity | Custom widgets; analytics |

---

## Industry-Specific MVP Features

### LEGAL — Based on Clio, PracticePanther

| Feature | MVP Priority | Description |
|---------|--------------|-------------|
| **Client/Matter Management** | MUST | Create clients, link matters, track status |
| **Contact Management** | MUST | Multiple contacts per client; roles (billing, primary) |
| **Time Tracking** | MUST | Log time against matters; billable vs. non-billable |
| **Invoice Generation** | MUST | Create invoices from time entries; basic templates |
| **Task Management** | MUST | Assign tasks to matters; due dates |
| **Calendar Integration** | NICE | Sync with Google/Outlook; deadline reminders |
| **Document Storage** | NICE | Upload/link documents to matters |
| **Trust Accounting** | NICE | Track client funds separately (Phase 2) |

---

### ACCOUNTING — Based on Karbon, Method

| Feature | MVP Priority | Description |
|---------|--------------|-------------|
| **Client/Engagement Profiles** | MUST | Track tax returns, bookkeeping accounts |
| **Pipeline/Workflow** | MUST | Lead → Prospect → Client; track stage |
| **Task/Project Tracking** | MUST | Tax return lifecycle; milestone tracking |
| **Document Links** | MUST | Link to tax documents, financials |
| **Deadline Calendar** | MUST | Filing deadlines by jurisdiction |
| **Staff Assignment** | MUST | Assign preparer, reviewer to engagements |
| **Integration Sync** | NICE | Sync with QuickBooks/Xero (Phase 2) |
| **Billing/Invoicing** | NICE | Time-based or flat fee billing (Phase 2) |

---

### INVESTMENTS — Based on Black Diamond, Advent

| Feature | MVP Priority | Description |
|---------|--------------|-------------|
| **Client Portfolio Profiles** | MUST | Link clients to investment accounts |
| **AUM Tracking** | MUST | Assets Under Management; manual or sync |
| **Investment Policy Statement** | MUST | Store IPS for each client |
| **Performance Reporting** | MUST | Basic performance vs. benchmark |
| **Fee Calculation** | NICE | AUM fee calculation (% of AUM) |
| **Rebalancing Alerts** | NICE | Alerts when portfolio drifts from IPS |
| **Regulatory Reports** | NICE | Basic SEC reporting (Phase 2) |

---

### INSURANCE — Based on Applied Systems

| Feature | MVP Priority | Description |
|---------|--------------|-------------|
| **Client/Policy Management** | MUST | Policies linked to clients; status tracking |
| **Carrier Relationships** | MUST | Track which carriers write which business |
| **Quote Tracking** | MUST | Quotes from multiple carriers per client |
| **Renewal Tracking** | MUST | Upcoming renewals; alerts |
| **Commission Tracking** | NICE | Track commissions by policy; payout schedules |
| **Producer Licensing** | NICE | Track agent licenses; expiration alerts |
| **Policy Documents** | NICE | Store certificates, applications |

---

## Phase 1 MVP — Consolidated Feature List

### CORE (All Verticals)

- ✅ Multi-tenant organization management
- ✅ User authentication + RBAC
- ✅ Client/Contact CRUD
- ✅ Activity logging (notes, calls, meetings)
- ✅ Dashboard with basic KPIs
- ✅ Global search
- ✅ Basic reporting

### LEGAL VERTICAL

- ✅ Client + Matter management
- ✅ Time tracking by matter
- ✅ Task management by matter
- ✅ Basic invoice generation

### ACCOUNTING VERTICAL

- ✅ Client + Engagement tracking
- ✅ Pipeline (Lead → Client)
- ✅ Task management by engagement
- ✅ Deadline calendar

### INVESTMENTS VERTICAL

- ✅ Client + Portfolio profiles
- ✅ AUM tracking
- ✅ Investment Policy Statement storage
- ✅ Basic performance reporting

### INSURANCE VERTICAL

- ✅ Client + Policy management
- ✅ Quote tracking
- ✅ Renewal tracking
- ✅ Carrier relationship tracking

---

## Phase 1 Technical Scope

| Component | MVP Requirement |
|-----------|-----------------|
| **Frontend** | Web app (React/Next.js or Vue) |
| **Backend** | REST API (Node/Python/Go) |
| **Database** | PostgreSQL |
| **Auth** | JWT + email/password |
| **File Storage** | Basic (S3 or local) |
| **Integrations** | None in MVP (Phase 2) |
| **Mobile** | Not in MVP (Phase 2) |

---

## Competitive Differentiation

What makes us different from existing systems:

| Our Advantage | Description |
|---------------|-------------|
| **Unified Data Model** | Single client record across all verticals |
| **Industry-Agnostic Core** | Same CRM works for legal + accounting + investments + insurance |
| **Open Architecture** | API-first; customers can build custom integrations |
| **Modern UX** | Better UI/UX than legacy systems (Clio, Black Diamond are dated) |
| **Pricing** | Flexible per-module pricing vs. per-seat |

---

## What's NOT in MVP (Phase 2+)

- Trust accounting (Legal)
- QuickBooks/Xero sync (Accounting)  
- Morningstar/Bloomberg integration (Investments)
- Carrier API connections (Insurance)
- Client portal
- Mobile apps
- Email/calendar sync
- Document automation
- Advanced analytics
- Webhooks

---

## Summary

Phase 1 MVP should take **6-12 months** to build for a team of 3-5 engineers, targeting:

- 4 verticals supported
- Core CRM features for each
- Basic project/engagement tracking
- Time tracking + invoicing (at least one vertical)
- Clean, modern UX as differentiator

This positions us to compete with Clio (legal), Karbon (accounting), and Black Diamond (investments) while offering a unified platform they can't match.

---

*Research compiled from Clio, PracticePanther, MyCase, Karbon, Method, Black Diamond, Advent, Applied Systems, and other market leaders*