# AQ EduSAE — Student Activity & Evaluation Portal

> **Role:** Technical Lead & Business Analyst · AQ Tech · 2025
> **Team size:** ~17 intern developers
> **Status:** Requirements finalized (BRD v1.2); system under development
> **Original document:** [`docs/BRD_SAE_v1.2.docx`](./docs/)

---

## Overview

AQ EduSAE is a university SaaS platform that digitizes the management of student extracurricular activities and conduct scoring (*điểm rèn luyện*) for higher-education institutions in Vietnam.

The system replaces a fully manual, end-of-semester self-reporting process — which generated over **10,000 uploaded evidence files per cycle** and produced unreliable, qualitative-only results — with a structured, real-time **Plan–Do–Check–Act (PDCA)** management cycle compliant with **Vietnamese Ministry of Education Circular 16/2015/TT-BGDĐT**.

---

## Problem Statement

Before this system, universities managed student conduct scores through:

- **End-of-semester self-declaration** — students submitted their own scores at the last minute, making real-time intervention impossible
- **Manual evidence floods** — 10,000+ uploaded image/document files per semester that staff physically could not verify
- **No mid-semester monitoring** — academic advisors and homeroom teachers had no visibility into student progress until it was too late to remediate
- **Fragmented multi-party coordination** — Student Affairs Office, Youth Union, Faculty Boards, and Review Councils operated without a shared process or data source

---

## Solution Architecture (PDCA Model)

The system is structured around four operational phases:

```
PLAN ──────────────────────────────────────────────────────────
  Score framework configuration (max points, mandatory activities)
  Annual/semester activity planning by Student Affairs & Youth Union
  Auto-enrollment of mandatory activities; student personal planning

DO ────────────────────────────────────────────────────────────
  Activity execution & attendance (QR code / student card / import)
  Score recording by authorized organizational units only
  EduSoft.NET integration: auto-convert academic grades → conduct points

CHECK ─────────────────────────────────────────────────────────
  Evidence review & score approval workflow
  Real-time monitoring dashboard for academic advisors & homeroom teachers
  Student complaint submission with evidence attachment

ACT ───────────────────────────────────────────────────────────
  Faculty-level and university-level Review Council workflows
  Finalization and public disclosure (20-day notice per Circular 16)
  Aggregate reporting for institutional improvement
```

---

## Key Features (15 Feature Groups)

| Group | Capability |
|---|---|
| **Admin** | User accounts, group management, role-based permissions |
| **Document Management** | Regulatory docs, process guides, form templates |
| **Score Framework** | Configurable scoring rubric, mandatory activity catalog |
| **Activity Planning** | Department activity registration & approval workflow |
| **Activity Execution** | Notifications, class-based registration windows, progress tracking |
| **Score Recording** | Bulk import, QR/card attendance, evidence upload |
| **Score Approval** | Multi-step review and official recognition workflow |
| **Complaint Handling** | Student submissions, staff resolution, audit trail |
| **University Monitoring** | Real-time dashboards for school-level oversight |
| **Advisor Monitoring** | Per-class drill-down for academic advisors |
| **Homeroom Monitoring** | Per-class drill-down for homeroom teachers |
| **Review Council** | Faculty-level and university-level committee workflows |
| **Lookup Tools** | Student self-service: score lookup, activity history, transcripts |
| **Reporting** | Faculty & university aggregate reports (target: <5s for 10k students) |
| **Student Portal** | Planning, evidence submission, score confirmation, complaints |

---

## Measurable Targets Defined in BRD

| Metric | Target |
|---|---|
| Reduction in file-evidence dependency | **−70%** |
| Staff manual processing time (data entry + reporting) | **−75%** |
| Complaint resolution time | **≤5 business days** |
| Advisor monitoring actions to reach a student's result | **≤3 clicks** |
| Students completing personal planning & score confirmation | **≥90%** |
| System adoption rate (staff + students) | **≥95%** |
| Report generation time (10k students) | **<5 seconds** |

---

## Technical Integration Points

- **EduSoft.NET sync** — REST integration to pull academic grade data and auto-convert to conduct points based on a configurable conversion matrix
- **QR code / student card attendance** — real-time attendance recording that eliminates manual file evidence for participation events
- **Mail server configuration** — templated automated email notifications for activity announcements, approvals, and score publication
- **Multi-tenant org structure** — supports School → Faculty → Department → Class hierarchy with cascading RBAC

---

## My Contributions

As **Technical Lead and Business Analyst** on this project, my responsibilities spanned both the product definition and engineering coordination layers:

**Business Analysis & Requirements**
- Authored the full Business Requirements Document (BRD) across 3 versions (v1.0 → v1.2), covering 11 business process groups and 15 feature groups
- Conducted stakeholder analysis across 6 actor types: System Admin, Student Affairs staff, Youth Union, Academic Advisors, Review Council members, and Students
- Mapped all workflows to Circular 16/2015/TT-BGDĐT legal requirements, ensuring regulatory compliance was built into the process design rather than retrofitted

**Technical Leadership**
- Defined the PDCA-based system architecture that transformed a passive end-of-semester reporting model into a continuous, auditable management cycle
- Designed the multi-tier approval workflow (Record → Approve → Review Council → Publish) ensuring data integrity and accountability at each stage
- Specified the EduSoft.NET integration contract and QR/card attendance data flows
- Led a team of ~17 intern developers, managing sprint planning, code reviews, and delivery milestones via Azure DevOps

**Key Design Decisions**
- Chose score-at-source over student self-declaration to eliminate the reliability problem at its root — only the organizing unit can record scores for its own activities
- Designed complaint handling as a first-class workflow (not an afterthought) to satisfy transparency requirements under Circular 16
- Introduced a student personal planning feature so students have visibility into the full semester's activity calendar from day one, enabling proactive participation instead of last-minute remediation

---

## Tech Stack

`C# / .NET` · `Node.js` · `TypeScript` · `React` · `PostgreSQL` · `Docker` · `Azure DevOps CI/CD`

---

## Document

The original Vietnamese BRD (`BRD_SAE_v1.2.docx`) is included in [`docs/`](./docs/) as evidence of the requirements work. It contains the full process diagrams, feature specifications, risk register, and constraints section.
