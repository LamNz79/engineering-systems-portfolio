# CV Highlights — Quick Reference

> Copy-paste bullets from the relevant section when tailoring your CV.
> All bullets are grounded in SAE and EAQ project docs (BRD/URD/SRS).

---

## Frontend Roles

**AQ EduSAE** — Student Activity & Evaluation Portal
- Built role-specific dashboards for 6 distinct user types (students, advisors, homeroom teachers, student affairs staff, review council members, admins) in React, each with a tailored information architecture
- Designed a student personal planning UI enabling proactive semester-level activity scheduling, replacing a passive end-of-semester self-declaration flow
- Led frontend delivery for a complaint management workflow with evidence attachment, multi-state tracking (submission → assignment → resolution → audit trail), compliant with MoET Circular 16/2015
- Delivered real-time monitoring dashboards for academic advisors and homeroom teachers with drill-down to individual student activity records, targeting ≤3 clicks to reach any student's result
- Resolved a circular dependency between TanStack Store and API calls that was causing significant UI performance degradation

**AQ EduEAQ** — Accreditation Management System
- Built the **evidence health monitoring dashboard** with expiry alerts, broken-link detection, and missing-evidence heatmap across the accreditation cycle
- Implemented a multi-tier document review UI (draft → review → approve) with side-by-side version diff for self-assessment criterion cards
- Designed and built a **report export UI** allowing non-technical staff to upload Word/Excel templates, map data variables, and generate populated accreditation reports on demand — zero developer involvement for format changes
- Delivered a responsive web interface targeting < 300ms response time for ≥ 90% of user interactions across both desktop and mobile browsers
- Implemented an **external reviewer portal** with isolated access scope and inline commenting on self-assessment content
- Built the dynamic report dashboard with configurable filters, sortable paginated tables, and Excel export

---

## Backend Roles

**AQ EduSAE** — Student Activity & Evaluation Portal
- Designed and implemented a **score-at-source recording system**: only the authorized organizing unit can record scores for its own activities, eliminating self-declaration and reducing evidence file dependency by ~70%
- Implemented **QR code and student card attendance pipeline**: real-time event check-in data flows directly into the score recording system, replacing manual file upload evidence
- Defined data model and API contracts for a full complaint handling workflow: submission, evidence attachment, assignment, resolution, audit trail

**AQ EduEAQ** — Accreditation Evidence & Self-Assessment Management System
- Designed a **reference-based evidence versioning system**: one evidence record can be cited across multiple accreditation criteria and assessment cycles without file duplication; updates to source documents propagate automatically to all citations
- Built a **configurable accreditation standard tree engine** (Standard → Criterion → Requirement) supporting multiple concurrent frameworks (Circular 04/2016, AUN-QA, Circular 12/2017) from a single codebase
- Specified full audit trail requirements across all data-mutating operations, compliant with Ministry of Education data governance standards
- Designed a **template-driven report export engine**: admin-uploaded Word/Excel templates with mapped data variables, runtime-populated without code changes
- Integrated EduSoft.NET sync with merge logic: update matched records, preserve locally-created data not present in source system

**Across both projects**
- Managed Azure DevOps CI/CD pipelines for build, test, and deployment across development and staging environments
- Led a team of ~17 intern developers: sprint planning, code review, technical mentorship, delivery milestone management
- Resolved 50+ bugs across UI and API layers ahead of client delivery

---

## Fullstack Roles

**AQ EduSAE** — Student Activity & Evaluation Portal
*University SaaS platform managing student extracurricular activities and conduct scoring for Vietnamese higher-education institutions. Replaced a manual process generating 10,000+ evidence files per semester.*

- Led full-stack delivery as Technical Lead and BA on a team of ~17 intern developers, owning the project from BRD authorship through production deployment
- Designed a **PDCA-based (Plan–Do–Check–Act) system architecture** that transformed a passive, end-of-semester self-reporting process into a real-time, auditable management cycle — replacing a workflow that generated 10,000+ manual evidence files per semester
- Built **score-at-source recording** backed by EduSoft.NET REST integration and QR/student card attendance pipelines, reducing file-evidence dependency by ~70% and manual staff processing time by ~75%
- Delivered role-specific React dashboards for 6 user types with real-time monitoring, targeting ≤3 clicks to surface any student's activity result
- Implemented multi-tenant RBAC (School → Faculty → Class hierarchy) and a complaint handling workflow compliant with Vietnamese Ministry of Education Circular 16/2015
- Defined measurable system targets: ≥90% student adoption, ≤5 business days complaint resolution, <5s aggregate reports for 10,000 students

**AQ EduEAQ** — Accreditation Evidence & Self-Assessment Management System
*Enterprise SaaS platform digitizing the full accreditation lifecycle for universities: internal quality assurance, self-assessment report writing, evidence collection, multi-tier review, external assessor access, and post-assessment improvement tracking.*

- Authored URD v1.2 (160+ pages, 48 workflow steps, 9 functional subsystems) and led full-stack implementation across a microservices architecture (.NET 9 / ReactJS / SQL Server)
- Designed a **reference-based evidence versioning system** eliminating document duplication across accreditation criteria and cycles — a root-cause fix for the core data integrity problem
- Built **configurable accreditation standard tree engine** supporting multiple concurrent frameworks (Circular 04/2016, AUN-QA, Circular 12/2017) from a single codebase
- Implemented **closed post-assessment improvement loop** as a first-class workflow subsystem: limitations from self-assessment, external team recommendations, and council recommendations are consolidated into a unified improvement register and tracked through assignment → periodic reporting → monitoring
- Delivered **template-driven report export engine** (admin-managed Word/Excel templates with variable mapping) allowing non-technical staff to manage Ministry-mandated form changes without developer involvement
- Defined non-functional requirements: <300ms UI response (90th percentile), >99% uptime, full audit trail on all mutations

---

## Architecture & Platform Skills

- **Turborepo monorepo** — pnpm workspace with shared `@aq-fe-framework` and `@aq-fe/core-ui` packages across 15+ apps
- **Azure DevOps** — CI/CD pipeline authoring (build, test, deploy dev/staging)
- **REST API design** — resource-oriented, paginated endpoints, consistent error contracts
- **SQL Server** — entity design, foreign key constraints, soft delete (`Is_Delete` pattern), audit fields on all entities
- **Next.js App Router** — page routes, layouts, feature modules, shared API/stores/providers layers
- **Shared component framework** — contributed to `@aq-fe-framework` used across all AQ Tech applications

---

## Spec Documents

| Document | Project | Pages | Content |
|---|---|---|---|
| BRD_SAE_v1.2.docx | EduSAE | ~100+ | Full Vietnamese BRD — all user types, workflows, PDCA cycle, RBAC model, MoET Circular 16/2015 compliance |
| URD_EAQ_v1.2.docx | EduEAQ | 160+ | Full Vietnamese URD — 8 phases, 48 steps, 9 subsystems, field-level specs |
| eaq-srs.pdf | EduEAQ | 138 | System Requirements Specification — detailed UI specs, data models, control types |
