---
pdf_options:
  format: Letter
  landscape: true
  margin: 15mm
---

# Improvement Backlog v1

**Process:** Grade Finalization in PowerSchool
**Version:** 1.0
**Date:** 2026-02-24
**Based on:** Workflow Critique Memo (2026-02-23); SOP v1.5; KB Article v1.6.2; Quick Reference v1.6.3

---

## Overview

This backlog catalogs all optimization opportunities identified during the M07 workflow diagnostic. Each item is assigned an **OP code** — a unique, stable identifier used consistently across the critique memo, this backlog, and the top-3 deep-dive analysis. Codes are assigned by priority grouping, not by the order in which pain points were discovered.

Items are ranked by a combination of impact (defect risk, teacher effort, handoff reliability) and estimated effort (S = Small, M = Medium). High-priority, small-effort items are sequenced first.

---

## Backlog Table

| ID | Opportunity | Description | Category | Evidence Anchor | Owner | Effort | Priority | Impact / Success Metric | Status |
|----|-------------|-------------|----------|-----------------|-------|--------|----------|-------------------------|--------|
| OP-01 | Create class-completion session checklist as job aid | Checklist tracks per-class completion status; prevents skipped classes during finalization by replacing reliance on memory. | Overprocessing | SOP Steps 5–9; Step 5 note ("Must be repeated for all classes taught"); Step 9 loop-back | Process Owner | S | High | Error reduction / time savings — zero missed-class rework incidents per finalization period; decrease in teacher self-reported time-to-complete | Backlog |
| OP-02 | Create grade weight reference card with screenshot | Visual reference card shows a correctly configured class; gives teachers a verification point before saving weights. | Defect / Rework | SOP Step 5 note; Exception "Incorrect grading weights identified → Reopen and adjust" | Process Owner | S | High | Error reduction — "Incorrect grading weights" exceptions = 0 per finalization period | Backlog |
| OP-03 | Create standard email template for Step 10 notification | Standard template with required subject line and body fields replaces unstructured free-text notification to the secretary. | Handoff | SOP Step 10; Secretary role — tracks teacher submissions but has no defined email format | Process Owner | S | High | Handoff reliability — 100% of notifications include all required fields; secretary manual follow-up burden decreases per period | Backlog |
| OP-04 | Update Step 6 to require explicit weight verification before saving | Step 6 rewritten to gate saving on explicit weight confirmation; makes weight review a required step, not an assumed precondition. | Defect / Rework | CHANGELOG v1.5.1 — "Save before exiting" omission found during cross-artifact validation; SOP Step 6 | Process Owner | S | Medium | Error reduction — Step 6 omission incidents = 0 per finalization period; weight errors caught before save | Backlog |
| OP-05 | Define acceptance criteria for "Is the grade correct?" (Step 7) | Formal acceptance criteria defined for the Step 7 decision point; removes teacher ambiguity about what constitutes a correct grade. | Defect / Ambiguity | SOP Step 7 decision — no definition of "correct" provided | Process Owner + Admin | M | Medium | Error reduction — acceptance criteria documented in SOP; ambiguity-related rework incidents = 0 | Backlog |
| OP-06 | Investigate whether an admin-level bulk finalization view exists | If available, a bulk teacher-level view replaces class-by-class cycling and eliminates the need for a manual completion checklist. | Overprocessing | SOP Steps 5–9 — class-level repetition with no teacher-level aggregate view | Administrator | S (investigate) | Medium | Time savings — investigation finding documented within one admin cycle; recommendation recorded in CHANGELOG | Backlog |
| OP-08 | Investigate whether PowerSchool supports locked weight templates | If available, admin-enforced weight templates lock the 10% exam weight at the system level, eliminating misconfiguration risk entirely. | Defect / Rework | top3-deep-dive.md OP-02 Countermeasure B; SOP Step 5 note — 10% exam weight is guidance only, not system-enforced | Administrator | S (investigate) | Medium | Error reduction — investigation finding documented within one admin cycle; if available, weight misconfiguration eliminated at system level | Backlog |
| OP-07 | Define secretary's downstream follow-up workflow | Secretary's complete post-notification workflow documented end-to-end; closes the last [TBD] gap in the process package. | Handoff | Secretary role — tracks teacher completion but downstream actions were not specified until v1.7.1 | Secretary + Admin | M | Low | Process completeness — secretary workflow documented; no [TBD] rows remain in any process artifact | In Progress |
| OP-09 | Add grading calendar anchor to Step 1 trigger | Step 1 updated with an explicit finalization due date; administrator maintains the date and includes it in the reminder email. | Waiting | SOP Step 1 — "receives email OR recognizes end of quarter is near"; trigger is passive and subjective | Administrator | S | Low | Time savings — late finalization submissions = 0 per grading period; Step 1 trigger references a specific due date | Backlog |

---

## Effort Key

| Code | Definition |
|------|------------|
| S | Small — single artifact update or template creation; completable in one work session |
| M | Medium — requires coordination across roles or multi-artifact revision |

---

## Notes

- OP-01, OP-02, and OP-03 are the Top 3 for 5-Whys root-cause analysis. See [`top3-deep-dive.md`](./top3-deep-dive.md).
- OP-07 (secretary workflow) was partially resolved in v1.7.1 — the secretary's role was defined as tracking teacher submission emails. Full downstream workflow specification remains open.
- All items reference existing SOP step numbers and artifact evidence. No issues were invented; every anchor is citable.

---

*Backlog based on SOP v1.5 and supporting artifacts as of v1.7.2. To be revisited after countermeasures are implemented (M08 measurement phase).*
