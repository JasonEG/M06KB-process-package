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

**Date:** 2026-02-23 (updated)
**Module transition:** M06 KB → M07 Workflow Critique

### Session Summary — 2026-02-23

**What we did today:**
- Reviewed and edited `analysis/workflow-critique-memo.md` section by section with user input.
- Cut pain points from 6 to 5 — removed Pain Point 5 (subjective grade correctness; teacher determines correctness).
- Updated Pain Point 2: corrected to 5-class load, 9-period day context, exactly 20 UI interactions.
- Updated Pain Point 3: clarified 10% exam is the only required weight constraint; 90% at teacher's discretion; removed system-side locking suggestion.
- Updated Pain Point 4: corrected system behavior — PowerSchool does prompt to save but does not auto-save; added explicit weight verification requirement before confirming save.
- Updated Pain Point 5 (formerly 6): resolved secretary [TBD] — secretary tracks which teachers have submitted grade finalization confirmation emails.
- Resolved secretary [TBD] across 7 files: `SOP.md`, `SOP_v1.md`, `KB_Page.md`, `glossary.md`, `process.mmd`, `process.bpmn`, `workflow-critique-memo.md`.
- Added OP code explanation (OP = optimization opportunity ID, assigned by priority not order) to `workflow-critique-memo.md` and `M07-plan.md`.
- Updated memo header: date to 2026-02-23, To: "Grading Process Improvement Review".
- Generated `analysis/workflow-critique-memo.pdf` via `md-to-pdf` (using local temp workaround for network drive speed — copy to temp, run md-to-pdf, copy PDF back).
- Updated `CHANGELOG.md` (v1.7.1), `CLAUDE.md`, and `prompt-log/week07-analysis-log.md` (Entry 23).

**What still needs to be done (M07):**
1. `analysis/improvement-backlog-v1.md` — 8-item prioritized backlog (OP-01 through OP-08) with owner, effort, metric, and priority.
2. `analysis/top3-deep-dive.md` — 5-Whys root-cause analysis for OP-01 (manual cycling), OP-02 (weight validation), OP-03 (email handoff); each ending with root cause, 2 countermeasures, 1 success metric, and key risks.
3. `docs/source/SOP_v1_annotated.md` — Copy of SOP_v1.md with ⚠️ pain-point callout blockquotes at relevant steps.
4. PDF exports of improvement-backlog-v1 and top3-deep-dive via `md-to-pdf` → `docs/exports/`.
5. `README.md` update to add `analysis/` to the folder structure tree.
6. Commit and push all remaining M07 changes to `origin/master`.

---

Current state (v1.7.1):
1. SOP, diagrams (BPMN + Mermaid), glossary, README, CHANGELOG — all consistent and validated.
2. 8 PowerSchool screenshots in `artifacts/screenshots/`.
3. `artifacts/examples/walkthrough-outline.md` — Narrated walkthrough outline with timestamps (v1.5.4).
4. Prompt log: Entries 1–21 in `week05-cli-log.md`; Entries 22–23 in `week07-analysis-log.md`.
5. `docs/source/SOP_v1.md` — human-readable SOP (v1.5).
6. `docs/source/KB_Page.md` — publish-readiness improvements applied (v1.6.2).
7. `docs/source/Quick_Reference.md` — publish-readiness improvements applied (v1.6.3).
8. `docs/source/Checklist.md` — 10-step procedural checklist with GFM checkboxes.
9. `docs/exports/` — All four PDFs in place: `SOP_v1.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf`, `Checklist.pdf`.
10. `M07-plan.md` — Module 07 execution plan (6 pain points, 8-item backlog, Top 3 deep-dive targets).
11. `analysis/workflow-critique-memo.md` — Evidence-based critique memo (5 pain points, OP-01 through OP-08, secretary role resolved).
12. `analysis/workflow-critique-memo.pdf` — PDF export of critique memo.

M07 work in progress (next steps):
- `analysis/improvement-backlog-v1.md` — 8-item prioritized backlog (not yet created).
- `analysis/top3-deep-dive.md` — 5-Whys deep dive for OP-01, OP-02, OP-03 (not yet created).
- `docs/source/SOP_v1_annotated.md` — Annotated SOP with pain-point callouts (not yet created).
- PDF exports of remaining analysis docs (not yet generated).
- README.md update to include `analysis/` folder tree (not yet done).

Deferred from M06:
- Secretary role resolved (2026-02-23) — updated across SOP.md, SOP_v1.md, KB_Page.md, glossary.md, process.mmd, process.bpmn, and workflow-critique-memo.md. Secretary tracks which teachers have submitted grade finalization confirmation emails for the grading period.
- YAML front matter in `KB_Page.md` renders visibly in PDF — gray-matter suppression deferred.
- Print layout / CSS styling for `Quick_Reference.md` — deferred.
