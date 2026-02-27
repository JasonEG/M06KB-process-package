# Standard Operating Procedure — Finalizing Grades in PowerSchool
# (Annotated — Workflow Pain Points)

**Version:** 1.5 (Annotated)
**Last Updated:** 2026-02-26
**Annotation Author:** Jason Geanuracos
**Based on:** SOP v1.5; Workflow Critique Memo (2026-02-23); Improvement Backlog v1.0; Top-3 Deep Dive (2026-02-25)

> **About this document:** This is a read-only annotated copy of SOP v1.5. Procedural content is unchanged. Callout blocks identify known pain points and optimization opportunities at the step where they occur. Each callout references an OP code from the Improvement Backlog for traceability. No steps have been added, removed, or reworded.

---

## 1. Purpose

Standardize the process for teachers to verify, weight, finalize, and store quarter or semester grades in PowerSchool, and to notify the secretary when grade storage is complete.

---

## 2. Scope

**Start Trigger:** Teacher receives an email from the building principal or secretary OR recognizes that the end of a quarter or semester is near.

**End State:** All grades are stored in PowerSchool and an email confirmation has been sent to the secretary.

### In Scope

- Logging into PowerSchool
- Verifying grade accuracy for all classes
- Adjusting traditional grade calculations
- Finalizing quarter or semester grades
- Email notification to the secretary

### Out of Scope

- Entering individual assignments prior to verification
- System administration or configuration
- Post-finalization grade changes
- Communication with students or parents

---

## 3. Roles & Responsibilities

| Role | Responsibilities |
|------|-----------------|
| **Teacher** | Verify all grades are entered and accurate; Apply correct grading weights; Finalize grades; Notify the secretary upon completion |
| **Secretary** | Receive confirmation email that grades are stored; Track which teachers have submitted grade finalization confirmation emails for the grading period |
| **Principal** | Send reminder email indicating grading window |

---

## 4. Prerequisites

- **Access:** Valid username and password for PowerSchool
- **Tools:** PowerSchool / PowerTeacher Pro
- **Required Information:** List of assigned classes; Awareness of current grading period (quarter or semester)

---

## 5. Inputs & Outputs

**Inputs:**

- Existing grade data for all classes
- Selected grading period (quarter or semester)

**Outputs:**

- Finalized grades stored in PowerSchool
- Email confirmation sent to the secretary

---

## 6. Procedure

### Step 1 — Determine Timing

**Actor:** Teacher

Determine that it is time to finalize grades by reviewing an email from the Principal or by recognizing that the end of the quarter or semester is approaching.

> **Decision:** Is it time to finalize grades?
> - **Yes:** Proceed to Step 2.
> - **No:** End Process.

*Note: No system action occurs in this step.*

> ⚠️ **[OP-09] — Waiting:** The trigger is passive — "receives email OR recognizes end of quarter is near." No calendar anchor exists. Teachers who miss the email or misjudge timing may start late, compressing or missing the finalization window. This is a low-effort fix.
> *Recommendation: Add an explicit due date (e.g., "Finalization due by [DATE]") to Step 1 and the reminder email, maintained by the administrator.*

---

### Step 2 — Log In to PowerSchool

**Actor:** Teacher

Log in to PowerSchool using a valid username and password.

*Note: This step will fail if the prerequisite (valid credentials) is not met.*

---

### Step 3 — Open PowerTeacher Pro

**Actor:** Teacher

Open PowerTeacher Pro by selecting it under a currently taught class.

---

### Step 4 — Verify Grades

**Actor:** Teacher

Navigate to **Grading → Score Sheet**, use the class drop-down at the top of the screen to cycle through all classes, and verify that all quarter or semester grades are entered and accurate by reviewing each grade line by line.

*Note: If grades are incorrect, they must be corrected before proceeding.*

---

### Step 5 — Verify Grade Weights

**Actor:** Teacher

Open **Settings → Traditional Grade Calculations**, select a class you currently teach, choose **Actions → Edit**, and verify the grade weights for the quarter and semester.

*Note: Quarter exam set to 10%; remaining 90% allocated as percentages or total points.*

> ⚠️ **[OP-02] — Defect / Rework Risk:** No visual reference exists for required grade weights. PowerSchool accepts any configuration that sums to 100% — an incorrect exam weight (e.g., 15% instead of 10%) will not trigger a system error. Misconfigured weights may not surface until Step 7 or, worse, after grades are stored.
> *Recommendation: Create a weight reference card with a screenshot of a correctly configured class, and embed it in the SOP and Quick Reference at this step.*

> ⚠️ **[OP-08] — Defect / Rework (Investigation):** The 10% exam weight is a procedural guideline only — PowerSchool does not enforce it. Admin-configurable weight templates, if available, could lock this value at the system level and eliminate teacher misconfiguration risk entirely.
> *Recommendation: Investigate whether PowerSchool supports locked or admin-enforced weight templates.*

> ⚠️ **[OP-01] — Overprocessing:** Steps 5, 6, 7, and 8 must be repeated manually for every class using the class drop-down. A typical teacher schedule has 5 unique gradeable classes, producing 20 sequential UI interactions per finalization cycle. There is no progress indicator and no record of which classes have been completed. If a teacher is interrupted, there is no safeguard against skipping a class.
> *Recommendation: Create a five-row class-completion checklist (teacher name, grading period, one checkbox per class) as a job aid.*

> ⚠️ **[OP-06] — Overprocessing (Investigation):** The SOP addresses only the teacher's class-by-class view. No admin-level bulk finalization view is documented. If one exists in PowerSchool, it could replace class-by-class cycling entirely — eliminating both OP-01 and the need for a manual checklist.
> *Recommendation: Investigate whether an aggregate teacher-level finalization view is available to administrators.*

---

### Step 6 — Save Grade Calculations

**Actor:** Teacher

Save the grade calculation changes for the class before exiting the Traditional Grade Calculations screen.

*Note: Must be repeated for all classes taught.*

> ⚠️ **[OP-04] — Defect / Rework:** PowerSchool does not auto-save but will prompt the user to save when navigating away. The risk is that a teacher may confirm the save prompt without first verifying that the weights are correct. The system silently accepts any valid configuration, so an unreviewed save can commit incorrect weights. This gap was previously reflected in the project documentation: the "Save before exiting" instruction was missing from the KB Article until v1.5.1, caught only during cross-artifact validation.
> *Recommendation: Update Step 6 to require explicit weight verification before confirming the save prompt — e.g., "Confirm the quarter exam weight reads 10% before selecting Save."*

---

### Step 7 — Review Final Grade

**Actor:** Teacher

Navigate to **Grading → Grades → Traditional** to view the final quarter or semester grade for the selected class.

> **Decision:** Is the final grade correct?
> - **Yes:** Proceed to Step 8.
> - **No:** Return to Step 4.

> ⚠️ **[OP-05] — Defect / Ambiguity:** The decision "Is the final grade correct?" has no documented acceptance criteria. Teacher judgment is the intended design, but with no threshold or definition of "correct," it is not possible to standardize or audit this decision point. Ambiguity here leaves rework risk unresolvable at the process level.
> *Recommendation: Define formal acceptance criteria for this decision point (e.g., grade matches expected calculation, no missing assignments, weights match reference card) in coordination with administration.*

---

### Step 8 — Mark Grades as Complete

**Actor:** Teacher

Move cursor to **Final Grade Status** at the bottom of the screen and check "Semester or Quarter Final Grades Are Complete."

*Note: An optional comment may be entered.*

---

### Step 9 — Repeat for All Classes

**Actor:** Teacher

Use the grading-period drop-down at the top of the screen to repeat the finalization process for all classes taught.

> **Decision:** Are all classes finalized?
> - **Yes:** Proceed to Step 10.
> - **No:** Return to Step 7.

---

### Step 10 — Notify Secretary & Log Out

**Actor:** Teacher

Send an email to the Secretary confirming that all grades are stored in PowerSchool, then log out.

> ⚠️ **[OP-03] — Handoff:** No email template, required subject line, or required body content is specified. The secretary must reconcile unstructured free-text emails — teacher by teacher, period by period — with no system support. Inconsistent email format increases the risk of missed or ambiguous notifications and adds manual tracking burden on the secretary.
> *Recommendation: Create a standard email template with a required subject line (e.g., "Grade Finalization Complete — [Teacher Name] — [Quarter] [Year]") and required body fields (teacher name, grading period, date completed, number of classes). Embed as a copy-paste block in the SOP and Quick Reference.*

> ⚠️ **[OP-07] — Handoff (In Progress):** The secretary's downstream follow-up workflow after receiving notification emails is not fully documented end-to-end. The secretary's role was clarified in v1.7.1 (tracks which teachers have submitted confirmation emails for the grading period), but the complete post-notification process remains unspecified.
> *Recommendation: Define and document the secretary's full post-notification workflow — what happens after all teachers have submitted, what escalation looks like if a teacher does not notify, and how completion is reported to administration.*

---

## 7. Exceptions

| Trigger | Resolution | Escalation |
|---------|-----------|------------|
| Grades are missing or incorrect during verification | Correct grades in the Score Sheet; Re-verify accuracy before continuing | Contact student if an assignment is missing; otherwise mark a zero |
| Incorrect grading weights identified | Reopen Traditional Grade Calculations; Adjust weights and save changes | Contact support personnel for assistance |
| Final Grade Status not marked complete for a class | Return to Final Grade Status screen; Check completion box and save | Verify correct grading period is selected, then contact support |

---

## 8. Annotation Summary

| OP Code | Step | Category | Priority | Status |
|---------|------|----------|----------|--------|
| OP-01 | Steps 5–9 | Overprocessing | High | Backlog |
| OP-02 | Step 5 | Defect / Rework | High | Backlog |
| OP-03 | Step 10 | Handoff | High | Backlog |
| OP-04 | Step 6 | Defect / Rework | Medium | Backlog |
| OP-05 | Step 7 | Defect / Ambiguity | Medium | Backlog |
| OP-06 | Steps 5–9 | Overprocessing | Medium | Backlog |
| OP-07 | Step 10 | Handoff | Low | In Progress |
| OP-08 | Step 5 | Defect / Rework | Medium | Backlog |
| OP-09 | Step 1 | Waiting | Low | Backlog |

> Full backlog with descriptions, owners, and success metrics: [`improvement-backlog-v1.md`](../../analysis/improvement-backlog-v1.md)
> Root-cause analysis for OP-01, OP-02, OP-03: [`top3-deep-dive.md`](../../analysis/top3-deep-dive.md)

---

*Annotated SOP based on SOP v1.5 and analysis artifacts as of v1.7.4. Procedural content is unchanged from SOP v1.5. All OP codes are traceable to the Improvement Backlog v1.0.*
