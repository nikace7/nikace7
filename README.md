# Nikesh Khatri

Software engineer in Kathmandu, Nepal. I build Django and React systems where "roughly right" is wrong: ledgers that have to balance, payroll that has to match tax law, and multi-tenant data that must never cross between customers.

**Open to remote backend and full-stack roles, and contract work.**

[nikeshkhatri.com.np](https://nikeshkhatri.com.np) · [LinkedIn](https://www.linkedin.com/in/nikesh-khatri-2b04582a9/) · [khatrinikace@gmail.com](mailto:khatrinikace@gmail.com)

| | |
| :--- | :--- |
| **Now** | Software Engineer at Goodwish Engineering, Lalitpur (since Aug 2024, contract since Jul 2026), plus two products of my own |
| **Strongest at** | Multi-tenant isolation, double-entry ledgers, payroll and tax rules, permission models |
| **Stack** | Python, Django, DRF, PostgreSQL, Celery, Redis · TypeScript, React, Next.js, NestJS · Docker, Caddy, GitHub Actions, Pytest, Playwright |
| **Education** | BSc CSIT, Prime College, Tribhuvan University (2020–2025) |

---

## Code you can read

### [Mero Pasal](https://github.com/nikace7/dokan) · [live](https://mero-pasal.online)
Multi-tenant SaaS for clothing shops in Nepal. Sole engineer, in production.
- Every shop is isolated by **PostgreSQL row-level security**: middleware sets the tenant per request, so a query that forgets its filter returns nothing instead of another shop's sales. Background jobs and support sessions cross tenants only through explicit, audited paths.
- Phone-first point of sale that tolerates outages, customer credit (*khata*) as a real ledger, an append-only stock ledger, VAT registers by the Nepali fiscal year, and a storefront per shop.
- 873 backend tests; CI enforces 80% coverage overall and **100% line and branch coverage** on pricing, sales, inventory writes and the calendar.
- Django, DRF, PostgreSQL, Celery, React, TypeScript, Docker, Caddy.

### [Lattice](https://github.com/nikace7/lattice) · [case study](https://nikeshkhatri.com.np/work/lattice)
Private document Q&A whose answers quote the exact passage they rely on.
- The server rejects any citation it did not retrieve and refuses an answer whose quote does not map back to the source file.
- Access is checked before pagination, so restricted documents never appear in a count or a search result.
- Runs fully local (E5 embeddings, a Qwen model through Ollama). 655 backend tests and an 80-case frozen retrieval evaluation that records its failures.
- Django, PostgreSQL with pgvector, Celery, React, TypeScript.

### [ParkBuddy](https://github.com/nikace7/parkbuddy)
Geospatial parking search and reservations with GeoDjango, PostGIS, Khalti payments and a PyTorch Nepali chatbot.

### [PCOS ultrasound classifier](https://github.com/nikace7/PCOS)
A TensorFlow/Keras CNN that screens pelvic ultrasound images.

---

## Production work (private code)

These belong to clients or my employer, so the code stays private. Case studies are on [nikeshkhatri.com.np](https://nikeshkhatri.com.np).

- **Garment Manufacturing ERP** (my own, sole engineer). Built the full order-to-ledger chain and took it live in a factory in September 2026. Production data showed which modules were never used, so I removed about 32,000 lines and kept cutting, piece-rate pay, stock and deliveries posting to one double-entry ledger. Floor actions save offline and sync idempotently. 261 merged PRs.
- **Digital File Tracking System** (Goodwish). Replaced paper registries for a public enterprise: *Darta*, *Chalani* and *Tippani* workflows with strict departmental permissions and an audit trail.
- **Attendance & Payroll SaaS** (Goodwish). Multi-tenant attendance from ADMS terminals, payroll and Nepali tax rules.
- **SaaS Parking Platform** (Goodwish). Gate check-in and check-out, tariffs, Khalti payments and multi-tenant revenue reports.
- **Svara** and **Bayline** (independent rebuilds). Bilingual voice kiosks that answer only from released content (409 tests), and cash-gate parking with idempotent payments and gapless receipts (610 backend tests).

---

## Notes

- [Tenant isolation with PostgreSQL RLS](https://nikeshkhatri.com.np/notes/tenant-isolation-postgres-rls): why ORM filters fail eventually, and how session variables and RLS policies make isolation the database's job.
- [A ledger-first ERP](https://nikeshkhatri.com.np/notes/ledger-first-erp): why accounting bolted onto invoices breaks under voids and credit notes, and how balanced journal entries make the trial balance the source of truth.
