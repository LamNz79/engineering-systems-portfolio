# CV Highlights — Quick Reference

> Copy-paste bullets from the relevant section when tailoring your CV.
> All bullets are grounded in SAE and EAQ project docs.

---

## Frontend Roles

**AQ EduSAE** — Student Activity & Evaluation Portal
- Built role-specific dashboards for 6 distinct user types (students, advisors, homeroom teachers, student affairs staff, review council members, admins) in React, each with a tailored information architecture
- Designed a student personal planning UI enabling proactive semester-level activity scheduling, replacing a passive end-of-semester self-declaration flow
- Led frontend delivery for a complaint management workflow with evidence attachment, multi-state tracking
- Delivered real-time monitoring dashboards for academic advisors and homeroom teachers with drill-down to individual student activity records, targeting ≤3 clicks to reach any student's result

**AQ EduEAQ** — Accreditation Management System
- Implemented a multi-tier document review UI (draft → review → approve) with side-by-side version diff for self-assessment criterion cards
- Designed and built an evidence health monitoring dashboard with alerts for expired, expiring-soon, and broken-link evidence items
- Built a report export UI allowing non-technical staff to upload Word/Excel templates, map data variables, and generate populated accreditation reports on demand — zero developer involvement for format changes
- Delivered a responsive web interface targeting < 300ms response time for ≥ 90% of user interactions across both desktop and mobile browsers
- Implemented an external reviewer portal with isolated access scope and inline commenting on self-assessment content

---

## Backend Roles

**AQ EduSAE** — Student Activity & Evaluation Portal
- Designed and implemented a score-at-source recording system: only the authorized organizing unit can record scores for its own activities, eliminating self-declaration and reducing evidence file dependency by 70%
- Implemented QR code and student card attendance pipeline: real-time event check-in data flows directly into the score recording system, replacing manual file upload evidence
- Defined data model and API contracts for a full complaint handling workflow: submission, evidence attachment, assignment, resolution, audit trail

**AQ EduEAQ** — Accreditation Management System
- Designed a reference-based evidence versioning system: one evidence record can be cited across multiple accreditation criteria and assessment cycles without file duplication; updates to source documents propagate automatically to all citations
- Built a configurable accreditation standard tree engine (Standard → Criterion → Requirement) supporting multiple concurrent frameworks (Circular 04/2016, AUN-QA) from a single codebase
- Specified full audit trail requirements across all data-mutating operations, compliant with Ministry of Education data governance standards
- Designed a template-driven report export engine: admin-uploaded Word/Excel templates with mapped data variables, runtime-populated without code changes

**Across both projects**
- Managed Azure DevOps CI/CD pipelines for build, test, and deployment across development and staging environments
- Led a team of ~17 intern developers: sprint planning, code review, technical mentorship, delivery milestone management

---

## Fullstack Roles

**AQ EduSAE** — Student Activity & Evaluation Portal
*University SaaS platform managing student extracurricular activities and conduct scoring for Vietnamese higher-education institutions.*

- Led full-stack delivery as Technical Lead and BA on a team of ~17 intern developers, owning the project from BRD authorship through production deployment
- Designed a PDCA-based (Plan–Do–Check–Act) system architecture that transformed a passive, end-of-semester self-reporting process into a real-time, auditable management cycle — replacing a workflow that generated 10,000+ manual evidence files per semester
- Built score-at-source recording backed by EduSoft.NET REST integration and QR/student card attendance pipelines, reducing file-evidence dependency by 70% and manual staff processing time by 75%
- Delivered role-specific React dashboards for 6 user types with real-time monitoring, targeting ≤3 clicks to surface any student's activity result
- Implemented multi-tenant RBAC (School → Faculty → Class hierarchy) and a complaint handling workflow compliant with Vietnamese Ministry of Education Circular 16/2015
- Defined measurable system targets: ≥90% student adoption, ≤5 business days complaint resolution, <5s aggregate reports for 10,000 students

**AQ EduEAQ** — Accreditation Evidence & Self-Assessment Management System
*Enterprise SaaS platform digitizing the full accreditation lifecycle for universities.*

- Authored URD v1.2 (160+ pages, 48 workflow steps, 9 subsystems) and led full-stack implementation across a microservices architecture (.NET 9 / ReactJS / SQL Server / Docker)
- Designed a reference-based evidence versioning system eliminating document duplication across accreditation criteria and cycles — a root-cause fix for the core data integrity problem
- Built configurable accreditation standard tree engine supporting multiple concurrent frameworks (Circular 04/2016, AUN-QA) from a single codebase
- Implemented closed post-assessment improvement loop as a first-class workflow subsystem, ensuring findings from each cycle feed directly into the next cycle's QA plan
- Delivered template-driven report export engine (admin-managed Word/Excel templates with variable mapping) allowing non-technical staff to manage Ministry-mandated form changes without developer involvement
- Defined non-functional requirements: <300ms UI response (90th percentile), >99% uptime, full audit trail on all mutations
