# Changelog

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
