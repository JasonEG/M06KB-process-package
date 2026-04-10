# Changelog

## [2.3.0] — 2026-04-10

### Changed

- `capstone/process.bpmn` — Connector label visibility fixed: added explicit `BPMNLabel` bounds to all sequence flow edges so labels render off the connector lines rather than on top of them. Manual cleanup completed in bpmn.io by user.
- `capstone/process.pdf` — Regenerated from corrected BPMN; connector labels now fully readable.

---

## [2.2.0] — 2026-04-09

### Added

- `capstone/process.bpmn` — BPMN 2.0 diagram for In-Home Dog Boarding Intake and Care; two swimlanes (Dog Sitter, Dog Owner); XOR gateways at Steps 1, 3, and 6; Step 6 daily care loop with standardLoopCharacteristics; Step 7 escalation subprocess; two decline end events and one normal end event.
- `capstone/process.pdf` — PDF export of BPMN diagram via bpmn-to-image; 2800×600 pool with 160×90 task boxes and 54×54 gateways.

### Changed

- `capstone/SOP.md` (v1.1) — Step 3 decision callout updated: "Established repeat client" determination now explicitly noted as at dog sitter's discretion (G-02 resolution).

---

## [2.1.0] — 2026-04-07

### Added

- `capstone/discovery-notes.md` — Phase-by-phase analysis of Abbey's process outline; gap/decision table (G-01 through G-05); open questions for partner review; BPMN diagram notes; AI usage log.
- `capstone/SOP.md` (v1.1) — Full 9-step SOP for In-Home Dog Boarding Intake and Care; governance header (DRI: Abbey Cohen); decision callouts at Steps 1, 3, and 6; escalation trigger and severity tiers in Step 7; exceptions table (6 entries).

### Changed

- `prompt-log/week12-capstone-log.md` → `prompt-log/capstone-log.md` — Renamed to cover the full capstone arc (Weeks 12–15). Entry 40 added for 2026-04-07 session.
- `capstone/SOP.md` Step 6/7 — Clarified escalation model (Option A): Step 6 handles inline daily-loop resolutions only; explicit trigger line for Step 7 added; Step 7 reframed as true escalation path.

---

## [2.0.0] — 2026-04-05

### Added

- `capstone/` — New subfolder for Week 12 capstone deliverables (Track A: Consultant).
- `capstone/Sample Process Outline DOG BOARDING.pdf` — Abbey Cohen's dog boarding intake and care process outline; source document for all capstone deliverables.
- `capstone/sample-process-outline.md` — Format reference sent to Abbey (Prusa MK3S+ filament change process).
- `prompt-log/week12-capstone-log.md` — Prompt log for capstone work (Entry 39).

### Removed

- `capstone/project-brief.md` — Removed; superseded by Abbey's actual process outline.

---

## [1.9.1] — 2026-03-27

### Added

- `discussions/` — New subfolder for Canvas discussion post drafts.
- `discussions/week11-saas-vs-onprem.md` — Draft discussion post for Week 11 (SaaS vs. on-prem tradeoffs); hybrid architecture framing (PowerSchool/Meta Solutions = SaaS, SOP documentation = on-prem); includes peer response placeholder and revision notes.
- `prompt-log/week11-discussion-log.md` — Prompt log for Week 11 discussion work (Entry 38).

## [1.9.0] — 2026-03-26

### Added

- `M10-plan.md` — Module 10 governance execution plan (7 steps, submission checklist, pre-made key decisions).
- `governance/` — New subfolder for M10 governance deliverables.
- `governance/audit-notes.md` — Step 1 artifact audit findings: PII risk classifications for all 10 Markdown files and 8 screenshots.
- `governance/governance-plan.md` — DRI, RACI, semi-annual review cadence, 7-step change control workflow, 3-tier escalation table, and sunset/refresh date (2027-02-16).
- `governance/redaction-data-handling-plan.md` — Data classification tiers, redaction token rules, storage & access table, manual audit logging section, AI tool handling rules, and 18-artifact redaction evidence table.
- `governance/change-log-table.md` — Governance-facing version summary table (v1.0.0 → v1.9.0); columns: Version, Date, Author, Summary, Reason, Type.
- `governance/qa-checklist.md` — Reusable QA review template (7 sections, 46 checks): SOP Structure, Clarity & Completeness, Diagram Alignment, Redaction & Sensitivity, Link & Reference Validation, Version & Governance Metadata, Approval Sign-Off.
- `governance/*.pdf` — PDF exports for all four governance Markdown files.
- `A10/` — Submission package: governance_plan.pdf, redaction_data_handling_plan.pdf, change_log_table.pdf, qa_checklist.pdf, SOP_v1.pdf, SOP_v1_annotated.pdf, prompt_log.md.
- `prompt-log/week10-governance-log.md` — Prompt log for M10 (Entries 35–37).

### Changed

- `docs/source/SOP_v1.md` — Version bumped v1.5 → v1.6; governance block added (DRI, published date, next review date, change summary).
- `docs/source/SOP_v1_annotated.md` — Version bumped v1.5 → v1.6 (Annotated); governance block added.
- `diagrams/bpmn/process.bpmn` — Governance comment block added (DRI, version, published date, next review date, change summary).
- `diagrams/mermaid/process.mmd` — Governance comment lines added (DRI, version, published date, next review date, change summary).
- `docs/exports/SOP_v1.pdf` — Regenerated to reflect v1.6 governance header.
- `docs/exports/SOP_v1_annotated.pdf` — Regenerated to reflect v1.6 governance header.
- `README.md` — Added `M10-plan.md`, `governance/` folder tree, `A10/` folder tree; updated prompt-log tree (week09 and week10 entries); added Source of Truth entries for all governance artifacts.

## [1.8.3] — 2026-03-06

### Added

- `measurement/measurement-plan.md`: Added `Data Collection Method` section (primary source, per-metric collection notes, privacy and redaction plan).
- `measurement/measurement-plan.md`: Added `Baseline Interpretation` section — one narrative paragraph per metric (M-01 through M-05) explaining what each baseline number means, where variance comes from, and how it connects to M07 improvement opportunities.

### Fixed

- `measurement/measurement-plan.md`: Corrected typo "unfinalzied" → "unfinalized" in M-01 interpretation.
- `measurement/measurement-plan.md`: Sorted M-04 Slowest Teachers in descending order (T007, T017, T003).
- `measurement/measurement-plan.pdf`: Regenerated to reflect all additions and fixes.
- `A08/measurement_plan.md` and `A08/measurement_plan.pdf`: Updated to match latest source.

## [1.8.2] — 2026-03-06

### Added

- `measurement/power-query-steps.pdf` — PDF export of `measurement/power-query-steps.md`.
- `A08/` — Submission package folder containing clean-named copies of all M08 deliverables: `measurement_plan.pdf`, `measurement_plan.md`, `baseline_dataset.xlsx`, `power_query_steps.pdf`, `power_query_steps.md`, `prompt_log.md`, and `data/Q1-finalization-export.csv`.

## [1.8.1] — 2026-03-05

### Added

- `measurement/baseline-dataset.xlsx` — Power Query workbook with 4 sheets: Raw Data (18 rows × 9 columns from CSV), Cleaned Data (+ 3 calculated columns: DaysFromDeadline, OnTime, WeightErrorFlag), Summary Pivot (department aggregations + bar chart), Dashboard (5 KPI cells M-01 through M-05 with Red/Yellow/Green conditional formatting and OP code mapping notes).
- `measurement/power-query-steps.md` — Step-by-step Power Query documentation (7 steps: source connection, promote headers, set types, add DaysFromDeadline, add OnTime, add WeightErrorFlag, load to sheet); includes full M query block, column reference table, and metric derivation reference.
- `measurement/measurement-plan.pdf` — PDF export of `measurement/measurement-plan.md`.

### Changed

- `README.md`: Added `M08-plan.md` to folder structure; added `measurement/` folder tree; added Source of Truth entries for all five M08 measurement files; updated prompt-log entry to include `week08-measurement-log.md`.
- `prompt-log/week08-measurement-log.md`: Entry 29 added (this session — xlsx, power-query-steps, PDF, doc updates).

### Fixed

- `measurement/power-query-steps.md`: Added blank-handling note after Step 3 (Q1 CSV has no blanks; step not required but documented for future use). Corrected Step 6 "Used by" note — WeightErrorFlag is a filtering/visualization helper; M-02 metric uses `SUM(WeightErrors)` directly, not `SUM(WeightErrorFlag)`.

## [1.8.0] — 2026-03-03

### Added

- `M08-plan.md` — Module 08 execution plan: 5 metrics (M-01 through M-05) mapped to M07 OP codes, 9-column mock dataset spec, 4-sheet Power Query workbook layout, and 8-step execution order. Includes rationale notes for OP-06/OP-08 exclusion and CSV-before-measurement-plan ordering.
- `measurement/` — New subfolder for M08 measurement deliverables (parallel to `analysis/`).
- `measurement/data/Q1-finalization-export.csv` — 18-row mock dataset (one row per teacher); columns: TeacherID, Department, NumClasses, FinalizationDate, Deadline, WeightErrors, NotificationComplete, ReworkIncidents, AvgTimePerClass_min. Q1 deadline: 10/31/2025.
- `measurement/measurement-plan.md` — Metric definitions with Q1 baseline values computed from CSV, improvement targets, gap analysis, OP code mapping, measurement cadence, and OP-06/OP-08 exclusion rationale.
- `prompt-log/week08-measurement-log.md` — New prompt log for M08 (Entry 28+).

### Fixed

- `prompt-log/week07-analysis-log.md` — Entry 27 (2026-03-01 session) backfilled; had been referenced in CLAUDE.md but not written to the log file.

## [1.7.5] — 2026-03-01

### Fixed

- `analysis/workflow-critique-memo.md`: Corrected "all six" → "all five" in Executive Summary — the memo documents five pain points; "all six" was a drafting artifact from an earlier six-item draft that was not caught during the 2026-02-27 review.
- `analysis/workflow-critique-memo.pdf`: Regenerated to reflect fix.

## [1.7.4] — 2026-02-25

### Changed

- `analysis/improvement-backlog-v1.md`: Added `Description` column (what would change per item); renamed `Success Metric` → `Impact / Success Metric` with impact type prefix per entry (error reduction, time savings, handoff reliability, process completeness); added `Status` column (all items Backlog; OP-07 In Progress); added YAML front matter for landscape PDF layout (Letter, 15mm margin).
- `analysis/improvement-backlog-v1.pdf`: Regenerated in landscape orientation to accommodate 10-column table.
- `analysis/top3-deep-dive.pdf`: Regenerated (PDF had not been updated since last session due to shell issue).
- `analysis/workflow-critique-memo.pdf`: Regenerated to reflect OP renumbering and terminology updates from v1.7.3.

## [1.7.3] — 2026-02-25

### Changed

- `analysis/improvement-backlog-v1.md`: OP-08 (calendar anchor) renumbered to OP-09; new OP-08 added — "Investigate whether PowerSchool supports locked weight templates" (derived from top3-deep-dive OP-02 Countermeasure B). Backlog expanded from 8 to 9 items. Footer version updated to v1.7.2.
- `analysis/top3-deep-dive.md`: Key table range updated to OP-01 through OP-09; OP-02 Countermeasure B assigned OP-08 label; "Quarter/Semester" → "Quarter" in OP-03 email template; footer version updated to v1.7.2.
- `analysis/workflow-critique-memo.md`: OP-08 (calendar anchor) renumbered to OP-09 in body and summary table; "Quarter/Semester" → "Quarter" in OP-03 recommendation; footer version updated to v1.7.2.
- `M07-plan.md`: OP-08 (calendar anchor) renumbered to OP-09; backlog item count updated to 9.

## [1.7.2] — 2026-02-24

### Added

- `analysis/improvement-backlog-v1.md` — 9-item prioritized improvement backlog (OP-01 through OP-09) with category, evidence anchor, owner, effort, priority, and success metric.
- `analysis/improvement-backlog-v1.pdf` — PDF export of improvement backlog.
- `analysis/top3-deep-dive.md` — 5-Whys root-cause analysis for OP-01 (manual class cycling), OP-02 (weight validation), OP-03 (email handoff); each with root cause, two countermeasures, success metric, and key risks.
- `analysis/top3-deep-dive.pdf` — PDF export of top-3 deep dive.

## [1.7.1] — 2026-02-23

### Changed

- `analysis/workflow-critique-memo.md`: Editorial revisions based on user review.
  - Header: date updated to 2026-02-23; "To" field updated to "Grading Process Improvement Review".
  - Cut from 6 to 5 pain points — removed Pain Point 5 (subjective grade correctness; teacher determines correctness).
  - Pain Point 2: corrected to 5-class load, 9-period day context, exactly 20 UI interactions.
  - Pain Point 3: clarified 10% exam is the only required weight; 90% at teacher's discretion; removed system-side locking suggestion.
  - Pain Point 4: corrected system behavior (PowerSchool prompts to save but does not auto-save); added explicit weight verification requirement before confirming save.
  - Pain Point 5 (formerly 6): resolved secretary role — secretary tracks which teachers have submitted grade finalization confirmation emails for the grading period.
  - Added OP code explanation (OP = optimization opportunity ID, assigned by priority not pain point order).
- `M07-plan.md`: Added OP code explanation before improvement backlog table.
- `SOP.md`, `docs/source/SOP_v1.md`, `docs/source/KB_Page.md`, `glossary.md`: Secretary role [TBD] resolved — now tracks teacher completion.
- `diagrams/mermaid/process.mmd`, `diagrams/bpmn/process.bpmn`: Secretary [TBD] note/label updated to reflect tracking responsibility.

### Added

- `analysis/workflow-critique-memo.pdf` — PDF export of workflow critique memo (replaces .docx).

## [1.7.0] — 2026-02-22

### Added

- `M07-plan.md` — Module 07 execution plan: 6 identified pain points, 8-item improvement backlog, Top 3 deep-dive targets, step rewrite target (Step 5), and annotated SOP approach.
- `analysis/` — New subfolder for M07 workflow analysis deliverables.
- `analysis/workflow-critique-memo.md` — Evidence-based workflow critique memo identifying 6 pain points (Waiting, Overprocessing, Defect/Rework, Handoff), each anchored to SOP step numbers and existing artifacts. Includes summary recommendation table linking to OP-01 through OP-09.
- `prompt-log/week07-analysis-log.md` — New prompt log for M07 (Entry 22+).

## [1.6.3] — 2026-02-21

### Changed

- `docs/source/Quick_Reference.md`: Publish-readiness improvements — content and decision logic unchanged.
  - Decision branches in Steps 1, 4, 6, and 7 moved to their own indented lines starting with `→`, with outcomes in **bold**, for visual clarity.
  - Footer owner updated from username (`jgeanuracos`) to full name and mailto link (`Jason Geanuracos — jgeanuracos@clsdraiders.org`); date bumped to 2026-02-21.
- `docs/exports/Quick_Reference.pdf`: Regenerated from updated source using `md-to-pdf`.

## [1.6.2] — 2026-02-21

### Changed

- `docs/source/KB_Page.md`: Publish-readiness improvements — content and meaning preserved, no SOP alignment changes.
  - Added YAML front matter block: 7 tags (`PowerSchool`, `Grading`, `Grade Finalization`, `Quarter`, `Semester`, `Teacher`, `PowerTeacher Pro`) and `category: Academic Processes` for platform discoverability.
  - `## Summary`: Added plain-language intro sentence before bullet list describing what the process is and when it applies.
  - `## Document Info`: Owner and author fields updated from username (`jgeanuracos`) to full name and mailto link (`Jason Geanuracos — jgeanuracos@clsdraiders.org`).
  - Added `## Frequently Asked Questions` section (5 entries) between Troubleshooting and Related Documents: no-email trigger, all-classes requirement, quarter vs. semester difference, correcting grades after marking complete, and login/IT escalation.
  - Added clickable screenshot links below Steps 4, 5, 8, and 10, referencing images in `artifacts/screenshots/` (URL-encoded filenames).
- `docs/exports/KB_Page.pdf`: Regenerated from updated source using `md-to-pdf`.

## [1.6.1] — 2026-02-20

### Changed

- `docs/source/KB_Page.md`: Editorial improvements for clarity and skimmability — no meaning changed, SOP alignment preserved.
  - `## TL;DR` → `## Summary`; paragraph replaced with 4 scannable bullets.
  - `## Steps (Simplified)` → `## Steps`
  - `## Exceptions / Troubleshooting` → `## Troubleshooting`
  - `## Links / Resources` → `## Related Documents and Tools`
  - `## Owner + Last Updated` → `## Document Info`
  - Jargon: "grading window is open" → "grade finalization period has started"; "allocated as percentages or total points" → "split across other assignments or categories"; "grading-period drop-down" → "grading period menu"; "contact support" → "contact IT support" (×2).
  - Link text: removed filenames and technical acronyms ("Mermaid", "BPMN") from all link labels.
  - Last updated date bumped to 2026-02-20.
- `docs/exports/KB_Page.pdf`: Regenerated from updated source.

## [1.6.0] — 2026-02-20

### Added

- `docs/exports/Checklist.pdf` — PDF export of `docs/source/Checklist.md` (new; no placeholder existed previously).

### Changed

- `docs/exports/SOP_v1.pdf` — Replaced placeholder with generated PDF export of `docs/source/SOP_v1.md`.
- `docs/exports/KB_Page.pdf` — Replaced placeholder with generated PDF export of `docs/source/KB_Page.md`.
- `docs/exports/Quick_Reference.pdf` — Replaced placeholder with generated PDF export of `docs/source/Quick_Reference.md`.
- `README.md` Folder Structure: Added `Checklist.pdf` to the `docs/exports/` tree.
- `README.md` Source of Truth table: Added `docs/exports/Checklist.pdf` entry.

## [1.5.4] — 2026-02-19

### Added

- `artifacts/examples/walkthrough-outline.md` — Narrated walkthrough outline (1:45–2:00) with timestamps covering why grade finalization matters, the main steps, common failure points, and escalation resources.

## [1.5.3] — 2026-02-19

### Changed

- `README.md`: Added "Start Here" section above Folder Structure with a role-based navigation table linking directly to `KB_Page.md`, `Quick_Reference.md`, `Checklist.md`, and `SOP_v1.md`. Includes audience-specific guidance for teachers and administrators.

## [1.5.2] — 2026-02-18

### Changed

- `glossary.md` PowerSchool entry: Added login URL (`ps-co.metasolutions.net`) to match the URL already documented in `KB_Page.md` and `Quick_Reference.md`.
- `README.md`: Updated module label from "Module 05 — CLI" to "Module 06 — KB".
- `README.md` Folder Structure: Added full `docs/` tree (`source/` with `SOP_v1.md`, `KB_Page.md`, `Quick_Reference.md`, `Checklist.md`; `exports/` with three PDF placeholders).
- `README.md` Source of Truth table: Added entries for all four `docs/source/` files and `docs/exports/*.pdf`.

## [1.5.1] — 2026-02-18

### Fixed

- `docs/source/KB_Page.md` Step 8: Added "Save before exiting" after the Final Grade Status checkbox instruction — omission identified during cross-artifact validation against Checklist.md and Quick_Reference.md.
- `docs/source/KB_Page.md` Step 9: Replaced implicit "Repeat Steps 7–8 for all classes" with an explicit decision rule — "If all classes are finalized → proceed to Step 10. If not → return to Step 7." — matching the decision logic present in Checklist.md and Quick_Reference.md.

## [1.5.0] — 2026-02-18

### Added

- `docs/source/Checklist.md` — 10-step procedural checklist with GitHub-flavored markdown checkboxes. Each step follows the format: action verb + object + success condition. Decision logic from the SOP (Steps 1, 7, 9) preserved as inline if/then branches.

## [1.4.0] — 2026-02-17

### Added

- `docs/source/KB_Page.md` — Knowledge-base article with 8 sections (TL;DR, When to Use, Prerequisites, Roles, Steps (Simplified), Exceptions/Troubleshooting, Links/Resources, Owner + Last Updated). Populated from SOP v1.5. One remaining gap flagged as [TBD]: Secretary follow-up actions after notification.
- `docs/source/Quick_Reference.md` — 1-page quick reference with 8-step checklist, inline if/then decision points, `[REQUIRED]` markers on required checks (Steps 4, 5, 7), Common Failure Points table with escalation column, and a dedicated Escalation section.

### Changed

- `docs/source/KB_Page.md`: Owner (jgeanuracos), review cycle (January and May), PowerSchool login URL, and IT Help Desk link populated — all previously [TBD].

## [1.3.0] — 2026-02-16

### Added

- `docs/` folder structure with `source/` and `exports/` subdirectories for knowledge-base deliverables.
- `docs/source/SOP_v1.md` — human-readable Markdown SOP converted from the JSON-formatted `SOP.md`.
- `docs/source/KB_Page.md` and `docs/source/Quick_Reference.md` (empty, pending content).
- Placeholder PDFs in `docs/exports/` (`SOP_v1.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf`).

## [1.2.0] — 2026-02-15

### Added

- 8 PowerSchool screenshots added to `artifacts/screenshots/` (gradebook, weights, grade status, completion email, etc.).
- Reworked `README.md` with sections for project purpose, folder navigation, source-of-truth vs. generated files, step-by-step diagram regeneration, and versioning/change history.

## [1.1.1] — 2026-02-15

### Added

- `CLAUDE.md` moved into the repository with a new **Git Repository** section documenting that the repo root is `process-package/`.

## [1.1.0] — 2026-02-13

### Added

- Regenerated rendered diagrams (`diagrams/bpmn/process.png`, `diagrams/mermaid/process.svg`) from source files.
- Expanded `README.md` with project overview, repository structure, and diagram regeneration instructions.

## [1.0.0] — 2026-02-11

### Added

- Mermaid flowchart (`diagrams/mermaid/process.mmd`) generated from SOP.md, covering all 10 steps and 3 decision points.
- Prompt log entry documenting the flowchart generation task (`prompt-log/week05-cli-log.md`).
- Glossary entries for roles (Teacher, Secretary, Principal) and systems (PowerSchool, PowerTeacher Pro) referenced in the SOP (`glossary.md`).
