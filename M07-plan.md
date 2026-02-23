# M07 Plan — Workflow Critique & Improvement Backlog

**Date:** 2026-02-22
**Module:** 07 — Interrogate the Workflow: Bottlenecks, Duplication, and Risk
**Based on:** Grade Finalization process package (M06, v1.6.3)

---

## Overview

Module 07 uses the existing Grade Finalization process package as a diagnostic artifact. The goal is to identify inefficiencies, trace them to evidence, and produce a prioritized improvement backlog ready for measurement (Week 8) and automation scoping (Week 9).

---

## Deliverables

| File | Description |
|------|-------------|
| `analysis/workflow-critique-memo.md` | 1–2 page evidence-based pain-point summary with recommendations |
| `analysis/improvement-backlog-v1.md` | Prioritized backlog table (8 items, ranked by impact + effort) |
| `analysis/top3-deep-dive.md` | 5-Whys + countermeasures + success metrics for Top 3 issues |
| `docs/source/SOP_v1_annotated.md` | Copy of SOP_v1.md with ⚠️ pain-point callouts embedded |
| `prompt-log/week07-analysis-log.md` | New prompt log (Entry 22+) |
| `docs/exports/*.pdf` | PDF exports of memo, backlog, and deep-dive |

Supporting updates: `CHANGELOG.md`, `CLAUDE.md`, `README.md` (add `analysis/` to folder tree).

---

## Identified Pain Points

All issues are grounded in SOP step numbers and existing artifacts.

| # | Issue | Category | SOP Evidence |
|---|-------|----------|--------------|
| 1 | Ambiguous start trigger — "recognize end of quarter is near" is subjective | Waiting | Step 1; scope.start_trigger |
| 2 | Manual class cycling with no completion tracker (Steps 5–9, repeated per class) | Overprocessing | Steps 5–9; Step 5 note "Must be repeated for all classes taught"; Step 9 loop-back |
| 3 | No system-enforced weight validation — 10%/90% is guidance only, no reference | Defect risk | Step 5 note; Exception "Incorrect grading weights identified" |
| 4 | Save-before-exit is a separate step with no system warning if skipped | Defect/Rework | Step 6; CHANGELOG v1.5.1 (save omission found and fixed in KB_Page) |
| 5 | "Is the grade correct?" (Step 7 decision) has no defined acceptance criteria | Defect/Ambiguity | Step 7 decision — no definition of "correct" |
| 6 | Unstructured email notification — no template, no required fields, no tracking | Handoff | Step 10; Secretary role listed as [TBD] in SOP and KB_Page |

---

## Top 3 for Deep-Dive (5-Whys)

### OP-01 — Manual class cycling without a completion tracker (Steps 5–9)
- **5-Whys chain:** Teacher must repeat Steps 5–9 per class → system finalizes at class level, not teacher level → no teacher-level completion view exists → no job-aid compensates → teacher has no progress indicator → risk of silently skipping a class
- **Root cause:** The system operates class-by-class with no teacher-level aggregate view, and the process has no compensating control (e.g., a session checklist).
- **Countermeasure A:** Create a single-page class-completion checklist as a standard job aid — one checkbox per class per grading period.
- **Countermeasure B:** Investigate whether a bulk teacher-level finalization view exists in the PowerSchool admin console.
- **Success metric:** Zero missed-class rework incidents per finalization period; decrease in teacher self-reported time-to-complete.

### OP-02 — No weight validation reference (Step 5)
- **5-Whys chain:** Teacher manually sets weights → system accepts any numeric values → no visual comparison reference exists → 10%/90% rule documented only as a SOP note → weight error possible without detection until Step 7 or later
- **Root cause:** The weight specification is not formalized as a verifiable, illustrated reference; no admin-enforced template locks the configuration.
- **Countermeasure A:** Create a weight reference card (expected values + screenshot per class type) embedded in Quick Reference and SOP.
- **Countermeasure B:** Request that the system administrator lock weight templates in PowerSchool where policy is fixed.
- **Success metric:** "Incorrect grading weights" exceptions = 0 per finalization period.

### OP-03 — Unstructured email notification (Step 10)
- **5-Whys chain:** SOP says "send email" with no template → process was designed from the teacher's perspective, not the secretary's → secretary role and follow-up actions listed as [TBD] → no tracking mechanism defined → secretary manually tracks who has/hasn't completed
- **Root cause:** The handoff was designed without capturing the recipient's information requirements; the secretary's downstream workflow was never specified.
- **Countermeasure A:** Create a standard email template (required subject line + body fields) embedded in the SOP as a copy-paste resource.
- **Countermeasure B:** Replace the email with a shared digital completion form (e.g., Google Form or SharePoint list) giving the secretary a real-time completion dashboard.
- **Success metric:** 100% of notifications include all required fields; secretary follow-up burden per period decreases.

---

## Improvement Backlog (8 items)

**OP codes** (e.g., OP-01) are unique identifiers for each optimization opportunity. They are assigned by priority grouping, not by pain point order, and are used consistently across the critique memo, improvement backlog, and deep-dive analysis to trace each issue through to its recommended countermeasure.

| ID | Opportunity | Category | Evidence Anchor | Owner | Effort | Priority |
|----|-------------|----------|-----------------|-------|--------|----------|
| OP-01 | Add class-completion session checklist as job aid | Overprocessing | SOP Steps 5–9; Step 5 note | Process Owner | S | High |
| OP-02 | Create weight reference card with screenshot | Defect/Rework | SOP Step 5 note + Exception | Process Owner | S | High |
| OP-03 | Create standard email template for Step 10 | Handoff | SOP Step 10; Secretary [TBD] | Process Owner | S | High |
| OP-04 | Merge Steps 5–6 into a single save-explicit step | Defect/Rework | CHANGELOG v1.5.1; SOP Step 6 | Process Owner | S | Medium |
| OP-05 | Define acceptance criteria for "grade is correct" (Step 7) | Defect/Ambiguity | SOP Step 7 decision | Process Owner + Admin | M | Medium |
| OP-06 | Investigate admin-level bulk finalization view | Overprocessing | SOP Steps 5–9 repetition | Administrator | S (investigate) | Medium |
| OP-07 | Define secretary's follow-up workflow (resolve [TBD]) | Handoff | SOP + KB_Page Roles [TBD] rows | Secretary + Admin | M | Low |
| OP-08 | Add grading calendar anchor to Step 1 | Waiting | SOP Step 1 trigger (subjective) | Administrator | S | Low |

---

## Step Rewrite Target — Step 5 (Verify Grade Weights)

The current step lacks: an explicit actor, a precondition, acceptance criteria, and a failure path.

**Rewritten Step 5:**

**Actor:** Teacher
**Precondition:** Step 4 is complete — all grades in the Score Sheet are verified and accurate for the selected class.
**Action:** Open **Settings → Traditional Grade Calculations**. Select the current class. Choose **Actions → Edit**. Review the weight fields:
- Quarter exam weight = **10%**
- All remaining categories combined = **90%** (values must sum to 100%)

If weights are correct, proceed to Step 6. If weights are incorrect, adjust values until they sum to 100% with the quarter exam at 10%, then proceed to Step 6.

**Exit criterion:** Weight fields display 10% (quarter exam) and 90% (remaining), with no system validation error shown.
**Failure path:** If the Save button does not respond, values reset after saving, or a validation error appears → do not proceed to Step 6. Contact IT support via the [IT Help Desk Portal](https://ww3.autotask.net/ClientPortal/login.aspx?ci=302139&accountId=431).

---

## Annotated SOP Approach

`SOP_v1_annotated.md` is a copy of `SOP_v1.md` with `> ⚠️ **Pain Point [OP-XX]:**` blockquotes inserted immediately after the relevant steps. Procedural content is unchanged — annotations are additive only.

---

## Execution Order

1. Create `analysis/` subfolder and the three analysis documents
2. Create `docs/source/SOP_v1_annotated.md`
3. Create `prompt-log/week07-analysis-log.md`
4. Export PDFs (memo, backlog, deep-dive) via `md-to-pdf`
5. Update `CHANGELOG.md`, `CLAUDE.md`, `README.md`
6. Commit and push to `origin/master`

> **Working rule:** Update the prompt log, CHANGELOG, and CLAUDE.md after each step before moving to the next.
