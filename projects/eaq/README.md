# AQ EduEAQ — Accreditation Evidence & Reporting Management System

> **My Role:** Developer + intern team coordinator · AQ Tech · 2025–2026
> **Team:** ~17 developers (mix of interns and junior devs)
> **Status:** In development
> **Original spec:** [`docs/URD_EAQ_v1.2.docx`](./docs/) *(Vietnamese, written by the team)*

---

## What the system does

Enterprise web app for Vietnamese university accreditation offices. Covers the full accreditation lifecycle: internal quality assurance, self-assessment report writing, evidence collection, multi-tier review and approval, external assessor access, and post-assessment improvement tracking.

Supports multiple accreditation frameworks (Circular 04/2016/TT-BGDĐT, AUN-QA). Built on a microservices architecture (.NET 9 / ReactJS / SQL Server) as specified in the URD.

---

## What I worked on

**UI & Components**
- Built the dynamic report dashboard with configurable filters, sortable paginated tables, and export functionality
- Implemented history view with paginated API fetching and controlled state transitions for complex multi-field evidence forms
- Built evidence health monitoring dashboard showing expiry alerts, broken links, and missing evidence across the repository

**API Integration**
- Integrated EduSoft.NET sync with merge logic: update matched records, preserve locally-created data not in source system

**Bugs & Stability**
- Resolved 50+ bugs across UI and API layers ahead of client delivery

**Team coordination**
- Formally assigned to review intern PRs and translate URD specs into dev tasks on this project

---

## Stack

`React` · `TypeScript` · `C#/.NET 9` · `SQL Server` · `RESTful API` · `Docker` · `Azure DevOps`

---

## Spec document

The URD (`docs/URD_EAQ_v1.2.docx`) is the original Vietnamese user requirements document written by the team — 160+ pages covering 8 process phases, 48 workflow steps, and 9 functional subsystems. I implemented features against this spec.
