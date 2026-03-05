# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **process package** for Module 06 (Knowledge Base). It builds on the Module 05 (CLI) process package and is a documentation deliverable, not a software project — there is no source code, build system, or test suite.

## Working Directory

The working directory for this project is on the network drive:

```
\\COLUM-FILE\Faculty\jgeanuracos\Desktop\UC Teach\IT7039 SS\M06 KB\process-package\
```

## Repository Structure

All content lives under `process-package/`:

- **README.md** — Project overview
- **SOP.md** — Standard Operating Procedure for the CLI process
- **CHANGELOG.md** — Version history of process changes
- **glossary.md** — Domain-specific terminology
- **diagrams/** — Process visualizations
  - `bpmn/process.bpmn` + `process.png` — BPMN 2.0 process diagram
  - `mermaid/process.mmd` + `process.svg` — Mermaid flowchart
- **docs/** — Knowledge-base deliverables
  - `source/` — Markdown source files (`SOP_v1.md`, `KB_Page.md`, `Quick_Reference.md`, `Checklist.md`)
  - `exports/` — PDF exports of source files
- **artifacts/** — Supporting materials (`examples/`, `screenshots/`)
- **prompt-log/** — AI prompt interaction logs

## Origin

This process package was originally created for Module 05 (CLI) and copied here for Module 06 (KB). The M05 version remains at:

- **Local:** `C:\Users\jgeanuracos\Documents\M05CLI\process-package\`
- **GitHub:** `https://github.com/JasonEG/M05CLI-process-package.git` (branch `master`)

## Git Repository

- **Remote:** `https://github.com/JasonEG/M06KB-process-package.git`
- **Branch:** `master`

## Working in This Project

- All documents are Markdown. Edits should preserve existing heading structure.
- Diagrams exist in both source format (`.mmd`, `.bpmn`) and rendered format (`.svg`, `.png`). When updating a diagram, edit the source file; the rendered file should be regenerated.
- The `artifacts/examples/` and `artifacts/screenshots/` directories are for supporting evidence referenced by the SOP or README.
- The prompt log tracks AI-assisted interactions during development of this process package.
- The `validation-log.md` records cross-artifact consistency checks. When validating, append a new entry there.

## Where We Left Off

**Date:** 2026-03-05 (updated)
**Module:** M08 — Measurement & Baseline Dataset ✅ COMPLETE

### ⚠️ START HERE NEXT SESSION

**M08 is fully complete and committed. All deliverables done. Ready for M09.**

M08 deliverables (all done):
- ✅ `M08-plan.md` — execution plan
- ✅ `measurement/data/Q1-finalization-export.csv` — 18-row mock dataset
- ✅ `measurement/measurement-plan.md` — metric definitions + Q1 baseline values
- ✅ `measurement/baseline-dataset.xlsx` — 4-sheet Power Query workbook (Raw, Cleaned, Pivot, Dashboard)
- ✅ `measurement/power-query-steps.md` — Power Query step documentation (reviewed and fixed)
- ✅ `measurement/measurement-plan.pdf` — PDF export
- ✅ `README.md` updated (measurement/ tree + Source of Truth entries)
- ✅ `CHANGELOG.md` updated (v1.8.1)
- ✅ `prompt-log/week08-measurement-log.md` updated (Entry 29)
- ✅ Committed and pushed to `origin/master`

---

### Session Summary — 2026-03-05

**What we did today:**
- Resumed M08 at Step 4. Reviewed `measurement-plan.md` and CSV — no issues found.
- Created `measurement/baseline-dataset.xlsx` via Python/openpyxl script — 4 sheets: Raw Data, Cleaned Data (3 calculated columns), Summary Pivot (dept aggregations + bar chart), Dashboard (5 KPIs with conditional formatting).
- Ran programmatic verification of xlsx — all values, calculated columns, and KPI statuses confirmed accurate.
- Created `measurement/power-query-steps.md` — 7 PQ steps with M query code, column reference, metric derivation table.
- Cross-referenced PQ steps against M08 plan and measurement plan — found and fixed 2 issues: missing blank-handling note, misleading WeightErrorFlag "Used by" attribution.
- Exported `measurement/measurement-plan.pdf` (md-to-pdf ran directly on network drive — no temp workaround needed).
- Updated README.md, CHANGELOG.md (v1.8.1), prompt log (Entry 29), and CLAUDE.md.
- Committed and pushed to `origin/master`.

---

### Session Summary — 2026-03-03

**What we did today:**
- Read CLAUDE.md and M07-plan.md for context; confirmed M07 fully closed at v1.7.5.
- Created `M08-plan.md` — metrics, dataset spec, workbook layout, execution order.
- Reviewed M08-plan and fixed three issues: DaysFromDeadline duplication, "Baseline Target" label ambiguity, OP-06/OP-08 silence.
- Revised execution order: CSV before measurement plan (so baseline values come from real data).
- Created `measurement/data/Q1-finalization-export.csv` (18 rows, Q1 deadline 10/31/2025).
- Created `measurement/measurement-plan.md` with Q1 baseline values computed from CSV.
- Backfilled Entry 27 in `week07-analysis-log.md` (had been referenced in CLAUDE.md but never written).
- Created `prompt-log/week08-measurement-log.md` (Entry 28).
- Updated `CHANGELOG.md` (v1.8.0) and `CLAUDE.md`.
- Session paused — PDF export, xlsx, power-query-steps.md, README, and commit deferred to next session.

---

### Session Summary — 2026-03-01

**What we did today:**
- Ran final review pass over all four M07 deliverables: `workflow-critique-memo.md`, `improvement-backlog-v1.md`, `top3-deep-dive.md`, `docs/source/SOP_v1_annotated.md`.
- Confirmed all PDF exports present (3 in `analysis/`, 5 in `docs/exports/`).
- Cross-checked OP-01 through OP-09 codes, priorities, statuses, and cross-document references — all consistent.
- Found one error in `workflow-critique-memo.md` Executive Summary: "all six" should be "all five" — drafting artifact from when the memo had 6 pain points, not caught in the 2026-02-27 review.
- Fixed "all six" → "all five"; regenerated `workflow-critique-memo.pdf`.
- Updated CHANGELOG (v1.7.5), prompt log (Entry 27), and CLAUDE.md.

---

### Session Summary — 2026-02-27

**What we did today:**
- Reviewed all three M07 analysis documents section by section: `workflow-critique-memo.md`, `improvement-backlog-v1.md`, `top3-deep-dive.md`.
- No changes to memo or deep dive — both accepted as-is.
- Added OP-## Key table to `improvement-backlog-v1.md` (defines "Optimization Opportunity"; consistent with `top3-deep-dive.md` format).
- Regenerated `improvement-backlog-v1.pdf` using local temp workaround.
- Committed and pushed to `origin/master` (commit `fcbc95e`).
- Updated prompt log (Entry 26) and CLAUDE.md.

---

### Session Summary — 2026-02-26

**What we did today:**
- Reviewed prompt log (`week07-analysis-log.md`) — confirmed current through Entry 25; no missing entries.
- Created `docs/source/SOP_v1_annotated.md` — annotated copy of SOP v1.5 with 9 OP-code blockquote callouts at Steps 1, 5, 6, 7, and 10; procedural content unchanged. Includes new Section 8 annotation summary table.
- Exported `docs/exports/SOP_v1_annotated.pdf` via md-to-pdf local temp workaround.
- Reviewed annotated SOP — confirmed all callouts match backlog OP codes and step anchors.
- Updated `README.md` — added `analysis/` folder tree, `M07-plan.md`, `SOP_v1_annotated.md/.pdf`, `week07-analysis-log.md`; expanded Source of Truth table with all new artifacts.
- Committed and pushed to `origin/master` (commit `f129928`).

---

### Session Summary — 2026-02-25

**What we did today:**
- Regenerated `analysis/top3-deep-dive.pdf` (shell had been broken in prior session).
- Reviewed `analysis/top3-deep-dive.md` — resolved all open questions:
  - OP-01: "Twenty sequential UI interactions" confirmed accurate (4 steps × 5 classes).
  - OP-02 Countermeasure B assigned label OP-08; old OP-08 (calendar anchor) renumbered OP-09.
  - OP-03: Grading period terminology locked as "Quarter".
  - Footers updated to v1.7.2 across all three analysis documents.
- Assessed and executed full OP renumbering across 7 files (CHANGELOG v1.7.3).
- Reviewed `analysis/improvement-backlog-v1.md` against course required fields — identified and added: Description column, Impact / Success Metric (renamed with impact type prefix), Status column. Backlog is now 9 items (OP-01 through OP-09).
- Added YAML front matter to `improvement-backlog-v1.md` for landscape PDF orientation (table was cut off in portrait).
- Regenerated all three analysis PDFs; resolved file-lock error on backlog PDF.
- Updated CHANGELOG (v1.7.3, v1.7.4), prompt log (Entry 25), and CLAUDE.md.

---

Current state (v1.7.4 + 2026-02-26 additions):
1. SOP, diagrams (BPMN + Mermaid), glossary, README, CHANGELOG — all consistent and validated.
2. 8 PowerSchool screenshots in `artifacts/screenshots/`.
3. `artifacts/examples/walkthrough-outline.md` — Narrated walkthrough outline with timestamps (v1.5.4).
4. Prompt log: Entries 1–21 in `week05-cli-log.md`; Entries 22–26 in `week07-analysis-log.md`.
5. `docs/source/SOP_v1.md` — human-readable SOP (v1.5).
6. `docs/source/SOP_v1_annotated.md` — annotated SOP with OP-01 through OP-09 callouts. ✅ Created and reviewed.
7. `docs/source/KB_Page.md` — publish-readiness improvements applied (v1.6.2).
8. `docs/source/Quick_Reference.md` — publish-readiness improvements applied (v1.6.3).
9. `docs/source/Checklist.md` — 10-step procedural checklist with GFM checkboxes.
10. `docs/exports/` — Five PDFs in place: `SOP_v1.pdf`, `SOP_v1_annotated.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf`, `Checklist.pdf`.
11. `M07-plan.md` — Module 07 execution plan (6 pain points, 9-item backlog, Top 3 deep-dive targets).
12. `analysis/workflow-critique-memo.md` + `.pdf` — Evidence-based critique memo (5 pain points, OP-01 through OP-09, secretary role resolved). ✅ Reviewed.
13. `analysis/improvement-backlog-v1.md` + `.pdf` — 9-item prioritized improvement backlog (landscape PDF); Key table added defining OP-##. ✅ Reviewed.
14. `analysis/top3-deep-dive.md` + `.pdf` — 5-Whys deep dive for OP-01, OP-02, OP-03; all open questions resolved. ✅ Reviewed.
15. `README.md` — updated to include `analysis/` folder tree and all new artifacts. ✅ Done.
16. All M07 changes committed and pushed to `origin/master` (commit `fcbc95e`). ✅ Done.

Deferred from M06:
- YAML front matter in `KB_Page.md` renders visibly in PDF — gray-matter suppression deferred.
- Print layout / CSS styling for `Quick_Reference.md` — deferred.
