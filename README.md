# Nikesh Khatri

Software engineer based in Kathmandu, Nepal. Building production platforms where "roughly right" is wrong: payroll that has to match tax law to the rupee, double-entry ledgers that have to balance, and multi-tenant architectures where tenant data must never cross boundaries.

<br/>

[![Status](https://img.shields.io/badge/Status-Open_to_Opportunities-007136?style=flat-square&logo=statuspage&logoColor=f7f5f1)](https://nikeshkhatri.com.np)
&nbsp;
[![Role](https://img.shields.io/badge/Role-Software_Engineer-15181e?style=flat-square)](https://nikeshkhatri.com.np)
&nbsp;
[![Location](https://img.shields.io/badge/Location-Kathmandu%2C_Nepal-15181e?style=flat-square&logo=googlemaps&logoColor=f7f5f1)](https://nikeshkhatri.com.np)
&nbsp;
[![Website](https://img.shields.io/badge/Website-nikeshkhatri.com.np-005222?style=flat-square&logo=googlechrome&logoColor=f7f5f1)](https://nikeshkhatri.com.np)
&nbsp;
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Nikesh_Khatri-15181e?style=flat-square&logo=linkedin&logoColor=f7f5f1)](https://www.linkedin.com/in/nikesh-khatri-2b04582a9/)
&nbsp;
[![Email](https://img.shields.io/badge/Email-khatrinikace%40gmail.com-15181e?style=flat-square&logo=gmail&logoColor=f7f5f1)](mailto:khatrinikace@gmail.com)

---

### Focus & Approach

Most of my daily work centers on Python/Django backends and TypeScript/React interfaces for systems that handle money, people, and legal rules. In finance-sensitive and permission-critical domains, correctness takes priority over cleverness. A ledger that does not balance to zero is broken; a multi-tenant query that leaks data across client accounts is a catastrophic failure.

I work full-lifecycle: database schema design, transactional boundary management, REST APIs, frontend interfaces, automated test suites, and containerized Linux deployment.

---

### Selected Systems

> **Note on code visibility:** Most of my production systems were commissioned by enterprise clients or deployed in private employer repositories. To provide transparency into the underlying architecture, detailed case studies and database notes are documented at [nikeshkhatri.com.np](https://nikeshkhatri.com.np).

#### [Mero Pasal](https://mero-pasal.online)
[![Live Product](https://img.shields.io/badge/Product-Live_Storefront-007136?style=flat-square&logo=googlechrome&logoColor=f7f5f1)](https://mero-pasal.online)
[![Tenancy](https://img.shields.io/badge/Tenancy-PostgreSQL_RLS-005222?style=flat-square&logo=postgresql&logoColor=f7f5f1)](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls)
[![Stack](https://img.shields.io/badge/Stack-Django_·_React_·_Docker-15181e?style=flat-square)](https://mero-pasal.online)

*Multi-tenant retail operations and storefront platform for Nepali businesses.*
- **Tenancy Architecture:** Enforces tenant isolation at the database layer using PostgreSQL Row-Level Security (RLS) and connection-scoped session variables, eliminating the risk of data leaks from forgotten application-level `WHERE` clauses.
- **Scope:** POS invoicing, IRD/CBMS-oriented VAT billing, customer credit (*khata*) ledger tracking, and public storefront generation.
- **Stack:** Django, Django REST Framework, PostgreSQL (RLS), React, TypeScript, Docker, Caddy.

<br/>

#### Garment Manufacturing ERP
[![Domain](https://img.shields.io/badge/Domain-Factory_ERP-15181e?style=flat-square)](https://nikeshkhatri.com.np)
[![Architecture](https://img.shields.io/badge/Architecture-Double--Entry_Ledger-005222?style=flat-square)](https://nikeshkhatri.com.np/notes/ledger-first-erp)
[![Delivery](https://img.shields.io/badge/Delivery-516_Commits_·_159_PRs-15181e?style=flat-square)](https://nikeshkhatri.com.np)
[![Stack](https://img.shields.io/badge/Stack-Django_·_Celery_·_React_·_Redis-15181e?style=flat-square)](https://nikeshkhatri.com.np)

*Order-to-ledger factory floor management system for textile manufacturing.*
- **Ledger Architecture:** Built around an immutable double-entry accounting core. Every material movement, cutting ticket, and piece-rate completion emits balanced journal entries within the same database transaction; audit trails rely on compensating entries rather than historical mutation.
- **Scope:** Merchandising, BOM costing, barcode-based WIP tracking, piece-rate SAM payroll, VAT billing, and dual-calendar (Bikram Sambat / Gregorian) scheduling.
- **Stack:** Django, DRF, PostgreSQL, Celery, Redis, React, Tailwind CSS, ReportLab.

<br/>

#### Digital File Tracking System (FTS)
[![Domain](https://img.shields.io/badge/Domain-GovTech_Workflow-15181e?style=flat-square)](https://nikeshkhatri.com.np)
[![Compliance](https://img.shields.io/badge/Workflows-Darta_·_Chalani_·_Tippani-005222?style=flat-square)](https://nikeshkhatri.com.np)
[![Stack](https://img.shields.io/badge/Stack-Django_5.2_·_PostgreSQL_16_·_Docker-15181e?style=flat-square)](https://nikeshkhatri.com.np)

*Administrative correspondence and registry tracking for a Nepali public enterprise.*
- **Permission & Audit Model:** Replaced paper registries with an immutable workflow system governing official document movement (*Darta*, *Chalani*, executive *Tippani* minute sheets, and *Tameli* archiving) with strict departmental role boundaries.
- **Stack:** Django 5.2, PostgreSQL 16, DRF, Docker.

<br/>

#### Bayline Parking Platform
[![Domain](https://img.shields.io/badge/Domain-Parking_Operations-15181e?style=flat-square)](https://nikeshkhatri.com.np)
[![Integration](https://img.shields.io/badge/Payments-Khalti_Gateway-005222?style=flat-square)](https://nikeshkhatri.com.np)
[![Stack](https://img.shields.io/badge/Stack-Django_·_DRF_·_React_·_Redis-15181e?style=flat-square)](https://nikeshkhatri.com.np)

*Multi-tenant parking operations and revenue reconciliation platform.*
- **Scope:** Automated barrier gate check-in/check-out, tariff calculations, thermal ticket generation, Khalti payment gateway integration, and multi-tenant revenue auditing.
- **Stack:** Django, DRF, React, PostgreSQL, Redis.

---

### Technical Notes

I write technical essays analyzing real production tradeoffs and schema designs:

- **[Tenant Isolation with PostgreSQL RLS](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls)** &nbsp; [![Read Note](https://img.shields.io/badge/Case_Study-Read_Note-005222?style=flat-square)](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls)  
  Why relying on application ORM queries for multi-tenancy eventually fails under complex joins, and how to use Postgres session variables and RLS policies to guarantee isolation in the database engine.

- **[A Ledger-First ERP](https://nikeshkhatri.com.np/notes/ledger-first-erp)** &nbsp; [![Read Note](https://img.shields.io/badge/Case_Study-Read_Note-005222?style=flat-square)](https://nikeshkhatri.com.np/notes/ledger-first-erp)  
  Why treating accounting as a reporting layer bolted onto invoices breaks under credit notes and voids, and how placing balanced journal entries at the center makes the trial balance the verifiable source of truth.

---

### Technical Proficiencies

| Domain | Stack & Core Tools |
| :--- | :--- |
| **Backend & APIs** | [![Python](https://img.shields.io/badge/Python_3.12-15181e?style=flat-square&logo=python&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Django](https://img.shields.io/badge/Django_5-005222?style=flat-square&logo=django&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![DRF](https://img.shields.io/badge/Django_REST-005222?style=flat-square&logo=django&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Celery](https://img.shields.io/badge/Celery-15181e?style=flat-square&logo=celery&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Node.js](https://img.shields.io/badge/Node.js-15181e?style=flat-square&logo=nodedotjs&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![NestJS](https://img.shields.io/badge/NestJS-15181e?style=flat-square&logo=nestjs&logoColor=f7f5f1)](https://nikeshkhatri.com.np) |
| **Data & Architecture** | [![PostgreSQL RLS](https://img.shields.io/badge/PostgreSQL_RLS-005222?style=flat-square&logo=postgresql&logoColor=f7f5f1)](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls) [![Redis](https://img.shields.io/badge/Redis-15181e?style=flat-square&logo=redis&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Double-Entry](https://img.shields.io/badge/Double--Entry_Ledgers-005222?style=flat-square)](https://nikeshkhatri.com.np/notes/ledger-first-erp) [![Prisma](https://img.shields.io/badge/Prisma-15181e?style=flat-square&logo=prisma&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![MySQL](https://img.shields.io/badge/MySQL-15181e?style=flat-square&logo=mysql&logoColor=f7f5f1)](https://nikeshkhatri.com.np) |
| **Frontend** | [![TypeScript](https://img.shields.io/badge/TypeScript-15181e?style=flat-square&logo=typescript&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![React](https://img.shields.io/badge/React_19-15181e?style=flat-square&logo=react&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Next.js](https://img.shields.io/badge/Next.js-15181e?style=flat-square&logo=nextdotjs&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-15181e?style=flat-square&logo=tailwindcss&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Vite](https://img.shields.io/badge/Vite-15181e?style=flat-square&logo=vite&logoColor=f7f5f1)](https://nikeshkhatri.com.np) |
| **DevOps & Quality** | [![Docker](https://img.shields.io/badge/Docker-15181e?style=flat-square&logo=docker&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-15181e?style=flat-square&logo=githubactions&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Pytest](https://img.shields.io/badge/Pytest-005222?style=flat-square&logo=pytest&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Playwright](https://img.shields.io/badge/Playwright-15181e?style=flat-square&logo=playwright&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Caddy](https://img.shields.io/badge/Caddy-15181e?style=flat-square&logo=caddy&logoColor=f7f5f1)](https://nikeshkhatri.com.np) [![Nginx](https://img.shields.io/badge/Nginx-15181e?style=flat-square&logo=nginx&logoColor=f7f5f1)](https://nikeshkhatri.com.np) |
| **Domain & Compliance** | [![Nepal Tax Slabs](https://img.shields.io/badge/Nepal_Tax_Slabs-005222?style=flat-square)](https://nikeshkhatri.com.np) [![SSF/SST Payroll](https://img.shields.io/badge/SSF%2FSST_Payroll-005222?style=flat-square)](https://nikeshkhatri.com.np) [![IRD/CBMS Invoicing](https://img.shields.io/badge/IRD%2FCBMS_Billing-005222?style=flat-square)](https://nikeshkhatri.com.np) [![Bikram Sambat](https://img.shields.io/badge/Bikram_Sambat_Dates-15181e?style=flat-square)](https://nikeshkhatri.com.np) |

---

### Engineering Principles

- **Correctness before cleverness:** In financial and permission-sensitive code, simple and obviously correct code covered by automated tests is always superior to clever optimizations.
- **Own the problem, not the ticket:** Requirements, schema design, edge cases, deployment, and late-night diagnostics are the same job. A feature is only finished when users run it without issue.
- **Learn the domain, not just the schema:** Framework documentation will not teach tax law, statutory deductions, or government registry rules. Engineering starts with understanding the real-world operational constraints.
