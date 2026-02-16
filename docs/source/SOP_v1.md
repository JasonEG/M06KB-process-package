# Standard Operating Procedure — Finalizing Grades in PowerSchool

**Version:** 1.5
**Last Updated:** 2026-02-16

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
| **Secretary** | Receive confirmation email that grades are stored; Follow-up actions after notification (TBD) |
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

### Step 2 — Log In to PowerSchool

**Actor:** Teacher

Log in to PowerSchool using a valid username and password.

*Note: This step will fail if the prerequisite (valid credentials) is not met.*

### Step 3 — Open PowerTeacher Pro

**Actor:** Teacher

Open PowerTeacher Pro by selecting it under a currently taught class.

### Step 4 — Verify Grades

**Actor:** Teacher

Navigate to **Grading → Score Sheet**, use the class drop-down at the top of the screen to cycle through all classes, and verify that all quarter or semester grades are entered and accurate by reviewing each grade line by line.

*Note: If grades are incorrect, they must be corrected before proceeding.*

### Step 5 — Verify Grade Weights

**Actor:** Teacher

Open **Settings → Traditional Grade Calculations**, select a class you currently teach, choose **Actions → Edit**, and verify the grade weights for the quarter and semester.

*Note: Quarter exam set to 10%; remaining 90% allocated as percentages or total points.*

### Step 6 — Save Grade Calculations

**Actor:** Teacher

Save the grade calculation changes for the class before exiting the Traditional Grade Calculations screen.

*Note: Must be repeated for all classes taught.*

### Step 7 — Review Final Grade

**Actor:** Teacher

Navigate to **Grading → Grades → Traditional** to view the final quarter or semester grade for the selected class.

> **Decision:** Is the final grade correct?
> - **Yes:** Proceed to Step 8.
> - **No:** Return to Step 4.

### Step 8 — Mark Grades as Complete

**Actor:** Teacher

Move cursor to **Final Grade Status** at the bottom of the screen and check "Semester or Quarter Final Grades Are Complete."

*Note: An optional comment may be entered.*

### Step 9 — Repeat for All Classes

**Actor:** Teacher

Use the grading-period drop-down at the top of the screen to repeat the finalization process for all classes taught.

> **Decision:** Are all classes finalized?
> - **Yes:** Proceed to Step 10.
> - **No:** Return to Step 7.

### Step 10 — Notify Secretary & Log Out

**Actor:** Teacher

Send an email to the Secretary confirming that all grades are stored in PowerSchool, then log out.

---

## 7. Exceptions

| Trigger | Resolution | Escalation |
|---------|-----------|------------|
| Grades are missing or incorrect during verification | Correct grades in the Score Sheet; Re-verify accuracy before continuing | Contact student if an assignment is missing; otherwise mark a zero |
| Incorrect grading weights identified | Reopen Traditional Grade Calculations; Adjust weights and save changes | Contact support personnel for assistance |
| Final Grade Status not marked complete for a class | Return to Final Grade Status screen; Check completion box and save | Verify correct grading period is selected, then contact support |
