# AQ EduSAE — Student Activity & Conduct Scoring Portal

> **My Role:** Developer + intern team coordinator · AQ Tech · 2025
> **Team:** ~17 developers (mix of interns and junior devs)
> **Status:** In development
> **Source spec:** `docs/BRD_SAE_v1.2.docx` (Vietnamese, written by the team)
> **Reference:** This project is built on top of the **AQnewWeb monorepo** (`C:\Users\lam\01work\AQnewWeb`). The SAE app in AQnewWeb (`apps/sae/`) is the predecessor/related codebase; this project (`sae/`) is the next-generation version.

---

## What the System Does

University SaaS platform managing **student extracurricular activity participation** and **conduct score (điểm rèn luyện — ĐRL) evaluation** for Vietnamese higher-education institutions.

The system replaces a manual, end-of-semester self-reporting process where students submitted conduct scores along with evidence files — a process that previously generated **10,000+ uploaded files per semester**, creating a heavy verification burden for university staff.

The new platform introduces a structured, auditable workflow:

1. **Universities define extracurricular activities** — structured activity catalog with criteria and scoring rubrics
2. **Students register for activities** — proactive enrollment before activity dates
3. **Participation is recorded** — via QR code or student card scan at events (replacing manual attendance taking)
4. **Advisors monitor progress** — real-time semester dashboards per student and per class
5. **Evaluation councils review** — multi-tier review workflow leading to finalized conduct scores
6. **Scores are finalized** — end-of-semester score aggregation and publication

The system is designed to comply with **Vietnamese MoET Circular 16/2015** (Quy chế công tác sinh viên).

---

## System Architecture

```
Student / Advisor / Staff / Admin Browser
    ↓
React SPA Frontend
    ├── apps/sae/src/
    │     ├── app/          — Next.js page routes + layouts
    │     ├── features/     — Feature modules
    │     └── shared/       — API clients, stores, hooks, utils
    └── packages/ (from AQnewWeb monorepo)
          ├── @aq-fe-framework   — shared component framework
          └── @aq-fe/core-ui     — core UI library
    ↓
.NET Backend REST API
    ↓
SQL Server Database
    ↓
External Integrations:
  ├── EduSoft.NET (student academic data sync)
  ├── QR Code / Student Card Attendance System
  └── File Storage (evidence attachments)
```

The AQnewWeb monorepo (`C:\Users\lam\01work\AQnewWeb`) also contains:
- `packages/aq-fe-framework` — shared React component framework
- `packages/core-ui` — `@aq-fe/core-ui` component library
- Other apps: `eaq`, `apm`, `asm`, `icm`, `ipm`, `lom`, `qmes`, `scm`, `srm`, `stm`, `svn`, `school`, etc.

---

## Functional Scope (from BRD v1.2)

### Core Modules

| Module | Description |
|---|---|
| **Activity Planning & Registration** | Universities define activities with criteria, max participants, and registration windows. Students proactively register before events. |
| **Attendance Recording** | QR code scan or student card tap records attendance in real time. Attendance data flows directly into the scoring system. |
| **Score-at-Source Recording** | Only the authorized organizing unit can record scores for its own activities. Eliminates self-declaration. |
| **Conduct Score Aggregation** | Semester-level score calculation from all attended activities. Final scores subject to council review. |
| **Student Dashboard** | Each student sees their registered activities, attendance history, and current conduct score. |
| **Advisor Dashboard** | Homeroom teachers and faculty advisors see their assigned students' activity participation and scores. |
| **Staff Dashboard** | Student affairs staff manage the full activity lifecycle and monitor school-wide participation rates. |
| **Council Review Workflow** | Evaluation councils review, comment, and finalize conduct scores per student. |
| **Complaint Management** | Students can lodge complaints with evidence attachments; complaints flow through assignment → resolution → audit trail. |
| **Report & Export** | Aggregated reports on participation rates, score distributions, activity popularity. |

---

## Key Technical Decisions

### Score-at-Source Recording
Only the authorized organizing unit (the club/faculty that ran the activity) can enter scores for that activity. Students cannot self-declare. This eliminates the incentive to fabricate evidence and makes scores directly attributable. This design reduced file-evidence dependency by approximately **70%** compared to the previous self-reporting model.

### QR Code / Student Card Attendance Pipeline
Real-time event check-in data flows directly from the attendance scanning system into the score recording system, replacing manual file upload evidence. Staff no longer need to collect and verify attendance spreadsheets.

### PDCA-Based System Architecture
The system implements a **Plan–Do–Check–Act** (PDCA) cycle:
- **Plan** — Activity definitions, criteria, registration windows
- **Do** — Student registration, attendance recording, score entry
- **Check** — Advisor dashboards, council review, compliance monitoring
- **Act** — Score finalization, complaint resolution, semester reporting

This transformed a passive, end-of-semester self-reporting process into a **real-time, auditable management cycle**.

### Complaint Handling Workflow
Multi-state complaint workflow compliant with MoET Circular 16/2015:
- Submission → Evidence attachment → Assignment → Investigation → Resolution → Audit trail
- Each state transition is logged with actor and timestamp

### Multi-Tenant RBAC
Role hierarchy: **School → Faculty → Class**
- Admins manage school-level settings
- Faculty managers oversee their department's activities and students
- Homeroom teachers monitor their class
- Students see only their own records

---

## System Modules Detail

### User Types & Role-Specific Dashboards

| User Type | Dashboard Capabilities |
|---|---|
| **Students** | View registered activities, attendance history, conduct score, lodge complaints |
| **Academic Advisors** | Monitor assigned students' participation, drill-down to individual records (≤3 clicks to any student result) |
| **Homeroom Teachers** | Class-level participation monitoring, conduct score oversight |
| **Student Affairs Staff** | Full activity lifecycle management, school-wide reporting, score finalization |
| **Evaluation Council Members** | Review student conduct files, approve/reject scores, access audit trail |
| **System Administrators** | User management, RBAC configuration, system settings |

### Performance Targets (from BRD)
| Metric | Target |
|---|---|
| Student adoption rate | ≥ 90% |
| Complaint resolution time | ≤ 5 business days |
| Aggregate report generation (10,000 students) | < 5 seconds |
| UI response time (90th percentile) | < 300ms |

---

## Technology Stack

### Frontend
- **Next.js** (App Router) — `apps/sae/src/app/`
- **React 19** with TypeScript
- **TanStack Store** — shared `stores/`
- **Tailwind CSS**
- **Shared packages** from `AQnewWeb` monorepo:
  - `@aq-fe-framework` — shared component framework
  - `@aq-fe/core-ui` — core UI component library

### Backend
- **C# / .NET** — REST API
- **Microsoft SQL Server** — relational database

### Infrastructure
- **Turborepo** monorepo (`pnpm`, `turbo.json`)
- **Azure DevOps** — CI/CD pipelines (build, test, deployment to dev + staging)
- **IIS** — production deployment
- Monorepo architecture (frontend + backend in one repo)

---

## My Contributions

### Frontend Development
- Built **role-specific dashboards for 6 user types**: students, academic advisors, homeroom teachers, student affairs staff, evaluation council members, and system administrators — each with tailored information architecture
- Developed **reusable UI components** shared across dashboards: data tables, form controls, status badges, loading skeletons, paginated API fetching
- Implemented **semester-based activity listing** with paginated API integration
- Designed a **student personal planning UI** enabling proactive semester-level activity scheduling, replacing the passive end-of-semester self-declaration flow
- Led frontend delivery for the **complaint management workflow** with evidence attachment and multi-state tracking

### System Integration
- Integrated **EduSoft.NET API** for academic-grade synchronization with conduct scoring workflows
- Implemented **QR code and student card attendance pipeline** — real-time check-in data flows directly into the score recording system

### Performance & Debugging
- Diagnosed and resolved a **circular dependency between TanStack Store and API calls** that was causing significant UI performance degradation

### Team Coordination
- Formally assigned to **review intern pull requests** and translate BRD specifications into development tasks
- Coordinated feature implementation across the intern development team

---

## Spec Document

The BRD (`docs/BRD_SAE_v1.2.docx`) is the original Vietnamese requirements document written by the team. It covers:
- Full business process design (PDCA cycle)
- Feature list and workflow specs for all 6+ user types
- Conduct score calculation rules and rubrics
- Complaint handling workflow (MoET Circular 16/2015 compliant)
- RBAC model (School → Faculty → Class hierarchy)
- Non-functional requirements (performance targets, adoption targets)
