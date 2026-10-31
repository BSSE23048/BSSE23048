# Portfolio development roadmap

Owner: Agha Shoaib Zaib. Start: 1 November 2026. This is a flexible work plan, not a scheduled automation.

## Current evidence

- Profile README corrected: MCB six-week IT internship; current part-time development at Gespec.
- Glam: 6 unit tests, lint and build passed locally; first Quality CI run passed.
- HST and Auto360: project introductions/setup/demo guidance improved.
- Gym: trusted-owner rules and frontend session fix prepared; four emulator tests and build passed locally. Provision real owners and stage before deployment.
- Flourish: environment hygiene PR prepared. Credential rotation and API identity/ownership hardening remain required.
- Runtime screenshots, complete live demos and individual team-project contributions remain to be documented.

## Session sizes

**Busy university day (15 minutes):** reproduce one issue or improve one exact setup step; record evidence and next action. No commit is required if no useful change is ready.

**Normal day (45–90 minutes):** 10 minutes reproduce/read; 30–60 minutes implement one bounded change; 10–20 minutes validate, explain and update the tracker.

**Weekly review (20 minutes):** identify completed user workflows, current blockers and one next outcome. Skip or move days during exams.

## Thirty-day sequence

| Days | Outcome | Acceptance evidence |
| --- | --- | --- |
| 1–3 | Review profile/contact details and resolve security provisioning/rotation prerequisites | Correct public experience; old credential revoked; authorized owner identities recorded privately |
| 4–7 | Stage the gym authorization change and scope Flourish's API fix | Owner workflow passes; anonymous, forged-role and cross-user access denied; no production data in fixtures |
| 8–10 | Run Glam's local customer-to-admin order workflow | Same synthetic order visible to customer/admin; failure state demonstrated |
| 11–14 | Complete Glam case study and screenshots | Mobile/desktop screenshots, setup from clean checkout, CI link and limitations |
| 15–17 | Exercise HST quotation/invoice/PDF workflow | Synthetic quotation, correct totals/numbering and readable multi-page PDF |
| 18–21 | Exercise Auto360's real-photo workflow | Rotation, missing-frame feedback, original inspection and draft/public boundary demonstrated |
| 22–24 | Select one maintained open-source issue | Reproduced current issue; contributor guide read; no existing active duplicate fix |
| 25–27 | Prepare a focused upstream fix or technical report | Minimal reproduction, relevant test and understandable explanation; submit only if appropriate |
| 28–30 | Review portfolio and choose one next build | Two strong demos; ownership clarified; actual PR outcomes recorded; one justified project selected |

Use approximately four sessions per week on owned projects, one on open source, one flexible catch-up and one rest/review day. Genuine incident/security work takes precedence.

## Progress tracker

Append one row per meaningful outcome; keep submitted and merged contributions distinct.

| Date | Repository / issue | User outcome | Validation | PR / evidence | State | Next action |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-11-01 | Profile | Correct internship/part-time positioning | CV and owner clarification; Markdown review | [PR 1](https://github.com/BSSE23048/BSSE23048/pull/1) | Merged | Confirm contact details |
| 2026-11-01 | Glam | Repeatable lint/test/build workflow | 6 unit tests + lint/build locally; first CI passed | [PR 1](https://github.com/BSSE23048/glam_skincare/pull/1) | Merged | Run synthetic order demo |
| 2026-11-01 | HST | Clear business-workflow README | Source/path/script review | [PR 1](https://github.com/BSSE23048/HST_Enterprises/pull/1) | Merged | Capture synthetic PDF workflow |
| 2026-11-01 | Auto360 | Clear viewer/setup/release documentation | Source/path/script review | [PR 1](https://github.com/BSSE23048/Auto360-Studio/pull/1) | Merged | Execute release acceptance checks |

Do not use commit counts or green squares as success measures. Useful measures are a completed workflow, reproducible fix, current working demo, relevant test, accurate documentation and accepted upstream contribution.

## Profile settings to apply when supported access is available

Suggested bio:

> Software Engineering student at ITU Lahore | React, Next.js & business web apps | Part-time developer | Open to scoped freelance work

Pin Glam, HST and Auto360 first. Add Flourish, Gym and MediSense after security, privacy and demonstration checks. Do not fill six slots with weaker evidence merely to reach six.

| Repository | Suggested description | Suggested topics |
| --- | --- | --- |
| glam_skincare | React/TypeScript storefront with Firebase order workflows and automated tests | react, typescript, firebase, ecommerce, playwright |
| HST_Enterprises | Business website and authenticated quotation/invoice portal built with React and Firebase | react, typescript, firebase, invoicing |
| Auto360-Studio | Photo-based vehicle inspection viewer with Supabase and a Cloudflare Worker API | react, typescript, supabase, cloudflare-workers |
| flourish-salon-pro | Next.js/Express salon booking and operations prototype with Supabase | nextjs, express, typescript, supabase, booking |
| fitness-kingdom-gym | React/Firebase member, payment and attendance management for a gym | react, firebase, gym-management |
| MediSense | Collaborative healthcare report OCR, retrieval and voice prototype using Angular and Flask | angular, flask, python, ocr, rag |

These are proposed settings, not a record that the profile bio, topics or pins were changed.

## Three next-project options — choose only after the existing-project gates

### 1. Webhook inbox and safe replay service — recommended gap

**User/problem:** a small business developer needs to understand failed third-party callbacks without processing the same event twice.

**Portfolio value:** demonstrates backend reliability, signatures, idempotency, retries, observability and integration testing rather than another CRUD dashboard.

**MVP/architecture:** TypeScript API, SQLite event store and a small Next.js dashboard. Validate one documented provider-style HMAC contract, record unique event IDs, show status and permit controlled local replay. Use synthetic events and local HTTP destinations.

**Acceptance:** bad signatures rejected; repeated event IDs produce one logical delivery; failed deliveries retry with bounded backoff; replay is authenticated; logs redact credentials; tests cover duplicates and timeouts.

**Milestones/effort estimates:** contract and fixtures 2–3h; receipt/storage 3–4h; delivery/retry tests 4–6h; dashboard/demo/docs 3–5h. Total estimate: 12–18h, adjusted after discovery.

**Demo/deployment/cost:** run API, dashboard and a fake recipient locally; record duplicate/failure/retry scenarios. Local tooling needs no paid services. Choose hosting only after checking storage, outbound-network and background-worker support; no paid plan is authorized.

### 2. Import and reconciliation workbench

**User/problem:** a small business has inconsistent CSV exports and needs to identify duplicate, missing or mismatched records before importing them.

**Portfolio value:** complements existing invoices/dashboards with data quality and auditable decisions.

**MVP/architecture:** React/TypeScript UI, deterministic parsing/validation module and a Python/FastAPI API only if server processing is needed. Start local with synthetic files; no bank connection or payment execution.

**Acceptance:** invalid rows produce precise errors; duplicate IDs are flagged; decimal amounts compare correctly; original inputs remain unchanged; exported results explain each match/mismatch; fixtures cover encoding and missing columns.

**Milestones/effort estimates:** schema/fixtures 2h; parser/rules/tests 3–5h; review UI 3–4h; demo/docs 2–3h. Total estimate: 10–14h.

**Demo/deployment/cost:** static local demonstration with downloadable synthetic fixtures. Client-only deployment may be sufficient; verify current provider limits before hosting. No external paid API is required for the MVP.

### 3. Small RAG evaluation workbench

**User/problem:** a developer needs evidence that document answers are grounded, rather than judging a chatbot by a few impressive responses.

**Portfolio value:** adds evaluation, failure analysis and transparent limitations to existing AI project claims.

**MVP/architecture:** Python evaluation runner, fixed synthetic question/document set, a retrieval adapter and a simple results viewer. Default to recorded fixture responses; optionally test one model provider with explicit cost control.

**Acceptance:** versioned dataset; retrieval hit/miss results; cited-document checks; abstention cases; repeatable report; examples of incorrect answers; clear distinction between deterministic metrics and human judgments.

**Milestones/effort estimates:** dataset/criteria 3–4h; runner/fixtures 3–4h; report/viewer 2–3h; documentation 2–3h. Total estimate: 10–14h.

**Demo/deployment/cost:** reproduce results locally without API credentials using fixtures. Real-model calls and hosted deployment are optional later; do not assume free usage or enable billing.
