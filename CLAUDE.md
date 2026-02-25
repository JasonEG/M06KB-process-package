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

**Date:** 2026-02-25 (updated)
**Module transition:** M06 KB → M07 Workflow Critique

### ⚠️ START HERE NEXT SESSION

1. Create `docs/source/SOP_v1_annotated.md` — copy of `SOP_v1.md` with `> ⚠️ **Pain Point [OP-XX]:**` blockquotes inserted after relevant steps (OP-01 through OP-05 and OP-09; procedural content unchanged).
2. Export `SOP_v1_annotated.md` → `docs/exports/SOP_v1_annotated.pdf` using local temp workaround.
3. Update `README.md` to add `analysis/` folder to the folder structure tree.
4. Commit and push all M07 changes to `origin/master`.

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

Current state (v1.7.4):
1. SOP, diagrams (BPMN + Mermaid), glossary, README, CHANGELOG — all consistent and validated.
2. 8 PowerSchool screenshots in `artifacts/screenshots/`.
3. `artifacts/examples/walkthrough-outline.md` — Narrated walkthrough outline with timestamps (v1.5.4).
4. Prompt log: Entries 1–21 in `week05-cli-log.md`; Entries 22–25 in `week07-analysis-log.md`.
5. `docs/source/SOP_v1.md` — human-readable SOP (v1.5).
6. `docs/source/KB_Page.md` — publish-readiness improvements applied (v1.6.2).
7. `docs/source/Quick_Reference.md` — publish-readiness improvements applied (v1.6.3).
8. `docs/source/Checklist.md` — 10-step procedural checklist with GFM checkboxes.
9. `docs/exports/` — All four PDFs in place: `SOP_v1.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf`, `Checklist.pdf`.
10. `M07-plan.md` — Module 07 execution plan (6 pain points, 9-item backlog, Top 3 deep-dive targets).
11. `analysis/workflow-critique-memo.md` + `.pdf` — Evidence-based critique memo (5 pain points, OP-01 through OP-09, secretary role resolved). ✅ Reviewed.
12. `analysis/improvement-backlog-v1.md` + `.pdf` — 9-item prioritized improvement backlog (landscape PDF); Description, Impact, and Status columns added. ✅ Reviewed.
13. `analysis/top3-deep-dive.md` + `.pdf` — 5-Whys deep dive for OP-01, OP-02, OP-03; all open questions resolved. ✅ Reviewed.

M07 work remaining:
- `docs/source/SOP_v1_annotated.md` — Annotated SOP with pain-point callouts (not yet created).
- PDF export of annotated SOP (not yet generated).
- README.md update to include `analysis/` folder tree (not yet done).
- Commit and push to `origin/master` (not yet done).

Deferred from M06:
- YAML front matter in `KB_Page.md` renders visibly in PDF — gray-matter suppression deferred.
- Print layout / CSS styling for `Quick_Reference.md` — deferred.
