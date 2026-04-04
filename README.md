# Pham Minh Lam — Project Portfolio

Documentation and writeups for the main projects I worked on at AQ Tech, linked from my CV as supporting evidence.

---

## Projects

| Project | Domain | My Role | Stack |
|---|---|---|---|
| [AQ EduSAE](./projects/sae/) | Student Activity & Conduct Scoring | Developer + Co-manage | .NET · React · SQL Server · IIS |
| [AQ EduEAQ](./projects/eaq/) | Accreditation Evidence Management | Developer + Co-manage | .NET 9 · React · SQL Server · IIS |

---

## Project Relationship

Both **EduSAE** and **EduEAQ** are built on top of the **AQnewWeb monorepo** (`C:\Users\lam\01work\AQnewWeb`), which contains shared infrastructure used across all AQ Tech applications:

```
AQnewWeb (monorepo — shared base)
├── packages/
│   ├── @aq-fe-framework     — shared React component framework
│   ├── @aq-fe/core-ui       — core UI component library
│   ├── eslint-config         — shared ESLint configs
│   └── typescript-config     — shared TypeScript configs
└── apps/
    ├── eaq  ← EAQ predecessor codebase (old version)
    ├── sae  ← SAE predecessor codebase (old version)
    ├── apm, asm, icm, ipm, lom, qmes, scm, srm, stm, svn, school...
    └── base-app  ← project template

Local project repos (next-gen versions):
├── projects/sae/  ← EduSAE next-gen
└── projects/eaq/ ← EduEAQ next-gen
```

---

## About Me

Software Engineer, Ho Chi Minh City · 2+ years at AQ Tech · B2 English (IELTS 6.5)

**Stack:** C# / .NET · React · TypeScript · Node.js · SQL Server · Azure DevOps

**Highlights:**
- Led full-stack delivery for 2 enterprise SaaS platforms used by Vietnamese universities
- Authored and implemented against 160+ page URDs and BRDs in Vietnamese
- Co-managed a team of ~17 intern developers across sprint planning, code review, and delivery
- Designed data models and API contracts for complex multi-entity workflows (score recording, accreditation cycles, evidence versioning)
- Built shared frontend component framework used across multiple applications

---

## Structure

```
portfolio/
├── README.md               ← this file
├── cv-highlights.md        ← CV bullets by role type (FE / BE / Fullstack)
└── projects/
    ├── sae/
    │   ├── README.md       ← full system overview + my contributions
    │   └── docs/           ← original BRD (Vietnamese)
    └── eaq/
        ├── README.md       ← full system overview + my contributions
        └── docs/           ← original URD (Vietnamese)
```

---

## How to Navigate

1. **For CV bullets** → see `cv-highlights.md`
2. **For full system understanding** → read `projects/sae/README.md` and `projects/eaq/README.md`
3. **For implementation proof** → browse the actual codebase at:
   - Next-gen projects: `C:\Users\lam\02project\...`
   - AQnewWeb monorepo: `C:\Users\lam\01work\AQnewWeb\`
   - Original SRS docs: `C:\Users\lam\01work\doc\`
