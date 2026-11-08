# Nikesh Khatri

Software engineer based in Kathmandu, Nepal. Building production platforms where "roughly right" is wrong: payroll that has to match tax law to the rupee, double-entry ledgers that have to balance, and multi-tenant architectures where tenant data must never cross boundaries.

<br/>

[![Status](https://img.shields.io/badge/Status-Open_to_Opportunities-007136?style=flat-square&logo=statuspage&logoColor=f7f5f1)](https://nikeshkhatri.com.np)
&nbsp;
![Role](https://img.shields.io/badge/Role-Software_Engineer-15181e?style=flat-square)
&nbsp;
![Location](https://img.shields.io/badge/Location-Kathmandu%2C_Nepal-15181e?style=flat-square&logo=googlemaps&logoColor=f7f5f1)
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

### At a Glance

| | |
| :--- | :--- |
| **Experience** | Software Engineer at **Goodwish Engineering Pvt. Ltd.**, Lalitpur — since August 2024 (full-time, now contract) |
| **Strongest at** | Multi-tenant data isolation, double-entry ledgers, payroll and tax rules, permission models |
| **Proof** | 1,400+ tests on Mero Pasal (92% coverage) · 476 backend tests on the Garment ERP (96%) · one system running in a factory |
| **Education** | BSc CSIT, Prime College, Tribhuvan University (2020–2025) |
| **Open to** | Remote full-stack and backend roles, and contract work |

---

### Selected Systems

> **Note on code visibility:** Most of my production systems were commissioned by enterprise clients or deployed in private employer repositories. To provide transparency into the underlying architecture, detailed case studies and database notes are documented at [nikeshkhatri.com.np](https://nikeshkhatri.com.np), and a sanitized code sample of the tenant-isolation design is [available here](https://gist.github.com/nikace7/36738988a91cea8a6acc721f1a7d0dc4).

#### [Mero Pasal](https://mero-pasal.online)
[![Live Product](https://img.shields.io/badge/Product-Live_Storefront-007136?style=flat-square&logo=googlechrome&logoColor=f7f5f1)](https://mero-pasal.online)
[![Tenancy](https://img.shields.io/badge/Tenancy-PostgreSQL_RLS-005222?style=flat-square&logo=postgresql&logoColor=f7f5f1)](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls)
[![Stack](https://img.shields.io/badge/Stack-Django_·_React_·_Docker-15181e?style=flat-square)](https://mero-pasal.online)

*Independent project · Multi-tenant retail operations and storefront platform for Nepali businesses.*
- **Tenancy Architecture:** Enforces tenant isolation at the database layer using PostgreSQL Row-Level Security (RLS) and connection-scoped session variables, eliminating the risk of data leaks from forgotten application-level `WHERE` clauses.
- **Offline-first POS:** A PWA sale queue survives power and internet outages and replays through idempotency-keyed sale and payment APIs, with gapless per-branch invoice numbering allocated under row locks.
- **Scope:** POS invoicing, append-only stock ledger with moving weighted-average cost, 13% VAT registers, customer credit (*khata*) tracking, and public storefront generation.
- **Quality:** 1,400+ automated tests, 92% backend coverage, 100% enforced on money-critical modules.
- **Stack:** Django, Django REST Framework, PostgreSQL (RLS), React, TypeScript, Docker, Caddy.

<br/>

#### Garment Manufacturing ERP
![Domain](https://img.shields.io/badge/Domain-Factory_ERP-15181e?style=flat-square)
[![Architecture](https://img.shields.io/badge/Architecture-Double--Entry_Ledger-005222?style=flat-square)](https://nikeshkhatri.com.np/notes/ledger-first-erp)
![Status](https://img.shields.io/badge/Status-In_Production-007136?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Django_·_PostgreSQL_·_React_·_TypeScript-15181e?style=flat-square)

*Independent project · Order-to-ledger factory floor management system, deployed in production for a garment factory.*
- **Ledger Architecture:** Built around an immutable double-entry accounting core. Every stock, payroll and payment event posts balanced journal entries through a single posting service; debit-XOR-credit is enforced by a database constraint, and corrections use reversing entries rather than historical mutation.
- **Scope:** Orders, cutting, barcoded bundles and WIP tracking, piece-rate payroll that cannot pay a period twice, per-order job costing, and dual-calendar (Bikram Sambat / Gregorian) dates.
- **Delivery:** Offline-tolerant PWA with a tablet kiosk mode for the factory floor and a Tauri Windows client; 476 backend tests at 96% coverage and CI-gated deploys with automatic rollback.
- **Stack:** Django, DRF, PostgreSQL, React, TypeScript, TanStack, Tailwind CSS, Docker, GitHub Actions.

<br/>

#### Digital File Tracking System (FTS)
![Domain](https://img.shields.io/badge/Domain-GovTech_Workflow-15181e?style=flat-square)
![Compliance](https://img.shields.io/badge/Workflows-Darta_·_Chalani_·_Tippani-005222?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Django_5.2_·_PostgreSQL_16_·_Docker-15181e?style=flat-square)

*At Goodwish Engineering · Administrative correspondence and registry tracking for a Nepali public enterprise.*
- **Permission & Audit Model:** Replaced paper registries with an immutable workflow system governing official document movement (*Darta*, *Chalani*, executive *Tippani* minute sheets, and *Tameli* archiving) with strict departmental role boundaries.
- **Stack:** Django 5.2, PostgreSQL 16, DRF, Docker.

<br/>

#### SaaS Parking Platform
![Domain](https://img.shields.io/badge/Domain-Parking_Operations-15181e?style=flat-square)
![Integration](https://img.shields.io/badge/Payments-Khalti_Gateway-005222?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Django_·_DRF_·_React_·_Redis-15181e?style=flat-square)

*At Goodwish Engineering · Multi-tenant parking operations and revenue reconciliation platform.*
- **Scope:** Gate check-in/check-out, tariff calculations, thermal ticket generation, Khalti payment gateway integration, and multi-tenant revenue reporting.
- **Stack:** Django, DRF, React, PostgreSQL, Redis.

<br/>

#### Svara: Voice & Device Studio
![Domain](https://img.shields.io/badge/Domain-Voice_Kiosks-15181e?style=flat-square)
![Architecture](https://img.shields.io/badge/Answers-Only_From_Released_Content-005222?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-NestJS_·_Next.js_·_PostgreSQL-15181e?style=flat-square)

*Independent rebuild · Bilingual (English and Nepali) voice assistants for visitor kiosks.*
- **Releases, not live edits:** Staff publish knowledge as an immutable, hashed release. A conversation searches only its pinned release, and the server checks every passage the model cites against that release before any tool call runs.
- **No lost commands:** A kiosk's desired release is derived and committed in the same transaction as the staff change that caused it. The command table is the outbox, and Redis only wakes the worker.
- **Quality:** 190 unit, 173 integration and 46 browser tests, plus a 40-case bilingual conversation evaluation, all green in CI.
- **Stack:** NestJS, Next.js, TypeScript, PostgreSQL 17, Redis, Caddy, Docker Compose.

<br/>

#### Lattice: Cited Document Q&A
![Domain](https://img.shields.io/badge/Domain-Document_RAG-15181e?style=flat-square)
![Architecture](https://img.shields.io/badge/Citations-Server--Checked-005222?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Django_·_pgvector_·_Ollama-15181e?style=flat-square)

*Independent project · A private document workspace whose answers quote the exact passage they rely on.*
- **Checked citations:** The model returns evidence IDs and quotes. The server rejects any ID it did not retrieve, maps each quote back to a location in the source file, and refuses any answer whose quote does not map completely.
- **Access in the query:** Restricted collections never appear in a page, a count or a search result, because access is checked before pagination.
- **Fully local:** E5 embeddings and a Qwen model run on the machine, so documents never leave it. 655 backend tests and an 80-case frozen retrieval evaluation, with the failures recorded alongside the successes.
- **Stack:** Django, PostgreSQL with pgvector, Celery, React, TypeScript, Ollama, Docker Compose.

<br/>

#### Bayline: Parking Operations
![Domain](https://img.shields.io/badge/Domain-Cash_Gate_Parking-15181e?style=flat-square)
![Architecture](https://img.shields.io/badge/Payments-Idempotent-005222?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Django_·_PostgreSQL_·_React-15181e?style=flat-square)

*Independent rebuild · Multi-tenant parking operations for car parks that take cash at the gate.*
- **No double charges:** Payment and exit are separate idempotent requests, so a retry after a dropped connection repeats only the exit. Checkout recalculates the fee on the server from the pinned tariff.
- **Gapless receipts:** Per-location receipt numbers are allocated inside the payment transaction, so a rolled-back payment rolls back its number too.
- **No double bookings:** A PostgreSQL exclusion constraint stops two customers holding the same bay. Money is integer paisa throughout, and 610 backend tests cover it.
- **Stack:** Django, DRF, PostgreSQL, React, Vite, TypeScript, Caddy, Docker Compose.

---

### Code You Can Read

- **[ParkBuddy](https://github.com/nikace7/parkbuddy):** geospatial parking search and reservations with GeoDjango, PostGIS, Khalti and a PyTorch Nepali chatbot.
- **[PCOS ultrasound classifier](https://github.com/nikace7/PCOS):** a TensorFlow/Keras CNN that screens pelvic ultrasound images.
- **[Tenant isolation sample](https://gist.github.com/nikace7/36738988a91cea8a6acc721f1a7d0dc4):** the PostgreSQL RLS design behind Mero Pasal, sanitized.

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
| **Backend & APIs** | ![Python](https://img.shields.io/badge/Python_3.12-15181e?style=flat-square&logo=python&logoColor=f7f5f1) ![Django](https://img.shields.io/badge/Django_5-005222?style=flat-square&logo=django&logoColor=f7f5f1) ![DRF](https://img.shields.io/badge/Django_REST-005222?style=flat-square&logo=django&logoColor=f7f5f1) ![Celery](https://img.shields.io/badge/Celery-15181e?style=flat-square&logo=celery&logoColor=f7f5f1) ![Node.js](https://img.shields.io/badge/Node.js-15181e?style=flat-square&logo=nodedotjs&logoColor=f7f5f1) ![NestJS](https://img.shields.io/badge/NestJS-15181e?style=flat-square&logo=nestjs&logoColor=f7f5f1) |
| **Data & Architecture** | [![PostgreSQL RLS](https://img.shields.io/badge/PostgreSQL_RLS-005222?style=flat-square&logo=postgresql&logoColor=f7f5f1)](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls) ![Redis](https://img.shields.io/badge/Redis-15181e?style=flat-square&logo=redis&logoColor=f7f5f1) [![Double-Entry](https://img.shields.io/badge/Double--Entry_Ledgers-005222?style=flat-square)](https://nikeshkhatri.com.np/notes/ledger-first-erp) ![Prisma](https://img.shields.io/badge/Prisma-15181e?style=flat-square&logo=prisma&logoColor=f7f5f1) ![MySQL](https://img.shields.io/badge/MySQL-15181e?style=flat-square&logo=mysql&logoColor=f7f5f1) |
| **Frontend** | ![TypeScript](https://img.shields.io/badge/TypeScript-15181e?style=flat-square&logo=typescript&logoColor=f7f5f1) ![React](https://img.shields.io/badge/React_19-15181e?style=flat-square&logo=react&logoColor=f7f5f1) ![Next.js](https://img.shields.io/badge/Next.js-15181e?style=flat-square&logo=nextdotjs&logoColor=f7f5f1) ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-15181e?style=flat-square&logo=tailwindcss&logoColor=f7f5f1) ![Vite](https://img.shields.io/badge/Vite-15181e?style=flat-square&logo=vite&logoColor=f7f5f1) |
| **DevOps & Quality** | ![Docker](https://img.shields.io/badge/Docker-15181e?style=flat-square&logo=docker&logoColor=f7f5f1) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-15181e?style=flat-square&logo=githubactions&logoColor=f7f5f1) ![Pytest](https://img.shields.io/badge/Pytest-005222?style=flat-square&logo=pytest&logoColor=f7f5f1) ![Playwright](https://img.shields.io/badge/Playwright-15181e?style=flat-square&logo=playwright&logoColor=f7f5f1) ![Caddy](https://img.shields.io/badge/Caddy-15181e?style=flat-square&logo=caddy&logoColor=f7f5f1) ![Nginx](https://img.shields.io/badge/Nginx-15181e?style=flat-square&logo=nginx&logoColor=f7f5f1) |
| **Domain & Compliance** | ![Nepal Tax Slabs](https://img.shields.io/badge/Nepal_Tax_Slabs-005222?style=flat-square) ![SSF/SST Payroll](https://img.shields.io/badge/SSF%2FSST_Payroll-005222?style=flat-square) ![VAT Registers](https://img.shields.io/badge/VAT_Registers-005222?style=flat-square) ![Bikram Sambat](https://img.shields.io/badge/Bikram_Sambat_Dates-15181e?style=flat-square) |

---

### Engineering Principles

- **Correctness before cleverness:** In financial and permission-sensitive code, simple and obviously correct code covered by automated tests is always superior to clever optimizations.
- **Own the problem, not the ticket:** Requirements, schema design, edge cases, deployment, and late-night diagnostics are the same job. A feature is only finished when users run it without issue.
- **Learn the domain, not just the schema:** Framework documentation will not teach tax law, statutory deductions, or government registry rules. Engineering starts with understanding the real-world operational constraints.
