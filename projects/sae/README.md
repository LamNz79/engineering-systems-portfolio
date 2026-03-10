# AQ EduSAE — Student Activity & Conduct Scoring Portal

> **My Role:** Developer + intern team coordinator · AQ Tech · 2025
> **Team:** ~17 developers (mix of interns and junior devs)
> **Status:** In development
> **Original spec:** [`docs/BRD_SAE_v1.2.docx`](./docs/) *(Vietnamese, written by the team)*

---

## What the system does

Multi-university SaaS portal that replaces a manual, end-of-semester self-declaration workflow for student conduct scoring (*điểm rèn luyện*). Before this system, students submitted their own scores at the end of semester — generating 10,000+ uploaded evidence files per cycle that staff couldn't realistically verify.

The replacement is a real-time cycle: universities plan activities upfront, students register and attend, staff record scores via QR/card or import, advisors monitor progress mid-semester, and a review council finalizes results. Compliant with Vietnamese MoET Circular 16/2015.
![Architect](projects/sae/docs/images/sae-system.png)
---

## What I worked on

**UI & Components**
- Built role-specific dashboards for 6 user types (students, advisors, homeroom teachers, student affairs staff, council members, admins)
- Designed and maintained a reusable component library (tables, forms, badges, loading states) shared across all dashboards
- Implemented semester-based activity listing with paginated API fetching and loading state management

**API Integration**
- Integrated EduSoft.NET API for academic-grade-to-conduct-score sync

| Pages | Purpose |
|---|---|
| **Register Extracurricular Activity Plan** | Faculty, Club, Student support, etc... to register activity |
| **AnnualPlan PlanApproval** | Approving registered activity |
| **AnnualPlan StudentAffair** | Student affair to do CRUD method on activity of this and other semester in this year EX: 20251, 20252|
| **ExecutePlan ConfigRegistration** | Setting time for classes to register into activity  |
| **Current Semester** | CRUD on this current semester events |


**Bugs & Performance**
- Diagnosed and fixed a circular dependency between TanStack Store and API calls that was causing significant UI slowness

**Team coordination**
- Formally assigned to review intern PRs and break BRD specs down into dev tasks on this project

---

## Stack

`React` · `TypeScript` · `TanStack Store` · `C#/.NET` · `PostgreSQL` · `Docker` · `Azure DevOps`

---

## Spec document

The BRD (`docs/BRD_SAE_v1.2.docx`) is the original Vietnamese requirements document written by the team. It covers the full business process design, feature list, and workflow specs that I implemented against.
