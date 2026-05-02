---
title: "UI/UX & Mermaid Diagram Inventory"
description: "Central summary of all UI/UX specification files, mermaid diagram files, templates, and project typologies across the docs-paperclip repository."
author: "PaperclipForge AI — Shared Services"
date: "2026-05-02"
status: "📋 Placeholder — Complete"
---

# UI/UX & Mermaid Diagram Inventory

**Location:** `docs-paperclip/reports/ui-ux-mermaid-diagram-inventory.md`

**Subfolder Organization:**
- UI/UX reports → `docs-paperclip/reports/ui-ux/`
- Mermaid diagram reports → `docs-paperclip/reports/mermaid/`

---

## 1. UI/UX Specification Files

These are the primary UI/UX specification documents across disciplines. Each contains mermaid diagrams and defines the user interface and user experience for that discipline's workflows.

| # | Discipline | File Path | Mermaid Diagrams | Associated Project |
|---|-----------|-----------|-----------------|-------------------|
| 1 | Engineering (Shared) | `docs-paperclip/disciplines-shared/engineering/UI-UX-SPECIFICATION.md` | ✅ Yes | — |
| 2 | Measurement (Shared) | `docs-paperclip/disciplines-shared/measurement/UI-UX-SPECIFICATION.md` | ✅ Yes | — |
| 3 | Electrical Engineering | `docs-paperclip/disciplines/00860-electrical-engineering/UI-UX-SPECIFICATION.md` | ✅ Yes | — |
| 4 | Procurement | `docs-paperclip/disciplines/01900-procurement/UI-UX-SPECIFICATION.md` | ✅ Yes | PROC-ORDER |
| 5 | Safety | `docs-paperclip/disciplines/02400-safety/UI-UX-SPECIFICATION.md` | ✅ Yes | — |

**Related report:** `docs-paperclip/reports/ui-ux/2026-04-29-ui-ux-specification-projects-report.md`

---

## 2. UI/UX-Related Issue Files

Issues that specifically address UI/UX concerns, linked to their parent projects.

| # | Issue | File Path | Parent Project |
|----|-------|-----------|---------------|
| 1 | PROC-001-ui-modal-e2e-flow | `docs-paperclip/disciplines/01900-procurement/projects/PROC-ORDER/issues/PROC-001-ui-modal-e2e-flow.md` | PROC-ORDER |
| 2 | PROC-043-ux-copy-review | `docs-paperclip/disciplines/01900-procurement/projects/PROC-ORDER/issues/PROC-043-ux-copy-review.md` | PROC-ORDER |
| 3 | PROC-VOICE-001-ui-components-development | `docs-paperclip/disciplines/01900-procurement/projects/PROC-VOICE/issues/PROC-VOICE-001-ui-components-development.md` | PROC-VOICE |
| 4 | MOBILE-006-ui-ux-testing | `docs-paperclip/disciplines-shared/testing/projects/MOBILE-TEST/issues/MOBILE-006-ui-ux-testing.md` | MOBILE-TEST |
| 5 | QSDWG-001-ui-measurement-workflow | `docs-paperclip/disciplines/02025-quantity-surveying/projects/PROC-001/QS-DWG-SWARM-ENTERPRISE/issues/QSDWG-001-ui-measurement-workflow.md` | QS-DWG-SWARM-ENTERPRISE |
| 6 | MEASURE-001-shared-ui-architecture | `docs-paperclip/disciplines-shared/measurement/projects/MEASURE-COMM/desktop/issues/MEASURE-001-shared-ui-architecture.md` | MEASURE-COMM |
| 7 | MEASURE-001-ui-review-coordination | `docs-paperclip/disciplines-shared/measurement/projects/MEASURE-COMM/desktop/issues/MEASURE-001-ui-review-coordination.md` | MEASURE-COMM |
| 8 | MEASURE-TENDER-004-ui-dashboard | `docs-paperclip/disciplines-shared/measurement/projects/MEASURE-TENDER/desktop/issues/MEASURE-TENDER-004-ui-dashboard.md` | MEASURE-TENDER |
| 9 | PROD-008-ui-settings-testing | `docs-paperclip/disciplines-shared/testing/projects/PROD-TEST/desktop/issues/PROD-008-ui-settings-testing.md` | PROD-TEST |
| 10 | SAFETY-*-005-ux-accessibility (×8) | `docs-paperclip/disciplines/02400-safety/projects/SAFETY-*/mobile/issues/SAFETY-*-005-ux-accessibility.md` | Various Safety projects |
| 11 | ARCH-001-building-specification | `docs-paperclip/disciplines/00825-architectural/projects/ARCHITECTURAL-WORKFLOW/desktop/issues/ARCH-001-building-specification-development-workflow.md` | ARCHITECTURAL-WORKFLOW |
| 12 | SOLAR-004-building-integration | `docs-paperclip/disciplines-sector-specific-details/00001-solar-installations/projects/SOLAR-INSTALL/desktop/issues/SOLAR-004-building-integration-architectural-coordination.md` | SOLAR-INSTALL |
| 13 | DESKTOP-SEC-004-equipment-controls | `docs-paperclip/disciplines/02500-security/projects/SECURITY-ASSET/desktop/issues/DESKTOP-SEC-004-equipment-immobilization-controls.md` | SECURITY-ASSET |

---

## 3. UI/UX Shared Guidelines Directories

| # | Company | Path |
|---|---------|------|
| 1 | Shared (all) | `docs-paperclip/companies/shared/ui-ux-guidelines/` |
| 2 | DevForge AI | `docs-paperclip/companies/devforge-ai/shared/ui-ux-guidelines/` |
| 3 | DomainForge AI | `docs-paperclip/companies/domainforge-ai/shared/ui-ux-guidelines/` |
| 4 | PaperclipForge AI | `docs-paperclip/companies/paperclipforge-ai/shared/ui-ux-guidelines/` |
| 5 | PromptForge AI | `docs-paperclip/companies/promptforge-ai/shared/ui-ux-guidelines/` |
| 6 | QualityForge AI | `docs-paperclip/companies/qualityforge-ai/shared/ui-ux-guidelines/` |
| 7 | Loopy AI | `docs-paperclip/companies/loopy-ai/shared/ui-ux-guidelines/` |
| 8 | InfraForge AI | `docs-paperclip/companies/infraforge-ai/shared/ui-ux-guidelines/` |
| 9 | MobileForge AI | `docs-paperclip/companies/mobileforge-ai/shared/ui-ux-guidelines/` |

---

## 4. Spec Files

| # | File | Description |
|---|------|-------------|
| 1 | `docs-paperclip/specs/agent-config-ui.md` | Agent configuration UI specification (286 lines) |
| 2 | `docs-paperclip/specs/cliphub-plan.md` | Cliphub plan |

---

## 5. Mermaid Diagram Files

### 5.1 Mermaid Template System (Core)

These are the central mermaid template system files — parameterized templates, renderer, and procedure.

| # | File | Type | Lines | Description |
|---|------|------|-------|-------------|
| 1 | `docs-paperclip/templates/mermaid/procurement-lifecycle.yaml` | YAML Template | 64 | Parameterized procurement lifecycle mermaid template |
| 2 | `docs-paperclip/templates/mermaid/registry.yaml` | YAML Registry | 87 | Mermaid template registry — maps templates to disciplines |
| 3 | `docs-paperclip/scripts/render-mermaid.js` | JS Renderer | 283 | CLI renderer: renders parameterized templates with discipline values |
| 4 | `docs-paperclip/procedures/workflows/mermaid-diagram-template-system-procedure.md` | Procedure | 464 | Complete procedure for creating, rendering, versioning templates |
| 5 | `docs-paperclip/companies/paperclipforge-ai/skills/mermaid-diagram-templates/SKILL.md` | Skill | 136 | Shared skill for mermaid diagram templates |

### 5.2 Files Containing Inline Mermaid Diagrams (` ```mermaid `)

| # | File | Discipline/Area |
|---|------|----------------|
| 1 | `docs-paperclip/companies/mobileforge-ai/MOBILE-ARCHITECTURE.md` | Mobile Architecture |
| 2 | `docs-paperclip/companies/paperclipforge-ai/shared/brainstorming/SKILL.md` | Brainstorming Skill |
| 3 | `docs-paperclip/companies/paperclipforge-ai/shared/build-error-fix/SKILL.md` | Build Error Fix Skill |
| 4 | `docs-paperclip/companies/shared/brainstorming/SKILL.md` | Brainstorming Skill (Shared) |
| 5 | `docs-paperclip/companies/shared/build-error-fix/SKILL.md` | Build Error Fix Skill (Shared) |
| 6 | `docs-paperclip/disciplines-non/00105-travel-arrangements/DISCIPLINE-WORKFLOWS-CATALOG.md` | Travel Arrangements |
| 7 | `docs-paperclip/disciplines-non/00106-timesheets/DISCIPLINE-WORKFLOWS-CATALOG.md` | Timesheets |
| 8 | `docs-paperclip/disciplines-shared/engineering/DISCIPLINE-WORKFLOWS-CATALOG.md` | Engineering |
| 9 | `docs-paperclip/disciplines-shared/engineering/UI-UX-SPECIFICATION.md` | Engineering UI/UX |
| 10 | `docs-paperclip/disciplines-shared/engineering/plans/2026-04-20-cross-discipline-engineering-platform-implementation-plan.md` | Engineering Platform Plan |
| 11 | `docs-paperclip/disciplines-shared/measurement/DISCIPLINE-WORKFLOWS-CATALOG.md` | Measurement |
| 12 | `docs-paperclip/disciplines-shared/measurement/UI-UX-SPECIFICATION.md` | Measurement UI/UX |
| 13 | `docs-paperclip/disciplines/00825-architectural/00825-architectural-workflows-list.md` | Architectural |
| 14 | `docs-paperclip/disciplines/00860-electrical-engineering/UI-UX-SPECIFICATION.md` | Electrical Engineering UI/UX |
| 15 | `docs-paperclip/disciplines/00880-board-of-directors/00880-board-of-directors-workflow-conversion-procedure.md` | Board of Directors |
| 16 | `docs-paperclip/disciplines/00884-engineering-director/00884-engineering-director-workflow-conversion-procedure.md` | Engineering Director |
| 17 | `docs-paperclip/disciplines/01900-procurement/UI-UX-SPECIFICATION.md` | Procurement UI/UX |
| 18 | `docs-paperclip/disciplines/02025-quantity-surveying/projects/PROC-001/QS-DWG-SWARM-ENTERPRISE/workflow-diagram.md` | Quantity Surveying |
| 19 | `docs-paperclip/disciplines/02400-safety/UI-UX-SPECIFICATION.md` | Safety UI/UX |
| 20 | `docs-paperclip/procedures/workflows/mermaid-diagram-template-system-procedure.md` | Mermaid Template Procedure |
| 21 | `docs-paperclip/procedures/workflows/universal-workflow-implementation-audit-trail.md` | Universal Workflow Audit |

### 5.3 Files with Flowchart/Diagram Keywords (Additional)

These files contain diagram-related keywords (flowchart, sequenceDiagram, classDiagram, stateDiagram, erDiagram, gantt, pie, journey, mindmap) — 100+ files across:
- `docs-paperclip/companies/construct-ai/` — commercial, civil, electrical, safety skills
- `docs-paperclip/companies/contentforge-ai/` — company skills
- `docs-paperclip/companies/qualityforge-ai/` — testing skills
- `docs-paperclip/companies/paperclipforge-ai/` — shared skills
- `docs-paperclip/disciplines/` — workflow catalogs, procedures
- `docs-paperclip/hermes_agent/` — agent documentation and skills
- `docs-paperclip/plans/`, `docs-paperclip/procedures/`, `docs-paperclip/workflows/`

---

## 6. Project Typologies

### 6.1 Knowledge Disciplines with Project Typologies

The `docs-paperclip/knowledge-disciplines/` directory contains 22 discipline directories, each with a `project-typologies/` subdirectory. Each discipline has per-typology files for 9 project types plus an index and README.

| # | Discipline Code | Discipline Name | Typology Files | Discipline Knowledge File |
|---|----------------|----------------|---------------|--------------------------|
| 1 | 00400 | Contracts | 11 files | `0010_EPC-CONTRACTS.MD` |
| 2 | 00425 | Contracts — Pre-Award | 11 files | `0010_TENDER-PROCUREMENT.MD` |
| 3 | 00435 | Contracts — Post-Award | 11 files | `0010_CONTRACT-ADMIN.MD` |
| 4 | 00800 | Design | 11 files | `0010_ARCHITECTURAL-DESIGN.MD` |
| 5 | 00825 | Architectural | 11 files | `0010_ARCHITECTURAL-SERVICES.MD` |
| 6 | 00835 | Chemical Engineering | 11 files | `0010_PROCESS-PLANT.MD` |
| 7 | 00850 | Civil Engineering | 11 files | `0010_CIVIL-WORKS.MD` |
| 8 | 00850 | Landscaping | 11 files | `0010_LANDSCAPING.MD` |
| 9 | 00855 | Geotechnical Engineering | 11 files | `0010_GEOTECHNICAL.MD` |
| 10 | 00860 | Electrical Engineering | 11 files | `0010_POWER-SYSTEMS.MD` |
| 11 | 00870 | Mechanical Engineering | 11 files | `0010_MECHANICAL.MD` |
| 12 | 00871 | Process Engineering | 11 files | `0010_PROCESS-DESIGN.MD` |
| 13 | 00872 | Structural | 11 files | `0010_STRUCTURAL.MD` |
| 14 | 01000 | Environmental | 11 files | `0010_ENVIRONMENTAL.MD` |
| 15 | 01700 | Logistics | 11 files | `0010_LOGISTICS.MD` |
| 16 | 01900 | Procurement | 11 files | — |
| 17 | 02025 | Quantity Surveying | 11 files | `0010_QS-SERVICES.MD` |
| 18 | 02050 | Information Technology | 11 files | `0010_ENTERPRISE-IT.MD`, `0020_DATA-CENTER.MD` |
| 19 | 02400 | Safety | 11 files | `0010_CONSTRUCTION-SAFETY.MD`, `0020_EMERGENCY-RESPONSE.MD`, `0030_HEALTH-AND-HYGIENE.MD` |
| 20 | 02500 | Security | 11 files | `0010_SECURITY-SYSTEMS.MD` |
| 21 | 03000 | Sundry | 11 files | `0010_SUNDRY.MD` |

### 6.2 Shared Project Typologies (9 Types)

Each discipline's `project-typologies/` directory contains the same 9 project type files:

| Code | Project Type |
|------|-------------|
| 0010 | Oil & Gas |
| 0020 | Mining |
| 0030 | Residential |
| 0040 | Commercial |
| 0045 | Mixed-Use |
| 0050 | Infrastructure |
| 0055 | Industrial |
| 0060 | Institutional |
| 0070 | Energy & Power |

---

## 7. Summary Statistics

| Category | Count |
|----------|-------|
| UI/UX Specification files | 5 |
| UI/UX-related issues | 13+ |
| UI/UX shared guidelines directories | 9 |
| Spec files | 2 |
| Mermaid template YAML files | 2 |
| Mermaid renderer scripts | 1 |
| Mermaid template procedure/skill files | 2 |
| Files with inline ` ```mermaid ` blocks | 21 |
| Files with diagram keywords | 100+ |
| Disciplines with project typologies | 22 |
| Total project typology files | ~242 (22 disciplines × 11 files) |