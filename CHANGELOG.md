# Changelog

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
