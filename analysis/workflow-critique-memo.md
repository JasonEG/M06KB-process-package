# Workflow Critique Memo

**To:** Grading Process Improvement Review
**From:** Jason Geanuracos
**Date:** 2026-02-23
**Re:** Grade Finalization in PowerSchool — Workflow Pain Points and Recommendations
**Based on:** SOP v1.5 (2026-02-16), KB Article v1.6.2, Quick Reference v1.6.3

---

## Executive Summary

The Grade Finalization process (SOP v1.5) is documented, validated, and internally consistent. However, a structured diagnostic review of the SOP, KB article, Quick Reference, and supporting artifacts reveals five recurring pain points. Three of these carry meaningful defect risk — incorrect weights, unsaved changes, and unstructured handoffs — and all six represent opportunities to reduce teacher effort, improve reliability, and close process gaps. This memo documents each issue with its evidence anchor and proposes a practical countermeasure.

---

## Pain Points

Each pain point is assigned an **OP code** (e.g., OP-01) — a unique identifier for each optimization opportunity. Codes are assigned by priority grouping, not by pain point order, and are used consistently across the critique memo, improvement backlog, and deep-dive analysis to trace each issue through to its recommended countermeasure.

### 1. Ambiguous Start Trigger — No Calendar Anchor
**Category:** Waiting
**SOP reference:** Step 1; scope `start_trigger`

The process begins when a teacher "receives an email from the principal or secretary OR recognizes that the end of a quarter or semester is near." The OR clause places the burden of timing awareness entirely on the teacher, with no formal calendar reference. Teachers who miss the email or misread the calendar may start late, compressing the finalization window or missing the deadline entirely.

**Evidence:** SOP Step 1 note — "No system action occurs in this step." The trigger is passive and subjective for the teacher.

**Recommendation (OP-09):** Add an explicit calendar anchor to Step 1 — e.g., "Finalization is due by [DATE]" — maintained by the administrator and included in the reminder email. Small effort, reduces deadline variability.

---

### 2. Manual Class Cycling with No Completion Tracker
**Category:** Overprocessing
**SOP reference:** Steps 5–9; Step 5 note; Step 9 loop-back decision

Steps 5, 6, 7, and 8 must be repeated individually for every class by cycling through a class drop-down menu. A typical teacher schedule spans nine periods, of which five are unique gradeable classes — two sections of the same course finalize as a single entity, and non-instructional periods (lunch, planning, study hall, academic duty) are excluded. This yields exactly twenty sequential UI interactions per finalization cycle with no progress indicator and no record of which classes are done. If a teacher is interrupted or loses their place, there is no system or document safeguard against skipping a class.

**Evidence:** SOP Step 5 note — "Must be repeated for all classes taught." Step 9 decision — "Are all classes finalized? No → Return to Step 7." No tracking artifact exists in the current package.

**Recommendation (OP-01):** Create a five-row class-completion checklist (teacher name, grading period, one row per gradeable class with checkbox and completion date). Low effort, immediate risk reduction.

---

### 3. No Verifiable Reference for Grade Weights
**Category:** Defect / Rework risk
**SOP reference:** Step 5 note; Exception "Incorrect grading weights identified"

The only required weight constraint is that the quarter exam is set to 10% of the final grade; the remaining 90% is allocated at the teacher's discretion. However, this requirement appears only as a prose note in the SOP with no visual reference. PowerSchool does not enforce the 10% value — any configuration that sums to 100% is accepted. A teacher who inadvertently changes the exam weight will produce incorrect final grades that may not be caught until the final grade review at Step 7 — or later, after grades are stored.

**Evidence:** SOP Step 5 note. Exception table — "Incorrect grading weights identified → Reopen and adjust." This exception documents a known, real failure mode.

**Recommendation (OP-02):** Create a grade weight reference card showing the required 10% exam allocation with a screenshot example, and embed it in the SOP and Quick Reference at Step 5. This gives teachers a visual check before saving.

---

### 4. Save-Before-Exit Is a Separate Step with No System Warning
**Category:** Defect / Rework
**SOP reference:** Step 6; CHANGELOG v1.5.1

PowerSchool does not auto-save grade weight changes but will prompt the user to save when navigating away. The risk is not a missing warning — it is that a teacher may confirm the save prompt without first explicitly verifying that the weights are correct. The system accepts any configuration that sums to 100%, so an unreviewed save can silently commit incorrect weights. This gap was reflected in the project's own documentation: the "Save before exiting" instruction was initially missing from the KB Article and only caught during cross-artifact validation (CHANGELOG v1.5.1).

**Evidence:** CHANGELOG v1.5.1 — "Step 8: Added 'Save before exiting' after the Final Grade Status checkbox instruction — omission identified during cross-artifact validation." SOP Exception — "Incorrect grading weights identified → Reopen and save."

**Recommendation (OP-04):** Update Step 6 to require explicit verification of grade weights before confirming the save prompt — e.g., "Confirm the quarter exam weight reads 10% before selecting Save." This makes weight review a required gate, not an assumed precondition.

---

### 5. Unstructured Email Notification — No Template, No Tracking
**Category:** Handoff
**SOP reference:** Step 10; Secretary role; KB_Page Roles table

The process concludes when the teacher "sends an email to the Secretary confirming that all grades are stored in PowerSchool." The SOP provides no email template, no required subject line, no required body content, and no acknowledgment from the secretary. The secretary's follow-up responsibility is to track which teachers have submitted grade finalization confirmation emails for the grading period. However, the SOP provides no email template, no required subject line, and no required body content, leaving the secretary to manually reconcile unstructured emails with no system support.

**Evidence:** SOP Step 10 — "Send an email to the Secretary." No template. Secretary role — tracks teacher completion, but with no defined email format to support consistent tracking.

**Recommendation (OP-03):** Create a standard email template specifying a required subject line (e.g., "Grade Finalization Complete — [Teacher Name] — [Quarter] [Year]") and required body fields (teacher name, grading period, date completed, number of classes). Embed as a copy-paste block in the SOP and Quick Reference. Longer term (OP-07), define the secretary's downstream process.

---

## Summary of Recommendations

| ID | Recommendation | Effort | Priority |
|----|----------------|--------|----------|
| OP-01 | Add class-completion session checklist | S | High |
| OP-02 | Create weight reference card with screenshot | S | High |
| OP-03 | Create standard email template for Step 10 | S | High |
| OP-04 | Merge Steps 5–6 into single save-explicit step | S | Medium |
| OP-06 | Investigate admin-level bulk finalization view | S | Medium |
| OP-07 | Define secretary's follow-up workflow | M | Low |
| OP-09 | Add grading calendar anchor to Step 1 | S | Low |

> The full backlog with owners, metrics, and effort estimates is in [`improvement-backlog-v1.md`](./improvement-backlog-v1.md).
> Root-cause analysis for OP-01, OP-02, and OP-03 is in [`top3-deep-dive.md`](./top3-deep-dive.md).

---

*This memo is based on SOP v1.5 and supporting artifacts as of v1.7.2. All pain points reference specific SOP step numbers and existing artifacts. No steps were invented; all evidence anchors are cited.*
