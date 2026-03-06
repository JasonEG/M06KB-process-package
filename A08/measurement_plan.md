# Measurement Plan — Grade Finalization Process

**Process:** Grade Finalization in PowerSchool
**Version:** 1.0
**Date:** 2026-03-03
**Based on:** M07 Improvement Backlog v1.0 (OP-01 through OP-09); SOP v1.5
**Measurement scope:** Q1 (Fall 2025) — finalization deadline 2025-10-31

---

## Purpose

This measurement plan defines the metrics used to establish a pre-improvement baseline for the Grade Finalization process. Each metric is tied to one or more M07 optimization opportunities (OP codes) and will be used to evaluate the effectiveness of implemented countermeasures in future grading periods.

---

## Data Source

| Field | Value |
|-------|-------|
| File | `data/Q1-finalization-export.csv` |
| Rows | 18 (one per teacher) |
| Period | Q1 — Fall 2025 |
| Deadline | 10/31/2025 |
| Departments | Math, Science, English, History, Electives |

All data is mock/illustrative, modeled on realistic grade finalization patterns. No personally identifiable information is included.

---

## Metric Definitions

### M-01 — Finalization Completion Rate

| Field | Value |
|-------|-------|
| **Definition** | Percentage of teachers who finalized all classes by the Q1 deadline |
| **OP Code(s)** | OP-01 (manual class cycling), OP-09 (ambiguous start trigger) |
| **Unit** | % of teachers on time |
| **Formula** | (Teachers with FinalizationDate ≤ Deadline) ÷ Total Teachers × 100 |
| **Q1 Baseline** | 83.3% (15 of 18 teachers on time) |
| **Improvement Target** | ≥ 95% |
| **Gap** | −11.7 percentage points |
| **Late teachers** | T003 (Nov 2), T007 (Nov 3), T012 (Nov 1) |

---

### M-02 — Weight Configuration Error Rate

| Field | Value |
|-------|-------|
| **Definition** | Average number of grade weight configuration errors per teacher per grading period |
| **OP Code(s)** | OP-02 (no weight validation reference) |
| **Unit** | Errors per teacher |
| **Formula** | Total WeightErrors ÷ Total Teachers |
| **Q1 Baseline** | 0.28 (5 errors across 18 teachers) |
| **Improvement Target** | ≤ 0.10 |
| **Gap** | +0.18 errors/teacher above target |
| **Affected teachers** | T003, T005, T008, T011, T017 |

---

### M-03 — Notification Compliance Rate

| Field | Value |
|-------|-------|
| **Definition** | Percentage of teacher notifications that include all required fields |
| **OP Code(s)** | OP-03 (unstructured email notification) |
| **Unit** | % of notifications compliant |
| **Formula** | (Teachers with NotificationComplete = 1) ÷ Total Teachers × 100 |
| **Q1 Baseline** | 66.7% (12 of 18 notifications complete) |
| **Improvement Target** | ≥ 90% |
| **Gap** | −23.3 percentage points |
| **Non-compliant teachers** | T003, T006, T010, T012, T015, T017 |

---

### M-04 — Average Time-to-Finalize per Class

| Field | Value |
|-------|-------|
| **Definition** | Average minutes a teacher spends finalizing a single class (all steps, one class) |
| **OP Code(s)** | OP-01 (manual class cycling without completion tracker) |
| **Unit** | Minutes per class |
| **Formula** | Sum of AvgTimePerClass_min ÷ Total Teachers |
| **Q1 Baseline** | 8.4 min |
| **Improvement Target** | ≤ 8.0 min |
| **Gap** | +0.4 min/class above target |
| **Slowest teachers** | T007 (12.5 min), T003 (11.2 min), T017 (11.8 min) |

---

### M-05 — Rework Incident Rate

| Field | Value |
|-------|-------|
| **Definition** | Average number of rework events (re-opened or resubmitted classes) per teacher per grading period |
| **OP Code(s)** | OP-04 (save-before-exit omission), OP-05 (no acceptance criteria for Step 7) |
| **Unit** | Incidents per teacher |
| **Formula** | Total ReworkIncidents ÷ Total Teachers |
| **Q1 Baseline** | 0.39 (7 incidents across 18 teachers) |
| **Improvement Target** | ≤ 0.20 |
| **Gap** | +0.19 incidents/teacher above target |
| **Affected teachers** | T003 (1), T005 (1), T007 (2), T010 (1), T014 (1), T017 (1) |

---

## Baseline Summary

| Metric ID | Metric Name | Q1 Baseline | Improvement Target | Gap | Meets Target? |
|-----------|-------------|-------------|--------------------|-----|---------------|
| M-01 | Finalization completion rate | 83.3% | ≥ 95% | −11.7 pp | No |
| M-02 | Weight configuration error rate | 0.28 errors/teacher | ≤ 0.10 | +0.18 | No |
| M-03 | Notification compliance rate | 66.7% | ≥ 90% | −23.3 pp | No |
| M-04 | Avg time-to-finalize per class | 8.4 min | ≤ 8.0 min | +0.4 min | No |
| M-05 | Rework incident rate | 0.39 incidents/teacher | ≤ 0.20 | +0.19 | No |

All five metrics fall short of their improvement targets. M-04 has the smallest gap (0.4 min); M-03 has the largest (23.3 pp). This baseline confirms the M07 critique findings and provides a measurable starting point for countermeasure evaluation.

---

## Out-of-Scope Items

The following M07 OP codes are not measured in this plan. Both are administrative investigation tasks that do not generate process data suitable for a repeatable baseline metric.

| OP Code | Opportunity | Reason Excluded |
|---------|-------------|-----------------|
| OP-06 | Investigate admin-level bulk finalization view | Investigation task; outcome is a documented finding, not a recurring metric |
| OP-08 | Investigate PowerSchool locked weight templates | Investigation task; outcome is a documented finding, not a recurring metric |

Both items remain open in `analysis/improvement-backlog-v1.md` with Status: Backlog.

---

## Measurement Cadence

| Activity | Frequency | Owner |
|----------|-----------|-------|
| Collect finalization data | Each grading period (Q1–Q4) | Process Owner |
| Compute M-01 through M-05 | Within 1 week of deadline | Process Owner |
| Compare to targets | Each grading period | Process Owner |
| Update baseline dataset | Each grading period | Process Owner |
| Review and revise targets | Annually | Process Owner + Admin |

---

*Measurement plan based on SOP v1.5 and M07 Improvement Backlog v1.0. To be revisited after countermeasures are implemented.*
