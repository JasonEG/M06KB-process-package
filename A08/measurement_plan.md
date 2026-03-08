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

## Data Collection Method

| Field | Value |
|-------|-------|
| **Primary source** | PowerSchool grade finalization admin report — exported by the building principal or designee within one week of each grading-period deadline |
| **Export format** | CSV (one row per teacher) |
| **Collection trigger** | Each grading period deadline (Q1–Q4) |
| **Responsible party** | Process Owner (building-level admin) |

### Per-Metric Collection Notes

| Metric | How Data Is Collected |
|--------|----------------------|
| M-01 Finalization completion rate | `FinalizationDate` and `Deadline` columns from admin export; on-time status derived in Power Query |
| M-02 Weight configuration error rate | `WeightErrors` column logged by admin during or after the finalization window (review of grade weight setup screens) |
| M-03 Notification compliance rate | `NotificationComplete` column — admin confirms whether each teacher's finalization email contained all required fields (subject line, class list, signature) |
| M-04 Avg time-to-finalize per class | `AvgTimePerClass_min` — self-reported by teachers via end-of-period survey, or extracted from PowerSchool session logs if available |
| M-05 Rework incident rate | `ReworkIncidents` — count of re-opened or resubmitted classes logged by admin during the finalization window |

### Privacy and Redaction Plan

- **No student data is collected or stored.** All metrics are teacher-level aggregates.
- **Teacher names are replaced with anonymous IDs** (T001–T018) before any data is stored, shared, or analyzed. The ID-to-name mapping is held only by the Process Owner and is not included in this dataset.
- **The CSV and workbook are stored in the process package repository**, which is access-controlled and not publicly published.
- If this process is adopted at scale, the ID mapping should be stored separately from the dataset and destroyed after the improvement cycle concludes.

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
| **Slowest teachers** | T007 (12.5 min), T017 (11.8 min), T003 (11.2 min) |

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

## Success Criteria

A pilot or improvement initiative for this process will be considered successful if, by the end of the first post-intervention grading period (Q2 — Winter 2026), the following conditions are met:

| Metric | Minimum Acceptable Improvement | Full Success Threshold |
|--------|-------------------------------|------------------------|
| M-01 Finalization completion rate | ≥ 90% on time (up from 83.3%) | ≥ 95% on time |
| M-02 Weight configuration error rate | ≤ 0.20 errors/teacher (reduction of ≥ 30%) | ≤ 0.10 errors/teacher |
| M-03 Notification compliance rate | ≥ 80% compliant (up from 66.7%) | ≥ 90% compliant |
| M-04 Avg time-to-finalize per class | ≤ 8.2 min (any measurable reduction) | ≤ 8.0 min |
| M-05 Rework incident rate | ≤ 0.30 incidents/teacher (reduction of ≥ 20%) | ≤ 0.20 incidents/teacher |

**Minimum acceptable improvement** represents a meaningful directional signal — enough to confirm the countermeasure is working and worth continuing. **Full success** represents the long-term improvement target.

A pilot will be considered **unsuccessful** if any metric regresses (moves further from target) compared to the Q1 baseline, or if participant feedback indicates the countermeasure created new friction without offsetting benefit.

---

## Baseline Interpretation

### M-01 — Finalization Completion Rate

Fifteen out of eighteen teachers hit the deadline, which tells me most people are meeting expectations. The three who were late — T003, T007, and T012 — were only a few days past the deadline, which could be explained by illness or some other grading irregularity rather than a systemic failure. That said, the gap still exists and is worth addressing. A missing progress tracker likely contributes: without one, a teacher may not realize they have an unfinalized class remaining and simply forget it. Some teachers may also be unsure the window is even open, though that is less likely given that quarter end dates are on the district calendar and most staff are aware of them. The connection to OP-01 (no completion tracker) and OP-09 (ambiguous start trigger) is real, even if the late submissions in this sample were not severe.

### M-02 — Weight Configuration Error Rate

Five teachers had weight configuration errors, which is somewhat expected. Grade weighting is not intuitive, especially for teachers who are not comfortable with how percentages work or who are unfamiliar with how PowerSchool structures category weights. You would think high school teachers would handle this easily, but the system setup makes it more complicated than it appears, this is a problem that comes up every grading period. The baseline of 0.28 errors per teacher is nearly three times the target of 0.10, which confirms that the lack of a weight validation reference (OP-02) is a real gap. Including a validation reference sheet or, ideally, an in-system visual reminder showing teachers what their weight setup should look like could meaningfully reduce these errors.

### M-03 — Notification Compliance Rate

At 66.7%, the notification compliance rate is the weakest result in this baseline — only two-thirds of teachers sent a complete notification, leaving six non-compliant. This is the metric with the largest gap from target (−23.3 percentage points) and arguably the one that needs to be addressed first. Email seems like a simple task, but without a standard template, teachers are left to figure out what to include, when to send it, and where to send it. It is also likely that some teachers notified the secretary informally (stopping by the office or sending a text) which would not be captured as compliant even if the intent was there. A standardized email template tied to a clear trigger (OP-03) would remove the ambiguity and give both teachers and the secretary a consistent, trackable record.

### M-04 — Average Time-to-Finalize per Class

An average of 8.4 minutes per class is close to the target but the real-world impact adds up fast. A teacher with five classes is spending 40–50 minutes just finalizing grades during an already compressed end-of-quarter window — time that could otherwise go toward grading, planning, or supporting students. The 0.4-minute gap from target may look small, but reducing it would be well-received by staff. Some of the higher individual times (T007 at 12.5 minutes, T017 at 11.8 minutes, T003 at 11.2 minutes) may reflect factors like more grades to enter, a less efficient input device such as a laptop trackpad, or repetitive navigation caused by the lack of a progress tracker (OP-01). Without knowing which classes are already done, teachers may be cycling through completed classes unnecessarily, wasting time in the process. It is also worth noting that these same three teachers appear across multiple problem metrics, a pattern explored further in M-05.

### M-05 — Rework Incident Rate

The rework incident rate of 0.39 per teacher is nearly double the target of 0.20, with seven incidents recorded across six teachers — including T007 with two incidents. Rework at this scale suggests that some teachers are either not saving before exiting (OP-04) or are finalizing classes without confirming the correct grade configuration first (OP-05). A pattern worth calling out is that T003, T007, and T017 appear across multiple metrics in this baseline, not just rework, but also late finalization, weight errors, and slow completion times. These individuals are likely candidates for targeted peer coaching, a one-on-one walkthrough of the process with a colleague or administrator they trust, or simply a first-time structured orientation. It is possible they were never formally trained on the finalization workflow, which would explain the recurring errors across multiple dimensions. Addressing their needs directly rather than waiting for a school-wide rollout is likely the highest-leverage starting point for improvement.

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

## Quick Pilot Design — Email Template Pilot (Q2)

**OP Code addressed:** OP-03 (unstructured email notification)
**Primary metric:** M-03 — Notification compliance rate (Q1 baseline: 66.7%)

### Pilot Scope and Duration

| Field | Details |
|-------|---------|
| **Participants** | All 18 teachers (school-wide) |
| **Duration** | Q2 finalization window — approximately 1 week surrounding the Q2 deadline |
| **Intervention** | Distribute a standard notification email template to all teachers before Q2 opens. Admin sends a reminder 3 days before the deadline prompting teachers to use the template when notifying the office. |

The template will define the required fields: subject line format, class list, and signature. Teachers copy and send — no training session required.

### Success Metrics and Measurement Approach

| Metric | Q1 Baseline | Minimum Success (Q2) | Full Success (Q2) |
|--------|------------|----------------------|-------------------|
| M-03 Notification compliance rate | 66.7% | ≥ 80% | ≥ 90% |

After the Q2 deadline, the Process Owner reviews received notifications and scores each as compliant or non-compliant using the same criteria as Q1. The Q2 rate is compared directly to the Q1 baseline. No additional tooling is required.

Secondary signal: track whether any of the six Q1 non-compliant teachers (T003, T006, T010, T012, T015, T017) submitted compliant notifications in Q2.

### Risk Mitigation

| Risk | Likelihood | Mitigation |
|------|-----------|------------|
| Teachers ignore the template | Medium | Admin sends a personal follow-up to Q1 non-compliant teachers 1 day before the deadline |
| Template creates confusion (wrong fields) | Low | Admin reviews the template draft before distribution; one revision cycle allowed |
| Informal notification (text/in-person) continues | Medium | Admin logs informal notifications separately but does not count them as compliant — consistent with Q1 scoring |

**Rollback plan:** If M-03 does not improve or worsens in Q2, the template is retired and the approach escalates to a mandatory pre-deadline checkin meeting. No system changes are involved, so rollback requires no technical steps.

**Monitor:** Process Owner reviews compliance within 3 business days of the Q2 deadline and documents findings in the baseline dataset.

---

*Measurement plan based on SOP v1.5 and M07 Improvement Backlog v1.0. To be revisited after countermeasures are implemented.*
