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

**Date:** 2026-02-19 (updated)
**Module transition:** M05 CLI → M06 KB

Current state (v1.5.4):
1. SOP, diagrams (BPMN + Mermaid), glossary, README, CHANGELOG — all consistent and validated.
2. 8 PowerSchool screenshots in `artifacts/screenshots/`.
3. `artifacts/examples/` is still empty.
4. Prompt log current through Entry 15.
5. `docs/source/SOP_v1.md` populated from `SOP.md` (readable Markdown format).
6. `docs/source/KB_Page.md` populated — 8 sections, all [TBD] items resolved except Secretary follow-up actions after notification. Step 8 Save and Step 9 explicit decision rule fixed (v1.5.1).
7. `docs/source/Quick_Reference.md` populated — 8-step checklist with inline if/then decision points, [REQUIRED] markers, Common Failure Points table with escalation column, and dedicated Escalation section.
8. `docs/source/Checklist.md` populated — 10-step procedural checklist with GitHub-flavored markdown checkboxes; format: action verb + object + success condition; decision logic preserved as inline if/then branches.
9. `glossary.md` — PowerSchool login URL added (v1.5.2).
10. `README.md` — "Start Here" section added above Folder Structure with role-based navigation table linking directly to all four docs/source/ files (v1.5.3).
11. `artifacts/examples/walkthrough-outline.md` — Narrated walkthrough outline with timestamps (v1.5.4).
12. PDFs in `docs/exports/` are still placeholders.

Next steps:
- Export finalized source files to PDF and replace placeholders in `docs/exports/`
- Commit and push all changes to GitHub
