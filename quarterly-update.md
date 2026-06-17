# Apps & Data — Quarterly Team Update

**Prepared for:** Team Meeting · June 17, 2026
**Period covered:** March – June 2026
**Source:** Asana (completed + in-progress work, by assignee)

---

## At a glance

| Team member | Role | Completed (projects) | In progress | Timely support — done | Timely support — open |
|---|---|---|---|---|---|
| Scott Allen | App Developer Team Lead | 5 major workstreams | ~10 active | 10 | 0 |
| Matthew Narron | Data Analyst | 4 dashboards | ~12 active | — | — |
| Jesse Kuzy | Application Developer | 5 dev workstreams | 3 active | 49* | a few small |

\*A couple of Jesse's 49 are duplicate records of the same issue. Timely support is the bulk of Jesse's load.

---

## Scott Allen — Application Developer Team Lead

### Completed

**County Contributions app (Node 24 / React / Express)**
Shipped a large WCAG 2.1 AA accessibility remediation effort (landmarks, focus management, ARIA widgets, contrast, 320px reflow, keyboard-operable controls) and a security-hardening pass (closed a cross-county read leak, replaced CORS wildcards with an allowlist, added OIDC nonce validation, enforced append-only audit logs, patched dependencies, locked down dev-impersonation). Added admin year-end export reports and district-admin coverage filters, fixed prod QA findings, isolated app tables into a dedicated Postgres schema, and prepped the repo for team handoff.

**CAES Shared UI Library (@caes-webteam/ui)**
Built and published a shared React component library — app chrome (shell/header/footer/nav), UGA/CAES brand marks, design tokens, accessibility primitives, and a Storybook catalog — with automated publishing to GitHub Packages. Released v0.1.0 through v0.2.1.

**PDF Auto-Accessibility tool**
Added UGA Single Sign-On (MyID) login, role-based access and API-key management, save-time Adobe credential validation, a veraPDF second-opinion validation gate, OCR preflight for scanned PDFs, and reviewer-facing remediation output. Stood up a local Keycloak SSO test harness and removed dead Redis/Celery plumbing.

**AI Manager / EITS export**
Rebuilt the EITS "AI Tools License Requests" workbook export to match EITS's official format, corrected Copilot pricing and projected-cost formula errors (fixed a ~61% billing understatement), and added per-request pricing snapshots for accurate period billing.

**Departmental Parking Permit (DP) Smartsheet**
Built the intake form, tracking sheet, dashboards, and reference data (departments + ~3,200-person personnel directory) with a weekly n8n auto-sync, supporting Transportation & Parking's new FY27 process.

### In progress
- Rolling out @caes-webteam/ui to consumer apps (County Contributions first)
- County Contributions: replace blocking TRUNCATE in the lakehouse cache refresh; external testers
- Extension Expert Bot: release the stale-article feedback flow after ingestion testing; external tester rollout (mid-June–early July); monthly status updates
- HFIM Chatbot: dev pipeline + evaluation meeting prep
- ColdFusion maintenance (CF mail / Bouncy Castle jar error, date-picker validation, CF→git), GA Counts unplanned-support catch-all, AI form/presentation work, Fabric gateway checks, and a ColdFusion→Node/React generator conversion test

### Upcoming
- **Graduate announcement system** *(Scott leading)* — new system to manage and publish graduate announcements
- **Personnel DB rebuild** *(Jesse leading)* — refactor and rebuild the Personnel Database to modernize it
- **Expand @caes-webteam/ui** — build out the component set (tables, form controls, and more) for universal use across CAES apps, and add a distribution path so the library can be used on static pages too, not just React apps

### Timely support
**10 completed, 0 open** — n8n Asana-survey automation (90-day cleanup, email flow fixes, prefill link), Farmgate admin adds, TDX gateway on the automation server, MyID affiliate sends, and OIT Tools updates.

---

## Matthew Narron — Data Analyst

### Completed

**OMC Awards & Publications Dashboard**
Evaluated the existing Tableau dashboard, built the data connections, ingested CAES DB and combined Elements/CAESPD data, and delivered the V1 report to OMC for review.

**Employee Birthday Dashboard**
Gathered requirements, built the Power Automate list for manager emails, and wrote the how-to document.

**Grants Dashboard**
Delivered December updates and met with Andrew to resolve a connection error.

**OIT Metrics Dashboard**
Kicked off the initiative with Web Team and Help Desk planning meetings.

### In progress
- OMC Awards & Publications Dashboard — V2 report (due ~6/26)
- OIT Metrics / Leadership Dashboard — site discovery meetings (Field Services, Griffin, Tifton, Power BI connections); final deadline ~7/1
- CAES & FACS Elements Dashboard — Tableau eval, data connections, report work
- Power BI builds & migrations — New Hires/Transfers tweaks, Grants Dashboard, Parity Dashboard (Tableau→Power BI), Terminations & Transfers Dashboard, CAES Dean Financials, semantic-model research
- CAES Affiliates data-warehouse exploration (with Shawn Hill), Radon map (ArcGIS) update, migrating Power BI connections off Julia's account to OIT, Academic Analytics replacement, FarmGate mobile-layout research, Data Analyst onboarding

### Timely support
Not applicable — Matthew's work is dashboards and analytics, tracked as projects rather than timely-support tickets.

---

## Jesse Kuzy — Application Developer

### Completed

**RHEL 10 on-prem web server — infrastructure lead** *(ongoing dev & testing)*
Spearheading the new RHEL 10 on-prem web server that will host our intranet apps as we migrate off ColdFusion. Has stood up the foundation — installed the required libraries, configured the shared PostgreSQL database, established the file structure, and set up Podman for containerized app hosting. Development and testing continue as apps move over.

**Extension Expert Bot (RAG ingestion)**
Engineered the data ingestion, chunking, and upsert pipeline — Firecrawl crawls into Pinecone namespaces (Field Report, caes.uga.edu, extension, intranet) — expanded the crawl source list, optimized the crawl/ingestion scripts, and ran the new ingestion through the testing harness.

**Publications import**
Built the phased Pubs import script (phase 1 API connection → phase 2/2.5 compare + dry-run → phase 3 write to WordPress), completed the Field Report data migration, and replaced JSON file reads with live API calls.

**ETS → PEP Migration**
Reviewed the requirements doc and sent feedback, and produced the ETS category/user/session datasets PEP needs for the migration.

**Maintenance & security**
Picked a small CF app to convert for the new dev stack, remediated Oracle Java SE vulnerabilities, researched business.caes.uga.edu redirects, and completed the React class.

### In progress
- Add Cloud Sites / Sevalla to OIT Tools
- Investigate mangled publication slugs in URLs
- business.caes.uga.edu redirects (AEM .any file config)

### Upcoming
- **Personnel DB rebuild** *(Jesse leading)* — refactor and rebuild the Personnel Database to modernize it
- **Graduate announcement system** *(with Scott)* — supporting the new graduate announcement system
- **Expand @caes-webteam/ui** *(with Scott)* — build out the component set (tables, form controls, and more) for universal use across CAES apps, and add a distribution path so the library can be used on static pages too, not just React apps

### Timely support
**49 completed (a few are duplicate records), a few small items open.** This is the bulk of Jesse's quarter. Breakdown of what came in:
- **ETS access & Personnel DB** — access grants, impersonator setup, PDB data-custodian updates, account reactivations, registration windows
- **GA Counts** — error triage (several false-flag errors), two real Vue TypeError crash fixes (2,712 historical occurrences cleared), USDA NIFA race/ethnicity category updates
- **Extension Events Calendar / Destiny One** — event date/flyer fixes, approver setup, installment-payment coordination, attribution cleanup
- **AEM sites** — image-component duplication bug, redirects, navigation fixes
- **REST API** — added `getEmployeeGroup` and `showSiteURLs` parameters for OIT
- **Other** — ESTUDY date-range validation fix, OITTools reference page, file-share folders, error-log investigations

---

*Generated from Asana. Counts reflect tasks assigned to each team member with completion dates in the period.*
