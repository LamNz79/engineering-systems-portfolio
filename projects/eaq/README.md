# AQ EduEAQ — Accreditation Evidence & Self-Assessment Management System

> **My Role:** Developer + intern team coordinator · AQ Tech · 2025–2026
> **Team:** ~17 developers (mix of interns and junior devs)
> **Status:** In development
> **Source spec:** `doc/URD_EAQ_v1.2.docx` (Vietnamese, 160+ pages, written by the team)
> **Reference:** This project is built on top of the **AQnewWeb monorepo** (`C:\Users\lam\01work\AQnewWeb`), which contains the shared `@aq-fe-framework` and `@aq-fe/core-ui` packages used across all AQ Tech applications. The EAQ app in AQnewWeb (`apps/eaq/`) is the predecessor/related codebase; this project (`eaq/`) is the next-generation version.

---

## What the System Does

Enterprise web app for Vietnamese university accreditation offices. Covers the **full accreditation lifecycle**:

1. **Internal Quality Assurance** — planning, task assignment, evidence collection
2. **Self-Assessment Report Writing** — criterion-by-criterion analysis with evidence citations
3. **Multi-tier Review & Approval** — draft → review → approve workflow per criterion card
4. **External Assessor Access** — isolated portal with inline commenting on self-assessment content
5. **Post-Assessment Improvement** — closed-loop corrective action tracking across accreditation cycles

Supports multiple accreditation frameworks from a single codebase:
- **Circular 04/2016/TT-BGDĐT** (Ministry of Education Vietnamese national standards)
- **AUN-QA** (ASEAN University Network Quality Assurance)
- **Circular 12/2017/TT-BGDĐT**

Built on a microservices architecture (.NET 9 / ReactJS / SQL Server) as specified in the URD.

---

## System Architecture

The system follows a layered architecture defined in the URD:

```
User Browser (React SPA)
    ↓
Next.js App Router (apps/eaq/src/)
    ├── app/          — Next.js page routes + layouts
    ├── features/     — Feature modules (admin, auth, etc.)
    └── shared/       — Shared API clients, components, stores, hooks
    ↓
.NET 9 REST API (backend microservices)
    ↓
SQL Server Database
    ↓
External Integrations: EduSoft.NET (student info), Mail Server, File Storage
```

The frontend monorepo (`AQnewWeb`) also contains:
- `packages/aq-fe-framework` — shared React component framework
- `packages/core-ui` — core UI component library (`@aq-fe/core-ui`)
- `packages/eslint-config` · `packages/typescript-config` — shared lint/TS configs
- Other apps: `sae`, `apm`, `asm`, `icm`, `ipm`, `lom`, `qmes`, `scm`, `srm`, `stm`, `svn`, etc.

---

## Full Functional Scope (from 138-page SRS)

The system is organized into **8 process phases** and **9 functional subsystems**:

### Phase 1 — System Setup & Master Data
| Module | Description |
|---|---|
| **Account Management** | User accounts with EduSoft.NET sync for AQ Tech staff |
| **Account Group Management** | Role-based groups for batch permission assignment |
| **Permission Assignment** | Per-user permission matrix (menu-level access control) |
| **Unit-level Permissions** | Group-based scoped permissions (applies to all group members) |
| **Safety & Security Policy** | Documented security policies viewable by all users |
| **System Build/Maintenance Log** | Records of software build, maintenance, and improvement activities |
| **User Guides** | System documentation accessible to end users |
| **Document Type Catalog** | Classifies document types used across the system |
| **Unit Catalog** | Master list of organizational units (faculties, departments) |
| **Mail Server Configuration** | SMTP settings for automated email notifications |
| **Organization Info Config** | Product name and logo branding |
| **Council Role Catalog** | Roles within assessment committees (e.g., Chair, Secretary, Member) |
| **Notification Template Management** | Email templates with variable substitution for contextual alerts |

### Phase 2 — Accreditation Standards Configuration
| Module | Description |
|---|---|
| **Standards Framework Management** | Define which accreditation frameworks are active (e.g., Circular 04/2016, AUN-QA) |
| **Standards / Criteria / Requirements Tree** | Hierarchical config: Standard → Criterion → Requirement; drives all downstream workflows |
| **Training Program List** | Master list of university programs undergoing accreditation |
| **Training Program ↔ Standards Assignment** | Assigns which standards framework applies to each program |
| **Accreditation Cycles** | Define multi-year evaluation schedules per program |
| **Cycle Roadmap** | Detailed milestones with start/end dates per cycle |

### Phase 3 — Internal Quality Assurance & Planning
| Module | Description |
|---|---|
| **Work Analysis & Expected Evidence** | Decompose each requirement into: Analysis → Tasks → Expected Evidence |
| **Quality Assurance Planning** | Assign tasks to units (lead + supporting) based on analysis |
| **Writing Assignment** | Assign individual writers (staff members) to each task |
| **Periodic QA Reporting Cycles** | Define reporting periods for ongoing QA tasks |
| **Periodic QA Reports** | Staff submit progress reports per assigned task |
| **Report Submission Tracking** | Admin monitors submission status with reminder/alert system |
| **Cycle-End QA Reports** | End-of-cycle self-assessment report writing |
| **Cycle-End Report Tracking** | Monitor cycle-end report completion and review |
| **Remediation Plan** | Track limitations identified from prior assessments |
| **Remediation Assignment** | Assign corrective actions to individuals |
| **Remediation Progress Monitoring** | Periodic remediation status reporting |

### Phase 4 — Self-Assessment & External Evaluation
| Module | Description |
|---|---|
| **Self-Assessment Council Establishment (Form 01)** | Create councils with members, roles, and working groups |
| **Self-Assessment Planning (Form 02)** | Assign working groups to criteria with timelines and resources |
| **Task Assignment by Criterion** | Break down criterion tasks to individual working group members |
| **Criterion Analysis & Evidence (Form 03)** | Staff analyze each criterion: questions, collection methods, expected evidence |
| **Criterion Analysis Review** | Supervisor reviews and approves/rejects staff analyses |
| **Evidence Reconciliation** | Cross-reference expected evidence against actual evidence in the repository |
| **Evidence Review & Approval** | Authorized staff approve collected evidence |
| **Criterion Self-Assessment Report (Form 04)** | Staff draft criterion report: current status, strengths, weaknesses, action plan, self-rating |
| **Inline Commenting on Draft Reports** | Reviewers add inline text comments on draft report content |
| **Report Review & Endorsement** | Supervisor reviews, endorses, or rejects submitted reports |
| **Self-Assessment Report Export** | Print/export criterion assessment forms |
| **Self-Assessment Progress Tracking** | Real-time dashboard of self-assessment progress by criterion |
| **External Evaluation Document Management** | Manage documents related to external evaluation visits |
| **Accreditation Certificate Records** | Track and store official accreditation certificates |
| **Accreditation Results Statistics** | Aggregate and visualize accreditation outcomes |
| **Accreditation Communication** | Manage public-facing accreditation communication materials |

### Phase 5 — Post-Assessment Improvement (Closed Loop)
| Module | Description |
|---|---|
| **Limitations from Self-Assessment (by Criterion)** | Extract and track limitations identified in self-assessment reports |
| **External Team Recommendations (by Criterion)** | Record recommendations from external evaluation teams |
| **Accreditation Council Recommendations (by Criterion)** | Track recommendations from accreditation councils |
| **Consolidated Improvement Needs** | Aggregate all limitation sources into a unified improvement register |
| **Post-Evaluation Improvement Planning** | Create improvement plans from consolidated needs |
| **Improvement Task Assignment** | Assign specific improvement tasks to individuals |
| **Improvement Cycle Management** | Define periodic improvement reporting cycles |
| **Periodic Improvement Reports** | Staff submit periodic improvement progress reports |
| **Improvement Report Monitoring** | Admin monitors improvement reporting status |

### Phase 6 — Evidence Repository
| Module | Description |
|---|---|
| **Evidence Repository** | Centralized, versioned evidence storage with metadata (title, issuing body, date, validity period) |
| **Evidence Health Monitoring** | Dashboard showing expired, expiring-soon, and broken-link evidence items |
| **Evidence ↔ Criterion Linking** | Reference-based evidence citations — one evidence record cited across multiple criteria without duplication |

### Phase 7 — Reference Data & Administration
| Module | Description |
|---|---|
| **Organization Regulations** | Upload and manage organizational policies and procedures |
| **Work Process Documentation** | Reference materials for standard operating procedures |
| **Form Templates** | Standardized templates used across accreditation workflows |

### Phase 8 — Notifications & Reporting
| Module | Description |
|---|---|
| **Email Notification Engine** | Automated email alerts triggered by workflow events (submission, approval, reminder) |
| **Report Export Engine** | Admin-uploaded Word/Excel templates with variable mapping — runtime-populated reports without code changes |

---

## Data Model Overview (Key Entities)

```
BoTieuChuan (Standards Framework)
  └── TieuChuan (Standard)
        └── TieuChi (Criterion)
              └── YeuCau (Requirement)
                    └── PhanTich (Analysis)
                          ├── CongViec (Task)
                          │     └── MinhChungDuKien (Expected Evidence)
                          └── BaoCaoCongViec (Task Report)
                                └── MinhChungThucHien (Actual Evidence)

ChuongTrinhDaoTao (Training Program)
  └── GiaiDoanKiemDinh (Accreditation Cycle)
        └── ChuKyBaoCao (Reporting Cycle)

HoiDongTuDanhGia (Self-Assessment Council)
  ├── ThanhVien (Member) — role from DanhMucVaiTroHoiDong
  └── NhomCongTac (Working Group)

KhoMinhChung (Evidence Repository)
  └── MinhChung (Evidence) — versioned, reference-based

HanChe / KienNghi / KhuyenNghi (Limitations / Recommendations)
  └── KeHoachCaiTien (Improvement Plan)
        └── PhanCongCaiTien (Improvement Assignment)
```

### Evidence Versioning — Key Design Decision

> **Root-cause fix for data integrity:** Instead of duplicating evidence files across criteria and cycles, the system uses **reference-based versioning**. A single evidence record in `KhoMinhChung` can be cited from multiple `MinhChungDuKien` / `MinhChungThucHien` records. Updates to the source document propagate automatically to all citations.

---

## Key Technical Decisions

### Reference-Based Evidence Versioning
One evidence record can be cited across multiple accreditation criteria and assessment cycles without file duplication. This was designed as a root-cause fix for the data integrity problem where the same document was stored in dozens of places with no single source of truth.

### Configurable Standards Tree Engine
The Standard → Criterion → Requirement hierarchy is stored as data (not hardcoded), supporting multiple concurrent frameworks (Circular 04/2016, AUN-QA, Circular 12/2017) from a single codebase. Switching frameworks requires no code changes.

### Template-Driven Report Export
Admin users upload Word/Excel templates with mapped data variables. The engine runtime-populates templates on demand. Ministry-mandated form changes require no developer involvement — only a new template upload.

### Full Audit Trail
Every data mutation (create, update, delete) is logged with actor, timestamp, and before/after state. Required by Ministry of Education data governance standards. Audit fields (`NgayTao`, `NguoiTao`, `NgayCapNhat`, `NguoiCapNhat`, `Is_Delete`) are standard on all entity tables.

### Mail Server Integration
Configurable SMTP settings allow the system to send contextual email notifications at any workflow trigger point. Notification templates support variable substitution (e.g., `{HoTen}`, `{TenCongViec}`, `{HanChot}`).

---

## Technology Stack

### Frontend
- **Next.js** (App Router) — `apps/eaq/src/app/`
- **React 19** with TypeScript
- **TanStack Store** — shared `stores/`
- **Tailwind CSS** — `tailwind.config.ts`
- **Shared packages** from `AQnewWeb` monorepo:
  - `@aq-fe-framework` — shared component framework
  - `@aq-fe/core-ui` — core UI component library
  - `eslint-config` · `typescript-config` — monorepo-shared configs

### Backend
- **C# / .NET 9** — REST API microservices
- **Microsoft SQL Server** — relational database
- **Entity Framework Core** — ORM

### Infrastructure
- **Turborepo** monorepo (`pnpm`, `turbo.json`)
- **Azure DevOps** — CI/CD pipelines for build, test, and deployment
- **IIS** — production deployment

---

## My Contributions

### UI & Components
- Built the **dynamic report dashboard** with configurable filters, sortable paginated tables, and Excel export
- Implemented the **history view** with paginated API fetching and controlled state transitions for complex multi-field evidence forms
- Built the **evidence health monitoring dashboard** showing expiry alerts, broken links, and missing evidence across the repository
- Built role-specific **admin dashboards** with per-feature permission visibility
- Developed reusable shared components: data tables, form controls, status badges, loading skeletons

### API Integration
- Integrated **EduSoft.NET sync** with merge logic: update matched records, preserve locally-created data not present in source system
- Designed and implemented evidence versioning API endpoints supporting cross-criterion citation

### Bugs & Stability
- Resolved **50+ bugs** across UI and API layers ahead of client delivery

### Team Coordination
- Formally assigned to **review intern PRs** and translate URD specs into dev tasks
- Co-managed a team of ~17 intern developers across sprint planning, code review, and delivery milestones

---

## Spec Document

The URD (`doc/URD_EAQ_v1.2.docx`) is the original Vietnamese user requirements document — 160+ pages covering:
- **8 process phases** (system setup → standards config → QA planning → self-assessment → external evaluation → improvement → evidence repo → reporting)
- **48 workflow steps**
- **9 functional subsystems**
- Full data models with field-level type, constraint, and auto-update specifications
- Standard UI patterns: Add/Edit/Delete/Import/Export/View/Review/Notify/Print buttons with exact behavior descriptions

The SRS (this version's `eaq-srs.pdf` in `doc/`) is the **system requirements specification** derived from the URD, specifying the system as built.
