# Nikesh Khatri

Software engineer based in Kathmandu, Nepal (`UTC+05:45`). Building production platforms where "roughly right" is wrong: payroll that has to match tax law to the rupee, double-entry ledgers that have to balance, and multi-tenant architectures where tenant data must never cross boundaries.

[Website](https://nikeshkhatri.com.np) &nbsp;·&nbsp; [Case Studies](https://nikeshkhatri.com.np#work) &nbsp;·&nbsp; [Technical Notes](https://nikeshkhatri.com.np#notes) &nbsp;·&nbsp; [LinkedIn](https://www.linkedin.com/in/nikesh-khatri-2b04582a9/) &nbsp;·&nbsp; [Email](mailto:khatrinikace@gmail.com)

---

### Focus & Approach

Most of my daily work centers on Python/Django backends and TypeScript/React interfaces for systems that handle money, people, and legal rules. In finance-sensitive and permission-critical domains, correctness takes priority over cleverness. A ledger that does not balance to zero is broken; a multi-tenant query that leaks data across client accounts is a catastrophic failure.

I work full-lifecycle: database schema design, transactional boundary management, REST APIs, frontend interfaces, automated test suites, and containerized Linux deployment.

---

### Selected Systems

> **Note on code visibility:** Most of my production systems were commissioned by enterprise clients or deployed in private employer repositories. To provide transparency into the underlying architecture, detailed case studies and database notes are documented at [nikeshkhatri.com.np](https://nikeshkhatri.com.np).

#### [Mero Pasal](https://mero-pasal.online)
*Multi-tenant retail operations and storefront platform for Nepali businesses.*
- **Tenancy Architecture:** Enforces tenant isolation at the database layer using PostgreSQL Row-Level Security (RLS) and connection-scoped session variables, eliminating the risk of data leaks from forgotten application-level `WHERE` clauses.
- **Scope:** POS invoicing, IRD/CBMS-oriented VAT billing, customer credit (*khata*) ledger tracking, and public storefront generation.
- **Stack:** Django, Django REST Framework, PostgreSQL (RLS), React, TypeScript, Docker, Caddy.

#### Garment Manufacturing ERP
*Order-to-ledger factory floor management system for textile manufacturing.*
- **Ledger Architecture:** Built around an immutable double-entry accounting core. Every material movement, cutting ticket, and piece-rate completion emits balanced journal entries within the same database transaction; audit trails rely on compensating entries rather than historical mutation.
- **Scope:** Merchandising, BOM costing, barcode-based WIP tracking, piece-rate SAM payroll, VAT billing, and dual-calendar (Bikram Sambat / Gregorian) scheduling.
- **Stack:** Django, DRF, PostgreSQL, Celery, Redis, React, Tailwind CSS, ReportLab.

#### Digital File Tracking System (FTS)
*Administrative correspondence and registry tracking for a Nepali public enterprise.*
- **Permission & Audit Model:** Replaced paper registries with an immutable workflow system governing official document movement (*Darta*, *Chalani*, executive *Tippani* minute sheets, and *Tameli* archiving) with strict departmental role boundaries.
- **Stack:** Django 5.2, PostgreSQL 16, DRF, Docker.

#### Bayline Parking Platform
*Multi-tenant parking operations and revenue reconciliation platform.*
- **Scope:** Automated barrier gate check-in/check-out, tariff calculations, thermal ticket generation, Khalti payment gateway integration, and multi-tenant revenue auditing.
- **Stack:** Django, DRF, React, PostgreSQL, Redis.

---

### Technical Notes

I write technical essays analyzing real production tradeoffs and schema designs:

- **[Tenant Isolation with PostgreSQL RLS](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls)**  
  Why relying on application ORM queries for multi-tenancy eventually fails under complex joins, and how to use Postgres session variables and RLS policies to guarantee isolation in the database engine.

- **[A Ledger-First ERP](https://nikeshkhatri.com.np/notes/ledger-first-erp)**  
  Why treating accounting as a reporting layer bolted onto invoices breaks under credit notes and voids, and how placing balanced journal entries at the center makes the trial balance the verifiable source of truth.

---

### Technical Proficiencies

- **Languages:** Python, TypeScript, JavaScript, SQL
- **Backend & APIs:** Django, Django REST Framework, Celery, Node.js, NestJS, REST, WebSockets, OpenAPI
- **Data & Architecture:** PostgreSQL (RLS, indexing, transactional integrity), MySQL, Redis, Prisma, Double-entry ledgers, Multi-tenant architectures
- **Frontend:** React, Next.js, Vite, Tailwind CSS, Redux Toolkit
- **Delivery & Quality:** Docker, GitHub Actions (CI/CD), Nginx, Caddy, Pytest, Playwright, Vitest, Linux
- **Domain Specializations:** IRD / CBMS billing compliance, Nepal income tax slabs, SSF/SST payroll deductions, Bikram Sambat date systems

---

### Engineering Principles

- **Correctness before cleverness:** In financial and permission-sensitive code, simple and obviously correct code covered by automated tests is always superior to clever optimizations.
- **Own the problem, not the ticket:** Requirements, schema design, edge cases, deployment, and late-night diagnostics are the same job. A feature is only finished when users run it without issue.
- **Learn the domain, not just the schema:** Framework documentation will not teach tax law, statutory deductions, or government registry rules. Engineering starts with understanding the real-world operational constraints.
