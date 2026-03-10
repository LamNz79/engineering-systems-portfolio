# AQ EduEAQ — Accreditation Evidence & Self-Assessment Management System

> **Role:** Technical Lead & Business Analyst · AQ Tech · 2025–2026  
> **Team size:** ~17 intern developers  
> **Status:** URD v1.2 finalized; system under development  
> **Original document:** [`docs/URD_EAQ_v1.2.docx`](./docs/)

---

## Overview

AQ EduEAQ is an enterprise SaaS platform that digitizes the entire accreditation lifecycle for Vietnamese higher-education institutions — from internal quality assurance and self-assessment report writing, through external review, to post-assessment improvement tracking.

The system replaces a fragmented, manual process (spreadsheets, shared drives, paper forms) with a fully structured, auditable workflow built around a closed-loop quality management cycle. It supports multiple accreditation standards including **Circular 04/2016/TT-BGDĐT** and **AUN-QA**.

---

## Problem Statement

University accreditation offices faced three core pain points before this system:

- **No centralized evidence repository** — documents were scattered across personal drives, email threads, and physical folders; the same file was duplicated across multiple criteria
- **No workflow visibility** — committee coordinators had no real-time view of who had completed their assigned self-assessment sections, making deadline management entirely manual
- **Broken improvement loop** — findings and recommendations from previous assessment cycles (self-assessment, external review, accreditation council) were not systematically tracked through to resolution; issues were frequently repeated in the next cycle

---

## System Architecture (8-Phase Closed Loop)

```
Phase 1: Admin & System Setup
  ├── Tenant config, user accounts, RBAC (per-function permissions)
  ├── Mail server, auto-notification templates, counter catalogs
  └── Report export template upload + variable mapping

Phase 2: Foundation Data
  ├── Organizational unit hierarchy
  └── Accreditation standard tree (Standard → Criterion → Requirement)

Phase 3: Program & Accreditation Roadmap Setup
  ├── Training program registry
  ├── Assign accreditation standard to program
  └── Define accreditation phases & self-assessment timeline

Phase 4: Internal Quality Assurance (IQA)
  ├── Requirement gap analysis → task breakdown
  ├── QA plan + personnel assignment for narrative writing
  └── Periodic progress reporting cycles (with mid-cycle synthesis)

Phase 5: Self-Assessment Report (SAR)
  ├── Review Council formation (Form 01) & SAR plan (Form 02)
  ├── Criterion task assignment → evidence analysis (Form 03)
  ├── Evidence cross-reference with repository
  ├── Self-assessment card authoring & multi-tier approval (Form 04)
  └── Version diff, reviewer comments, report export

Phase 6: Evidence Repository
  ├── Centralized evidence bank with versioning
  ├── Evidence reuse across criteria/cycles (no duplication)
  └── Health dashboard: expiry alerts, broken links, missing evidence

Phase 7: External Assessment Support
  ├── External review team portal (read SAR, submit comments online)
  ├── External review records & accreditation certificate management
  └── Consolidated recommendations from all sources

Phase 8: Post-Assessment Quality Improvement
  ├── Auto-aggregate findings (from SAR, external review, accreditation council)
  ├── Improvement plan + staff assignment
  └── Periodic improvement reporting & mid-cycle synthesis
```

---

## Key Technical Features

| Subsystem | Highlights |
|---|---|
| **RBAC** | Function-level permissions, user group inheritance, per-unit data filtering |
| **Standard Tree** | Configurable multi-level hierarchy: Standard → Criterion → Requirement; supports multiple accreditation frameworks simultaneously |
| **Evidence Repository** | Versioned evidence records; one evidence file can be referenced across multiple criteria and multiple assessment cycles without duplication |
| **Evidence Health Dashboard** | Real-time alerts for expired, expiring-soon, or broken-link evidence items |
| **Report Export Engine** | Admin uploads Word/Excel templates, maps data variables; system auto-generates populated reports on demand |
| **Workflow Engine** | Assignment → Draft → Review → Approve pipeline for both IQA reports and SAR criterion cards, with progress tracking |
| **Version Diff** | Side-by-side comparison of self-assessment card versions to track revisions during review rounds |
| **External Reviewer Portal** | Isolated access scope for external review teams; inline commenting directly on SAR content |
| **Audit Trail** | Full action log for all data-modifying operations; required for accreditation compliance |
| **Bulk Import** | Excel import for users, org units, and initial configuration data |
| **EduSoft.NET Sync** | Smart merge sync with source academic system: update existing records, preserve locally-created data |

---

## Non-Functional Requirements Defined

| Attribute | Target |
|---|---|
| UI response time | **< 300ms** for ≥ 90% of user interactions |
| System uptime | **> 99%** |
| Error recovery | Within **24 hours** |
| Data integrity | Full audit trail on all mutations |
| Security | Role-based access, SSL/TLS, password policy, data standards per MoET regulations |

---

## Tech Stack (Defined in URD)

| Layer | Technology |
|---|---|
| **Backend** | .NET 9 (LTS), C# |
| **Frontend** | ReactJS (latest stable), Responsive Web |
| **Database** | Microsoft SQL Server (normalized schema, indexed for report queries) |
| **Architecture** | Microservices; RESTful API / gRPC between services |
| **Deployment** | Docker containers; CI/CD; on-premise or cloud (Azure) |

---

## My Contributions

**Business Analysis & Requirements Engineering**

- Authored the full User Requirements Document (URD v1.2) — 160+ pages covering 8 process phases, 48 workflow steps, 9 functional subsystems, and 6 non-functional quality attribute scenarios
- Mapped every workflow step to specific accreditation compliance obligations (Circular 04/2016, AUN-QA), ensuring the system design was audit-ready by construction
- Defined the integration contract for EduSoft.NET sync, including conflict resolution logic (merge strategy: update on match, preserve orphaned records)

**Technical Leadership**

- Designed the microservices architecture decomposition: identified service boundaries aligned to the 7 functional subsystems to allow independent scaling of the Evidence Repository and Report Export services
- Specified the evidence versioning and reuse model — a key design decision that eliminated the duplication problem where the same document was manually copied into every criterion it supported
- Defined the report export engine contract: template upload, variable mapping configuration, and runtime population, allowing non-technical staff to manage report formats without code changes
- Led a team of ~17 intern developers across the full delivery lifecycle: sprint planning, code reviews, Azure DevOps CI/CD pipeline management, UAT coordination

**Key Design Decisions**

- **Evidence reuse over duplication** — designed the repository as a reference-based system rather than file-per-criterion, eliminating inconsistency when a source document is updated mid-cycle
- **Closed improvement loop as first-class feature** — built Phase 8 (post-assessment improvement) as a full workflow subsystem rather than a reporting afterthought, so that findings from each cycle feed directly into the next cycle's QA plan
- **Template-driven report export** — decoupled report format from application logic so that changes to Ministry-mandated form layouts (which happen frequently) require no developer involvement

---

## Tech Stack

`C# / .NET 9` · `ReactJS` · `SQL Server` · `Microservices` · `RESTful API` · `Docker` · `Azure DevOps CI/CD`
