# Top 3 Deep Dive — Root Cause Analysis

**Process:** Grade Finalization in PowerSchool
**Version:** 1.0
**Date:** 2026-02-24
**Based on:** Workflow Critique Memo (2026-02-23); SOP v1.5; Improvement Backlog v1.0

---

## Key

| Term | Definition |
|------|------------|
| **OP-##** | Optimization Opportunity — a numbered process improvement candidate identified during the workflow critique. OP-01 through OP-09 are catalogued in the Improvement Backlog. |
| **5-Whys** | A root-cause analysis technique that asks "why" repeatedly until the underlying process failure is identified, rather than stopping at symptoms. |
| **Countermeasure** | A specific corrective action tied to the root cause. Each OP-## in this document has two countermeasures: one immediate (process/document fix) and one systemic (system or policy change). |

---

## Overview

This document presents a 5-Whys root-cause analysis for the three highest-priority optimization opportunities identified in the workflow critique. Issues were selected based on impact (defect risk, teacher effort, handoff reliability) rather than frequency or annoyance. Each analysis ends with a confirmed root cause, two countermeasures, a success metric, and key risks.

---

## OP-01 — Manual Class Cycling with No Completion Tracker

**Category:** Overprocessing
**SOP reference:** Steps 5–9; Step 5 note; Step 9 loop-back decision

### 5-Whys Chain

| Why | Answer |
|-----|--------|
| Why might a teacher skip a class during finalization? | There is no progress indicator — the teacher has no record of which classes are done. |
| Why is there no progress indicator? | Steps 5–9 must be repeated per class by cycling a drop-down menu with no aggregate view. |
| Why does the process repeat class-by-class with no aggregate view? | PowerSchool finalizes grades at the class level, not at the teacher level. |
| Why is there no teacher-level view compensating for this? | No job aid or checklist was ever created to track completion across classes. |
| Why was no compensating control created? | The process was documented from memory of expected behavior, not from a structured gap analysis. |

### Root Cause

The system operates class-by-class with no teacher-level aggregate view, and the process has no compensating control. A teacher with five gradeable classes must execute twenty sequential UI interactions with no system or document safeguard against losing their place or silently skipping a class.

### Countermeasures

**Countermeasure A (OP-01):** Create a single-page class-completion session checklist as a standard job aid — one row per gradeable class, with a checkbox and completion date field, keyed to the teacher's name and grading period. Embed in the SOP and Quick Reference at Step 5.

**Countermeasure B (OP-06):** Investigate whether a bulk teacher-level finalization view exists in the PowerSchool administrator console. If available, document the steps and add to the SOP as an alternate path. If unavailable, record the finding in the CHANGELOG for future system evaluation.

### Success Metric

Zero missed-class rework incidents per finalization period; decrease in teacher self-reported time-to-complete over two consecutive grading periods.

### Key Risks

- Teachers may not adopt the checklist if it is not embedded directly in the SOP workflow (not just referenced).
- A bulk admin view, if it exists, may require elevated permissions not available to all teachers.

---

## OP-02 — No Verifiable Reference for Grade Weights

**Category:** Defect / Rework
**SOP reference:** Step 5 note; Exception "Incorrect grading weights identified → Reopen and adjust"

### 5-Whys Chain

| Why | Answer |
|-----|--------|
| Why might a teacher submit incorrect grade weights? | The weight configuration is done manually in PowerSchool — the system accepts any values that sum to 100%. |
| Why can incorrect values be submitted without detection? | There is no visual comparison reference at the point of entry — only a prose note in the SOP. |
| Why is there only a prose note? | The 10% exam weight requirement was documented as a reminder, not as a verifiable, illustrated reference. |
| Why was no reference card created when the SOP was written? | The SOP was written to describe steps, not to provide visual verification aids at decision points. |
| Why was no visual verification aid added later? | The "Incorrect grading weights" exception was logged as a known failure mode but not traced back to a root cause requiring a process artifact. |

### Root Cause

The weight specification is not formalized as a verifiable, illustrated reference at the point of action. The SOP documents the requirement as a note, but PowerSchool enforces no constraint — any configuration summing to 100% is accepted. A teacher who inadvertently misconfigures weights will produce incorrect final grades that may not surface until Step 7 or after grades are stored.

### Countermeasures

**Countermeasure A (OP-02):** Create a grade weight reference card showing the required 10% exam allocation with a screenshot example of a correctly configured class. Embed as a visual block in the SOP at Step 5 and in the Quick Reference. The card gives teachers a direct visual check before saving.

**Countermeasure B (OP-08):** Request that the system administrator investigate whether PowerSchool supports locked weight templates for classes where the exam weight policy is fixed. If available, an admin-enforced template would eliminate the defect at the system level rather than relying on teacher vigilance.

### Success Metric

"Incorrect grading weights identified" exceptions = 0 per finalization period across all teachers.

### Key Risks

- A screenshot-based reference card becomes stale if the PowerSchool UI is updated — reference card must be versioned and reviewed each academic year.
- Admin-enforced weight templates may not be supported or may conflict with classes where teacher-set weights vary legitimately.

---

## OP-03 — Unstructured Email Notification with No Tracking

**Category:** Handoff
**SOP reference:** Step 10; Secretary role

### 5-Whys Chain

| Why | Answer |
|-----|--------|
| Why does the secretary manually reconcile teacher completion? | Teachers send unstructured emails with no required subject line, body fields, or format. |
| Why are the emails unstructured? | The SOP specifies "send an email" with no template, no required fields, and no acknowledgment requirement. |
| Why was no template defined when the SOP was written? | The process was designed from the teacher's perspective; the secretary's information requirements were never captured. |
| Why were the secretary's requirements not captured? | The secretary's downstream workflow was listed as [TBD] and was not resolved until v1.7.1 of the process package. |
| Why was the secretary role left unresolved? | The role's responsibilities were assumed to be understood and were not treated as a formal process input during initial documentation. |

### Root Cause

The handoff was designed without capturing the recipient's information requirements. The secretary's downstream workflow — tracking which teachers have submitted grade finalization confirmation emails — was never specified as a process input. This left the secretary to manually reconcile unstructured, inconsistent emails with no system support and no defined format to support consistent tracking.

### Countermeasures

**Countermeasure A (OP-03):** Create a standard email template specifying a required subject line (e.g., `Grade Finalization Complete — [Teacher Name] — [Quarter] [Year]`) and required body fields (teacher name, grading period, date completed, number of classes finalized). Embed as a copy-paste block in the SOP at Step 10 and in the Quick Reference.

**Countermeasure B (OP-07):** Replace or supplement the email with a shared digital completion form (e.g., Google Form or SharePoint list) that gives the secretary a real-time completion dashboard. This eliminates manual reconciliation entirely and provides a timestamped audit trail.

### Success Metric

100% of finalization notifications include all required fields per grading period; secretary-reported manual follow-up burden decreases over two consecutive grading periods.

### Key Risks

- A copy-paste email template requires teacher adoption — compliance cannot be enforced without a system-level mechanism.
- A shared digital form (Countermeasure B) requires administrator approval and may not be available in all school IT environments.
- Even a well-structured email can be missed or delayed — the template addresses format but not delivery confirmation.

---

*Root-cause analysis based on SOP v1.5 and supporting artifacts as of v1.7.2. All 5-Whys chains were validated against specific SOP step numbers and existing artifact evidence. No causes were invented.*
