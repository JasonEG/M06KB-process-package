# M10 Artifact Audit Notes — Step 1

**Date:** 2026-03-24
**Module:** M10 — Governance Package
**Purpose:** Internal reference — findings from pre-authoring artifact scan. Used to populate governance-plan.md (Step 2), redaction-data-handling-plan.md (Step 3), and qa-checklist.md (Step 6).

---

## Screenshots — Primary Risk Area

| File | Risk | Findings |
|------|------|----------|
| `Email Sent screen.png` | **HIGH — action required** | Real full name ("Jason Geanuracos"), real email (`jgeanuracos@clsdraiders.org`), recipient first name ("Kathy"), profile photo visible |
| `Gradebook screen.png` | **MEDIUM — pending human review** | Shows Score Sheet with student rows; class name "8(A) Intro to Steam" visible. Confirm no readable student names in leftmost column before including in A10 |
| `Tradional Grade Calc menu screen.png` | Low | Class name only — no PII |
| `Qtr weights screen.png` | Low | Class/term info only — no PII |
| `Weights screen.png` | Low | Category settings only — no PII |
| `Semester Weights screen.png` | Low | Term weighting only — no PII |
| `Qtr final grade status screen.png` | Clear | Modal dialog only — no PII |
| `S1 Final Grade status screen.png` | Clear | Modal dialog only — no PII |

**Required action before A10:** Redact `Email Sent screen.png` (blur or replace name, email, recipient name, and profile photo). Confirm `Gradebook screen.png` visually before including.

---

## Markdown Source Files — Sensitive Data

| Artifact | Sensitive items found | Classification |
|----------|-----------------------|----------------|
| `docs/source/KB_Page.md` | Real system URL (`ps-co.metasolutions.net`), real IT Help Desk URL (autotask.net with org-specific params), real email (`jgeanuracos@clsdraiders.org`), full name | Internal |
| `docs/source/Quick_Reference.md` | Same system URL, same IT Help Desk URL, real email | Internal |
| `docs/source/Checklist.md` | Real system URL (`ps-co.metasolutions.net`) | Internal |
| `docs/source/SOP_v1.md` | None — no URLs, no email, no names in procedure text | Internal |
| `docs/source/SOP_v1_annotated.md` | Author name ("Jason Geanuracos") — intentional attribution, not a risk | Internal |
| `artifacts/examples/walkthrough-outline.md` | None | Internal |
| `measurement/measurement-plan.md` | None — T-codes only, explicitly documented as mock | Internal |
| `measurement/data/Q1-finalization-export.csv` | **Confirmed clear** — T001–T018 only, no real names | Internal |

The URLs and email in KB_Page / Quick_Reference / Checklist are real but appropriate for internal staff-facing documents. They are not PII risks. Classified as Internal and noted in the redaction plan.

---

## Governance Metadata Gaps

Every source artifact is missing the governance block (DRI, version, next review date). This is expected and will be resolved in Steps 4 and 6.

| Artifact | Gap |
|----------|-----|
| `docs/source/SOP_v1.md` | No DRI, no next review date, no governance block — v1.5 → needs v1.6 block |
| `docs/source/SOP_v1_annotated.md` | Same |
| `docs/source/KB_Page.md` | Has process owner and review cycle rows but no formal governance block |
| `docs/source/Quick_Reference.md` | No governance metadata |
| `docs/source/Checklist.md` | No governance metadata |
| `diagrams/bpmn/process.bpmn` | No DRI/version comment block |
| `diagrams/mermaid/process.mmd` | No DRI/version comment |

---

## Summary

- **One definite redaction action:** `Email Sent screen.png` — must be redacted before A10 export
- **One item pending human review:** `Gradebook screen.png` — confirm no readable student names
- **No PII in any Markdown source file** — CSV confirmed mock data only
- **All remaining screenshots clear** — class names visible but not sensitive
- **Governance gaps are uniform** across all source files — resolved in Steps 4 and 6
- **Classification:** All Markdown docs = Internal; diagrams = Public; screenshots = Confidential (redact before submission)

---

*Internal audit notes — not a submission artifact. For A10 deliverables see governance-plan.md, redaction-data-handling-plan.md, and qa-checklist.md.*
