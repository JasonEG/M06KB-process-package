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

**Date:** 2026-02-21 (updated)
**Module transition:** M05 CLI → M06 KB

Current state (v1.6.3):
1. SOP, diagrams (BPMN + Mermaid), glossary, README, CHANGELOG — all consistent and validated.
2. 8 PowerSchool screenshots in `artifacts/screenshots/`.
3. `artifacts/examples/walkthrough-outline.md` — Narrated walkthrough outline with timestamps (v1.5.4).
4. Prompt log current through Entry 21.
5. `docs/source/SOP_v1.md` populated from `SOP.md` (readable Markdown format).
6. `docs/source/KB_Page.md` — publish-readiness improvements applied (v1.6.2): YAML front matter with tags/category, plain-language Summary intro sentence, owner contact updated to full name and email, FAQ section added (5 entries), clickable screenshot links added to Steps 4, 5, 8, and 10.
7. `docs/source/Quick_Reference.md` — publish-readiness improvements applied (v1.6.3): decision branches in Steps 1, 4, 6, 7 moved to indented `→` lines with bold outcomes; owner contact updated to full name and mailto link; date bumped to 2026-02-21.
8. `docs/source/Checklist.md` populated — 10-step procedural checklist with GitHub-flavored markdown checkboxes; format: action verb + object + success condition; decision logic preserved as inline if/then branches.
9. `glossary.md` — PowerSchool login URL added (v1.5.2).
10. `README.md` — "Start Here" section with role-based navigation table; folder structure and Source of Truth table include all four PDF exports (v1.6.0).
11. `docs/exports/` — All four PDFs generated and in place: `SOP_v1.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf`, `Checklist.pdf`. `KB_Page.pdf` regenerated after v1.6.2 edits; `Quick_Reference.pdf` regenerated after v1.6.3 edits.

Next steps:
- Secretary `[TBD]` row in `KB_Page.md` Roles table — follow-up actions after notification not yet defined.
- YAML front matter in `KB_Page.md` renders as a visible block in the PDF; consider a gray-matter config to suppress it from PDF output if needed.
- Print layout and color/icon styling for `Quick_Reference.md` — CSS stylesheet pass deferred.
