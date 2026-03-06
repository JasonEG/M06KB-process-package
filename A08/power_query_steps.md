# Power Query Steps — Grade Finalization Baseline Dataset

**Workbook:** `measurement/baseline-dataset.xlsx`
**Version:** 1.0
**Date:** 2026-03-05
**Source file:** `measurement/data/Q1-finalization-export.csv`

---

## Overview

This document records the Power Query transformations applied to produce the **Cleaned Data** sheet in `baseline-dataset.xlsx`. Steps are listed in the order they appear in the Power Query Applied Steps pane. The M query expression for each step is included for reproducibility.

The Raw Data sheet is the unmodified import. All calculated columns are derived in Power Query before loading to Cleaned Data.

---

## Step 1 — Connect to Source CSV

**Action:** Import `Q1-finalization-export.csv` via Power Query.

**Excel path:** Data → Get Data → From File → From Text/CSV → select `data/Q1-finalization-export.csv`

**Applied Step Name:** `Source`

```m
Source = Csv.Document(
    File.Contents("data\Q1-finalization-export.csv"),
    [Delimiter=",", Columns=9, Encoding=1252, QuoteStyle=QuoteStyle.None]
)
```

---

## Step 2 — Promote Headers

**Action:** Use first row as column headers.

**Applied Step Name:** `PromotedHeaders`

```m
PromotedHeaders = Table.PromoteHeaders(Source, [PromoteAllScalars=true])
```

**Result:** Columns named: `TeacherID`, `Department`, `NumClasses`, `FinalizationDate`, `Deadline`, `WeightErrors`, `NotificationComplete`, `ReworkIncidents`, `AvgTimePerClass_min`

---

## Step 3 — Set Data Types

**Action:** Assign correct data types to all nine columns.

**Applied Step Name:** `ChangedTypes`

```m
ChangedTypes = Table.TransformColumnTypes(PromotedHeaders, {
    {"TeacherID",            type text},
    {"Department",           type text},
    {"NumClasses",           Int64.Type},
    {"FinalizationDate",     type date},
    {"Deadline",             type date},
    {"WeightErrors",         Int64.Type},
    {"NotificationComplete", Int64.Type},
    {"ReworkIncidents",      Int64.Type},
    {"AvgTimePerClass_min",  type number}
})
```

**Note on blank handling:** The M08 plan notes "blanks handled" as part of the cleaning step. The Q1-finalization-export.csv contains no blank values, so no explicit null-removal step was required. If future grading-period exports contain blank rows or missing fields, add a `Table.SelectRows` step after `ChangedTypes` to filter out nulls before the calculated columns are derived.

---

## Step 4 — Add DaysFromDeadline Column

**Action:** Calculate the number of days between `FinalizationDate` and `Deadline`. Negative values indicate early finalization; positive values indicate late finalization; zero indicates on-deadline completion.

**Applied Step Name:** `AddedDaysFromDeadline`

```m
AddedDaysFromDeadline = Table.AddColumn(
    ChangedTypes,
    "DaysFromDeadline",
    each Duration.Days([FinalizationDate] - [Deadline]),
    Int64.Type
)
```

**Interpretation:**
- Negative → teacher finalized before deadline (early)
- 0 → teacher finalized on the deadline date (on time)
- Positive → teacher finalized after deadline (late)

---

## Step 5 — Add OnTime Column

**Action:** Flag each teacher as on time (1) or late (0) based on `DaysFromDeadline`.

**Applied Step Name:** `AddedOnTime`

```m
AddedOnTime = Table.AddColumn(
    AddedDaysFromDeadline,
    "OnTime",
    each if [DaysFromDeadline] <= 0 then 1 else 0,
    Int64.Type
)
```

**Used by:** M-01 Finalization completion rate → `SUM(OnTime) / COUNT(TeacherID)`

---

## Step 6 — Add WeightErrorFlag Column

**Action:** Flag each teacher as having a weight configuration error (1) or not (0).

**Applied Step Name:** `AddedWeightErrorFlag`

```m
AddedWeightErrorFlag = Table.AddColumn(
    AddedOnTime,
    "WeightErrorFlag",
    each if [WeightErrors] > 0 then 1 else 0,
    Int64.Type
)
```

**Used by:** Filtering and identifying affected teachers in the Dashboard and Summary Pivot (e.g., highlighting rows where a weight error occurred). Note: the M-02 metric formula uses `SUM(WeightErrors)` directly — not `SUM(WeightErrorFlag)` — because WeightErrors captures the error count per teacher, which may exceed 1. WeightErrorFlag is a convenience flag for conditional formatting and row-level filtering only.

---

## Step 7 — Load to Worksheet

**Action:** Close Power Query Editor and load the transformed table to the **Cleaned Data** sheet.

**Excel path:** Home → Close & Load → Close & Load To → Existing Worksheet → select Cleaned Data!$A$2

**Result:** 18 rows × 12 columns loaded to `Cleaned Data`, beginning at cell A2 (row 1 reserved for title label).

---

## Final Query (M Code — Complete)

```m
let
    Source = Csv.Document(
        File.Contents("data\Q1-finalization-export.csv"),
        [Delimiter=",", Columns=9, Encoding=1252, QuoteStyle=QuoteStyle.None]
    ),
    PromotedHeaders = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    ChangedTypes = Table.TransformColumnTypes(PromotedHeaders, {
        {"TeacherID",            type text},
        {"Department",           type text},
        {"NumClasses",           Int64.Type},
        {"FinalizationDate",     type date},
        {"Deadline",             type date},
        {"WeightErrors",         Int64.Type},
        {"NotificationComplete", Int64.Type},
        {"ReworkIncidents",      Int64.Type},
        {"AvgTimePerClass_min",  type number}
    }),
    AddedDaysFromDeadline = Table.AddColumn(
        ChangedTypes,
        "DaysFromDeadline",
        each Duration.Days([FinalizationDate] - [Deadline]),
        Int64.Type
    ),
    AddedOnTime = Table.AddColumn(
        AddedDaysFromDeadline,
        "OnTime",
        each if [DaysFromDeadline] <= 0 then 1 else 0,
        Int64.Type
    ),
    AddedWeightErrorFlag = Table.AddColumn(
        AddedOnTime,
        "WeightErrorFlag",
        each if [WeightErrors] > 0 then 1 else 0,
        Int64.Type
    )
in
    AddedWeightErrorFlag
```

---

## Column Reference — Cleaned Data Sheet

| # | Column | Type | Source | Notes |
|---|--------|------|--------|-------|
| 1 | TeacherID | Text | CSV | T001–T018 |
| 2 | Department | Text | CSV | Math, Science, English, History, Electives |
| 3 | NumClasses | Integer | CSV | Classes taught this period |
| 4 | FinalizationDate | Date | CSV | Date all classes were finalized |
| 5 | Deadline | Date | CSV | Official Q1 deadline: 10/31/2025 |
| 6 | WeightErrors | Integer | CSV | Count of grade weight config errors |
| 7 | NotificationComplete | Integer (bool) | CSV | 1 = complete, 0 = incomplete |
| 8 | ReworkIncidents | Integer | CSV | Re-opened or resubmitted class events |
| 9 | AvgTimePerClass_min | Decimal | CSV | Avg minutes per class to finalize |
| 10 | DaysFromDeadline | Integer | Calculated | FinalizationDate − Deadline (days) |
| 11 | OnTime | Integer (bool) | Calculated | 1 if DaysFromDeadline ≤ 0 |
| 12 | WeightErrorFlag | Integer (bool) | Calculated | 1 if WeightErrors > 0 |

---

## Metric Derivation Reference

| Metric | Formula (from Cleaned Data) | Q1 Result |
|--------|-----------------------------|-----------|
| M-01 Finalization completion rate | `SUM(OnTime) / COUNT(TeacherID) × 100` | 83.3% |
| M-02 Weight error rate | `SUM(WeightErrors) / COUNT(TeacherID)` | 0.28 |
| M-03 Notification compliance rate | `SUM(NotificationComplete) / COUNT(TeacherID) × 100` | 66.7% |
| M-04 Avg time-to-finalize per class | `AVERAGE(AvgTimePerClass_min)` | 8.4 min |
| M-05 Rework incident rate | `SUM(ReworkIncidents) / COUNT(TeacherID)` | 0.39 |

---

*Power Query steps documented from `baseline-dataset.xlsx`. M query tested against `Q1-finalization-export.csv` (18 rows, Q1 deadline 10/31/2025).*
