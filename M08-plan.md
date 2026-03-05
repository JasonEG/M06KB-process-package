# M08 Plan — Measurement & Baseline Dataset

**Date:** 2026-03-03
**Module:** 08 — Measure the Process: Baseline Metrics and Data Analysis
**Based on:** M07 Workflow Critique & Improvement Backlog (v1.7.5)

---

## Overview

Module 08 operationalizes the M07 improvement backlog. The goal is to define measurable metrics for the highest-priority OP codes, establish a Q1 baseline dataset, and use Power Query to transform raw data into a structured workbook that supports evidence-based improvement decisions.

---

## Deliverables

| File | Description |
|------|-------------|
| `measurement/measurement-plan.md` | Metric definitions, OP code mapping, baseline vs. target values |
| `measurement/data/Q1-finalization-export.csv` | 18-row mock raw dataset (Power Query source) |
| `measurement/baseline-dataset.xlsx` | Power Query workbook (4 sheets: Raw, Cleaned, Pivot, Dashboard) |
| `measurement/power-query-steps.md` | Step-by-step Power Query transformation documentation |
| `prompt-log/week08-measurement-log.md` | New prompt log (Entry 28+) |
| `measurement/measurement-plan.pdf` | PDF export of measurement plan |

Supporting updates: `CHANGELOG.md`, `CLAUDE.md`, `README.md` (add `measurement/` folder tree + Source of Truth entries).

---

## Metrics Defined

All metrics are mapped to M07 OP codes. Measurement scope is Q1 (fall grading period). Baseline values are derived from the mock dataset.

| Metric ID | Metric Name | OP Code(s) | Unit | Improvement Target |
|-----------|-------------|------------|------|--------------------|
| M-01 | Finalization completion rate | OP-01, OP-09 | % of classes finalized by deadline | ≥ 95% |
| M-02 | Weight configuration error rate | OP-02 | Errors per teacher per period | ≤ 0.1 |
| M-03 | Notification compliance rate | OP-03 | % of notifications with all required fields | ≥ 90% |
| M-04 | Average time-to-finalize per class | OP-01 | Minutes per class | ≤ 8 min |
| M-05 | Rework incident rate | OP-04, OP-05 | Rework incidents per teacher per period | ≤ 0.2 |

> **Baseline vs. target:** Improvement targets above represent the desired post-improvement state. Actual Q1 baseline values will be derived from the mock dataset and documented in `measurement-plan.md`.

> **OP-06 and OP-08 — not measured here:** Both are "investigate whether X exists" items (admin bulk view; locked weight templates). They do not generate process data suitable for a baseline dataset. They are logged as Backlog items in `improvement-backlog-v1.md` and will be addressed as administrative investigation tasks outside the M08 measurement scope.

---

## Mock Dataset Design (Q1-finalization-export.csv)

**18 rows** — one row per teacher in the school's grade finalization cohort.

**Columns:**

| Column | Type | Description |
|--------|------|-------------|
| `TeacherID` | String | T001–T018 |
| `Department` | String | Math, Science, English, History, Electives |
| `NumClasses` | Integer | Number of classes taught (1–5) |
| `FinalizationDate` | Date | Actual date all classes were finalized |
| `Deadline` | Date | Official Q1 finalization deadline |
| `WeightErrors` | Integer | Number of weight configuration errors recorded |
| `NotificationComplete` | Boolean | 1 = all required fields present; 0 = incomplete |
| `ReworkIncidents` | Integer | Number of rework events (re-opened or resubmitted classes) |
| `AvgTimePerClass_min` | Decimal | Self-reported or system-logged average minutes per class |

---

## Power Query Workbook — Sheet Structure

**Sheet 1: Raw Data**
- Imported directly from `data/Q1-finalization-export.csv` via Power Query
- No manual edits; source-of-truth for all transformations

**Sheet 2: Cleaned Data**
- Power Query transformation applied: data types set, blanks handled
- `DaysFromDeadline` calculated column derived from `FinalizationDate − Deadline` (negative = early, positive = late)
- `OnTime` calculated column: 1 if `DaysFromDeadline ≤ 0`, else 0
- `WeightErrorFlag` calculated column: 1 if `WeightErrors > 0`, else 0

**Sheet 3: Summary Pivot**
- PivotTable by Department: avg `AvgTimePerClass_min`, sum `WeightErrors`, % `NotificationComplete`, % `OnTime`
- PivotChart: bar chart of avg time-to-finalize by department

**Sheet 4: Dashboard**
- Five KPI cells (one per metric M-01 through M-05) with conditional formatting:
  - Green = at or better than target
  - Yellow = within 10% of target
  - Red = misses target

---

## Execution Order

1. Create `M08-plan.md` at root ← **this file**
2. Create `measurement/data/Q1-finalization-export.csv` (18-row mock dataset)
3. Create `measurement/measurement-plan.md` + export PDF ← informed by actual baseline values from CSV
4. Create `measurement/baseline-dataset.xlsx` (Power Query + tables + pivots + conditional formatting)
5. Create `measurement/power-query-steps.md` (Power Query step documentation)
6. Update `README.md` (add `measurement/` tree + Source of Truth entries)
7. Update `CHANGELOG.md`, `prompt-log/week08-measurement-log.md`, `CLAUDE.md`
8. Commit and push to `origin/master`

> **Rationale for order of steps 2–3:** The CSV is generated first so that actual Q1 baseline values can be computed and documented directly in `measurement-plan.md`, rather than leaving them as placeholders.

> **Working rule:** Run a consistency check after each deliverable before proceeding to the next. Update the prompt log, CHANGELOG, and CLAUDE.md at the end of the session.
