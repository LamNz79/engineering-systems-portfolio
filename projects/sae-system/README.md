# SAE – Student Activity & Evaluation System

## Overview

The **Student Activity & Evaluation System (SAE)** is a platform designed to manage and evaluate university student extracurricular activities and conduct scores.

The system replaces manual, end-of-semester evaluation with a structured digital workflow based on the **Plan – Do – Check – Act (PDCA)** management model.

Instead of relying on large volumes of uploaded evidence files and manual verification, SAE introduces automated participation tracking, role-based workflows, and centralized evaluation processes.

The system supports the full lifecycle of extracurricular activity management, from planning and participation tracking to evaluation and final approval.

---

## Problem

Traditional extracurricular evaluation processes often suffer from several operational issues.

### Late Self-Reporting

Students typically submit activity declarations at the end of the semester, making verification difficult and evaluations subjective.

### Evidence Overload

Administrators must review large volumes of uploaded files, which is time-consuming and prone to errors.

### Limited Monitoring

Academic advisors and departments lack tools to track student participation throughout the semester.

### Fragmented Workflow

Multiple stakeholders are involved in evaluation, including administrative departments, faculty advisors, and evaluation councils.

Without automation, coordination becomes slow and inconsistent.

---

## Solution

SAE digitizes the entire evaluation lifecycle through a **PDCA-driven workflow**.

### Plan

Administrative units define evaluation criteria and create activity plans for the academic year or semester.

Students can view the planned activities and build their personal participation plan.

### Do

Activities are conducted and participation is recorded using attendance tools such as:

- QR scanning
- student ID verification
- batch attendance imports

### Check

Participation records are verified by responsible units. Academic advisors monitor student progress throughout the semester.

### Act

Evaluation councils review final results and approve official conduct scores.

---

## Core Features

### Activity Planning

Administrative units can create and manage extracurricular activities with configurable participation rules.

Features include:

- activity registration and approval workflow
- event scheduling
- location management
- participant eligibility configuration
- automated notifications

---

### Participation Tracking

The system supports multiple participation recording mechanisms:

- QR code attendance
- student ID scanning
- attendance list import
- evidence submission when required

These mechanisms reduce manual work and improve data accuracy.

---

### Score Evaluation

Activities contribute to a structured **conduct score framework**.

Capabilities include:

- category-based evaluation criteria
- maximum score thresholds
- automated score aggregation
- advisor monitoring dashboards

---

### Complaint Management

Students can submit requests to review or correct evaluation results.

The system supports:

- complaint submission with attachments
- administrative review workflow
- decision tracking

---

### Final Evaluation

At the end of the semester:

1. Students confirm their activity records
2. Faculty evaluation councils review results
3. Final conduct scores are approved and published

---

## System Roles

### System Administrator

Responsible for system configuration and platform management.

Responsibilities include:

- user management
- role permission configuration
- academic year setup
- system configuration

---

### Administrative Units

Departments responsible for organizing extracurricular activities.

Responsibilities include:

- activity planning
- participation recording
- result verification
- complaint handling

---

### Academic Advisors

Advisors monitor student participation and progress.

Responsibilities include:

- tracking activity participation
- identifying students at risk of failing evaluation requirements
- guiding students in activity planning

---

### Evaluation Councils

Faculty and institutional councils conduct final evaluation.

Responsibilities include:

- reviewing evaluation reports
- validating results
- approving final conduct scores

---

### Students

Students interact with the system to manage their extracurricular progress.

Students can:

- register for activities
- track participation status
- submit evidence
- confirm evaluation results
- submit complaints if necessary

---

## System Workflow

The platform follows a PDCA-based lifecycle:

Activity Planning
        ↓
Student Participation
        ↓
Participation Verification
        ↓
Advisor Monitoring
        ↓
Complaint Handling
        ↓
Council Evaluation
        ↓
Final Result Publication



---

## Documentation

This repository contains documentation related to the SAE system design and requirements.

Examples include:

- business requirement summaries
- system requirement specifications
- workflow documentation
- architecture notes

---

## Repository Structure
    sae-system
    │
    ├── README.md
    │
    ├── architecture
    │     system-overview.md
    │
    ├── workflows
    │     pdca-workflow.md
    │
    ├── docs
    │     requirements-summary.md
    │
    └── diagrams
        ![SAE System Architecture](./diagrams/system-architecture.png)

 ```mermaid info```
---

## Notes

All documentation in this repository has been sanitized to remove sensitive or organization-specific information. The content focuses on system design concepts and workflows relevant to software engineering and system architecture.
