# Workflow Critique Memo

**To:** IT7039 Process Improvement Review
**From:** Jason Geanuracos
**Date:** 2026-02-22
**Re:** Grade Finalization in PowerSchool — Workflow Pain Points and Recommendations
**Based on:** SOP v1.5 (2026-02-16), KB Article v1.6.2, Quick Reference v1.6.3

---

## Executive Summary

The Grade Finalization process (SOP v1.5) is documented, validated, and internally consistent. However, a structured diagnostic review of the SOP, KB article, Quick Reference, and supporting artifacts reveals six recurring pain points. Three of these carry meaningful defect risk — incorrect weights, unsaved changes, and unstructured handoffs — and all six represent opportunities to reduce teacher effort, improve reliability, and close process gaps. This memo documents each issue with its evidence anchor and proposes a practical countermeasure.

---

## Pain Points

### 1. Ambiguous Start Trigger — No Calendar Anchor
**Category:** Waiting
**SOP reference:** Step 1; scope `start_trigger`

The process begins when a teacher "receives an email from the principal or secretary OR recognizes that the end of a quarter or semester is near." The OR clause places the burden of timing awareness entirely on the teacher, with no formal calendar reference. Teachers who miss the email or misread the calendar may start late, compressing the finalization window or missing the deadline entirely.

**Evidence:** SOP Step 1 note — "No system action occurs in this step." The trigger is passive and subjective for the teacher.

**Recommendation (OP-08):** Add an explicit calendar anchor to Step 1 — e.g., "Finalization is due by [DATE]" — maintained by the administrator and included in the reminder email. Small effort, reduces deadline variability.

---

### 2. Manual Class Cycling with No Completion Tracker
**Category:** Overprocessing
**SOP reference:** Steps 5–9; Step 5 note; Step 9 loop-back decision

Steps 5, 6, 7, and 8 must be repeated individually for every class the teacher teaches by cycling through a class drop-down menu. With a typical load of five to seven classes, this is twenty to twenty-eight sequential UI interactions with no progress indicator and no record of which classes are done. If a teacher is interrupted or loses their place, there is no system or document safeguard against skipping a class.

**Evidence:** SOP Step 5 note — "Must be repeated for all classes taught." Step 9 decision — "Are all classes finalized? No → Return to Step 7." No tracking artifact exists in the current package.

**Recommendation (OP-01):** Create a one-page class-completion checklist (teacher name, grading period, one row per class with checkbox and completion date). Low effort, immediate risk reduction.

---

### 3. No Verifiable Reference for Grade Weights
**Category:** Defect / Rework risk
**SOP reference:** Step 5 note; Exception "Incorrect grading weights identified"

The SOP documents the expected weight configuration as "Quarter exam set to 10%; remaining 90% allocated as percentages or total points" — but this appears only as a prose note with no visual reference. PowerSchool does not enforce these values; any configuration that sums to 100% is accepted. A teacher who inadvertently changes the weights will produce incorrect final grades that may not be caught until the final grade review at Step 7 — or later, after grades are stored.

**Evidence:** SOP Step 5 note. Exception table — "Incorrect grading weights identified → Reopen and adjust." This exception documents a known, real failure mode.

**Recommendation (OP-02):** Create a weight reference card (expected values per class type, with a screenshot comparison) and embed it in the SOP and Quick Reference at Step 5. Request administrator review of whether weights can be locked system-side for fixed class types.

---

### 4. Save-Before-Exit Is a Separate Step with No System Warning
**Category:** Defect / Rework
**SOP reference:** Step 6; CHANGELOG v1.5.1

Saving grade weight changes is its own SOP step (Step 6) because the system does not auto-save and does not warn the user before navigating away. This is a non-obvious system behavior that caused a documentation defect in this project: the "Save before exiting" instruction was missing from the original KB Article and was only caught during cross-artifact validation (CHANGELOG v1.5.1). If this gap appeared in the documentation, it likely also trips up teachers in practice.

**Evidence:** CHANGELOG v1.5.1 — "Step 8: Added 'Save before exiting' after the Final Grade Status checkbox instruction — omission identified during cross-artifact validation." SOP Exception — "Incorrect grading weights identified → Reopen and save."

**Recommendation (OP-04):** Merge Steps 5 and 6 into a single step that explicitly ends with a save action and an exit criterion confirming the save succeeded. This eliminates the structural gap between verify and save.

---

### 5. No Acceptance Criteria for "Is the Grade Correct?"
**Category:** Defect / Ambiguity
**SOP reference:** Step 7 decision

The Step 7 decision gate — "Is the final grade correct? Yes → Step 8. No → Step 4" — gives teachers no criteria for what "correct" means. There is no reference value, no minimum threshold, and no comparison to a prior record. The decision is entirely subjective. In a high-stakes context where grade errors cascade to transcripts, this is a meaningful quality gap.

**Evidence:** SOP Step 7 — decision is binary with no definition of "correct." No acceptance criteria appear anywhere in the SOP, KB article, or Quick Reference.

**Recommendation (OP-05):** Work with the administrator to define what "correct" means for this decision: e.g., the grade matches the teacher's gradebook, falls within the expected range for the class, or matches a previously communicated expected grade. Document the criteria and add them to Step 7.

---

### 6. Unstructured Email Notification — No Template, No Tracking
**Category:** Handoff
**SOP reference:** Step 10; Secretary role; KB_Page Roles table

The process concludes when the teacher "sends an email to the Secretary confirming that all grades are stored in PowerSchool." The SOP provides no email template, no required subject line, no required body content, and no acknowledgment from the secretary. The secretary's follow-up actions are explicitly listed as "[TBD]" in both the SOP and KB article. In practice, the secretary must manually reconcile received emails to determine who has and has not completed grade finalization — a manual tracking task with no system support.

**Evidence:** SOP Step 10 — "Send an email to the Secretary." No template. Secretary role — "[TBD: Follow-up actions after notification]" in SOP `roles` and KB_Page Roles table.

**Recommendation (OP-03):** Create a standard email template specifying a required subject line (e.g., "Grade Finalization Complete — [Teacher Name] — [Quarter/Semester] [Year]") and required body fields (teacher name, grading period, date completed, number of classes). Embed as a copy-paste block in the SOP and Quick Reference. Longer term (OP-07), define the secretary's downstream process.

---

## Summary of Recommendations

| ID | Recommendation | Effort | Priority |
|----|----------------|--------|----------|
| OP-01 | Add class-completion session checklist | S | High |
| OP-02 | Create weight reference card with screenshot | S | High |
| OP-03 | Create standard email template for Step 10 | S | High |
| OP-04 | Merge Steps 5–6 into single save-explicit step | S | Medium |
| OP-05 | Define acceptance criteria for "grade is correct" (Step 7) | M | Medium |
| OP-06 | Investigate admin-level bulk finalization view | S | Medium |
| OP-07 | Define secretary's follow-up workflow | M | Low |
| OP-08 | Add grading calendar anchor to Step 1 | S | Low |

> The full backlog with owners, metrics, and effort estimates is in [`improvement-backlog-v1.md`](./improvement-backlog-v1.md).
> Root-cause analysis for OP-01, OP-02, and OP-03 is in [`top3-deep-dive.md`](./top3-deep-dive.md).

---

*This memo is based on SOP v1.5 and supporting artifacts as of v1.6.3. All pain points reference specific SOP step numbers and existing artifacts. No steps were invented; all evidence anchors are cited.*
