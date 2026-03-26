# Change Log Table — Grade Finalization Process Package

**Version:** 1.0
**Published:** 2026-03-26
**DRI:** Jason Geanuracos, Process Documentation Lead
**Applies to:** All artifacts in the Grade Finalization Process Package (M06KB-process-package)

> This table is the governance-facing version summary for the process package. It consolidates all major versions from `CHANGELOG.md` into a structured format for review and audit purposes. For full detail on any version, see `CHANGELOG.md`.

---

| Version | Date | Author | Summary | Reason | Type |
|---------|------|--------|---------|--------|------|
| 1.0.0 | 2026-02-11 | Jason Geanuracos | Initial package creation — Mermaid flowchart, prompt log, glossary (roles and systems) | M05 CLI module deliverable; establish baseline process documentation | New Feature |
| 1.1.0 | 2026-02-13 | Jason Geanuracos | Regenerated BPMN and Mermaid rendered diagrams; expanded README with project overview and diagram regeneration instructions | Rendered diagrams needed for submission; README lacked navigation guidance | New Feature |
| 1.1.1 | 2026-02-15 | Jason Geanuracos | Added CLAUDE.md to repository with Git repository section | Persisting AI assistant context across sessions | New Feature |
| 1.2.0 | 2026-02-15 | Jason Geanuracos | Added 8 PowerSchool screenshots to `artifacts/screenshots/`; reworked README with folder navigation and source-of-truth table | Supporting evidence needed; README required structural improvement | New Feature |
| 1.3.0 | 2026-02-16 | Jason Geanuracos | Created `docs/` folder; added `SOP_v1.md` (human-readable Markdown SOP); added KB_Page.md and Quick_Reference.md stubs; added PDF export placeholders | M06 KB module deliverable; separate source from exports | New Feature |
| 1.4.0 | 2026-02-17 | Jason Geanuracos | Added `KB_Page.md` (8-section KB article) and `Quick_Reference.md` (1-page checklist with decision points and escalation table) | M06 KB deliverable — knowledge-base article and quick reference required | New Feature |
| 1.5.0 | 2026-02-18 | Jason Geanuracos | Added `Checklist.md` (10-step procedural checklist with GFM checkboxes and inline decision logic) | M06 KB deliverable — procedural checklist required | New Feature |
| 1.5.1 | 2026-02-18 | Jason Geanuracos | Fixed KB_Page.md Steps 8 and 9 — added save instruction and explicit decision rule to align with Checklist.md and Quick_Reference.md | Cross-artifact consistency gap identified during validation | Bug Fix |
| 1.5.2 | 2026-02-18 | Jason Geanuracos | Added PowerSchool login URL to glossary; updated README module label and docs/ folder tree | Consistency fix; README reflected outdated M05 label | Bug Fix |
| 1.5.3 | 2026-02-19 | Jason Geanuracos | Added "Start Here" section to README with role-based navigation table | Improved discoverability for teachers vs. administrators | Clarification |
| 1.5.4 | 2026-02-19 | Jason Geanuracos | Added `artifacts/examples/walkthrough-outline.md` (narrated walkthrough with timestamps) | Supporting artifact for narrated process walkthrough deliverable | New Feature |
| 1.6.0 | 2026-02-20 | Jason Geanuracos | Generated all PDF exports (`SOP_v1.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf`, `Checklist.pdf`); replaced placeholders | PDF exports required for submission; placeholders not sufficient | New Feature |
| 1.6.1 | 2026-02-20 | Jason Geanuracos | Editorial improvements to KB_Page.md — section renames, jargon reduction, link text cleanup | Publish-readiness review; terminology not accessible to all staff | Clarification |
| 1.6.2 | 2026-02-21 | Jason Geanuracos | KB_Page.md — added YAML front matter, Summary section, FAQ section, clickable screenshot links; regenerated PDF | Publish-readiness improvements; FAQ addresses common teacher questions | Clarification |
| 1.6.3 | 2026-02-21 | Jason Geanuracos | Quick_Reference.md — improved decision branch formatting, updated footer to full name and mailto link; regenerated PDF | Publish-readiness improvements; decision logic needed visual clarity | Clarification |
| 1.7.0 | 2026-02-22 | Jason Geanuracos | Created `M07-plan.md` and `analysis/` folder; added `workflow-critique-memo.md` identifying 6 pain points; started M07 prompt log | M07 workflow analysis module — critique memo required | New Feature |
| 1.7.1 | 2026-02-23 | Jason Geanuracos | Revised critique memo — cut to 5 pain points, corrected class-load figures, resolved secretary role [TBD]; updated all related artifacts; exported PDF | Review identified factual errors and unresolved role definition | Bug Fix |
| 1.7.2 | 2026-02-24 | Jason Geanuracos | Added `improvement-backlog-v1.md` (9-item OP backlog) and `top3-deep-dive.md` (5-Whys for OP-01, OP-02, OP-03); exported both as PDFs | M07 deliverable — improvement backlog and root-cause analysis required | New Feature |
| 1.7.3 | 2026-02-25 | Jason Geanuracos | OP renumbering — OP-08 (calendar anchor) → OP-09; new OP-08 added (locked weight template investigation); updated across 4 files | OP-02 deep dive surfaced new countermeasure that warranted its own backlog item | Optimization |
| 1.7.4 | 2026-02-25 | Jason Geanuracos | Backlog expanded with Description, Impact/Success Metric, and Status columns; YAML front matter added for landscape PDF layout; all three analysis PDFs regenerated | Course requirements specified additional backlog columns; table exceeded portrait width | Clarification |
| 1.7.5 | 2026-03-01 | Jason Geanuracos | Fixed "all six" → "all five" in critique memo Executive Summary; regenerated PDF | Drafting artifact from earlier 6-item version not caught in prior review | Bug Fix |
| 1.8.0 | 2026-03-03 | Jason Geanuracos | Created `M08-plan.md`, `measurement/` folder, `Q1-finalization-export.csv` (18-row mock dataset), and `measurement-plan.md` with Q1 baseline values; started M08 prompt log | M08 measurement module — measurement plan and mock dataset required | New Feature |
| 1.8.1 | 2026-03-05 | Jason Geanuracos | Added `baseline-dataset.xlsx` (4-sheet Power Query workbook) and `power-query-steps.md` (7-step documentation with M query); exported measurement plan PDF | M08 deliverable — Power Query workbook and step documentation required | New Feature |
| 1.8.2 | 2026-03-06 | Jason Geanuracos | Generated `power-query-steps.pdf`; created `A08/` submission package with clean-named copies of all M08 deliverables | Submission package required; PDF export for power-query-steps was missing | Bug Fix |
| 1.8.3 | 2026-03-06 | Jason Geanuracos | Added Data Collection Method and Baseline Interpretation sections to measurement plan; fixed typo and sort order errors; regenerated PDF and A08/ copies | User-authored interpretation content; proofread identified factual and formatting errors | Clarification |
| 1.9.0 | 2026-03-26 | Jason Geanuracos | Added `governance/` folder — governance plan, redaction & data handling plan, change log table, QA checklist; added governance headers to SOP_v1.md (v1.6), SOP_v1_annotated.md, and diagram source files; assembled A10/ submission package | M10 governance module — governance layer required on top of existing process package | Policy/Governance |

---

*For full detail on any version, including file-level changes, see `CHANGELOG.md` at the repository root.*
