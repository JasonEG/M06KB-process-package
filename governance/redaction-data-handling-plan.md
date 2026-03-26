# Redaction & Data Handling Plan — Grade Finalization Process Package

**Version:** 1.0
**Published:** 2026-03-24
**DRI:** Jason Geanuracos, Process Documentation Lead
**Next Review Date:** 2027-02-16
**Applies to:** All artifacts in the Grade Finalization Process Package (M06KB-process-package)

---

## 1. Purpose

This plan defines how sensitive data is identified, classified, redacted, stored, and accessed within the Grade Finalization Process Package. It ensures that no personally identifiable information (PII), credentials, or live system data are exposed in published or submitted artifacts.

---

## 2. Data Classification Tiers

| Tier | Definition | Examples in this package |
|------|-----------|--------------------------|
| **Public** | Safe for external distribution without restriction | SOP procedure text, diagrams (no data), QA checklist |
| **Internal** | Appropriate for staff use; not for external distribution | KB_Page.md, Quick_Reference.md, Checklist.md, measurement plan |
| **Confidential** | Contains sensitive data; must be redacted before any external sharing | Screenshots showing PowerSchool UI with real names, emails, or profile photos |
| **Restricted** | Must remain local; do not commit to public repo or share with third-party AI tools | Raw unredacted screenshots containing live system data or real identifiers |

---

## 3. Redaction Rules

When sensitive data is found in an artifact, apply the following substitution rules before publishing or submitting:

| Data Type | Redaction Token |
|-----------|----------------|
| Real teacher or staff full name | `[STAFF_NAME]` |
| Real email address | `[EMAIL_REDACTED]` |
| Real recipient name (first name only) | `[RECIPIENT_NAME]` |
| Profile photo or avatar | Blur or replace with `[PHOTO_REDACTED]` |
| Student name or ID | `[STUDENT_ID]` |
| System credentials or passwords | `[CREDENTIAL_REDACTED]` |
| Real system login URL | `[SYSTEM_URL]` |
| Real external vendor URL with org-specific parameters | `[VENDOR_URL]` |
| PowerSchool login screen data | Blur or label `[SCREENSHOT_REDACTED: login screen]` |

Redaction tokens must be visible and legible in the published artifact — do not use white text on white background or otherwise obscure that a redaction occurred.

---

## 4. Storage & Access

| Item | Location | Access |
|------|----------|--------|
| Source of truth (all artifacts) | Git repo: `https://github.com/JasonEG/M06KB-process-package.git` | Repo owner only (private) |
| Local working copy | `\\COLUM-FILE\Faculty\jgeanuracos\Desktop\UC Teach\IT7039 SS\M06 KB\process-package\` | DRI only |
| Exported PDFs for submission (A10/) | Same repo, `A10/` folder | Redacted versions only — safe to submit |
| Raw screenshots (pre-redaction, if any) | Local working copy only | Do not commit to repo if they contain live PII |
| Teacher ID-to-name mapping (if used) | Held by Process Owner only; not in this dataset | Not stored in repo |

---

## 5. Audit Logging

Formal system-level access logging is not available for this process package (no DMS or access management system is in use). In place of automated logging, the following manual audit record is maintained:

| Log Type | What Is Recorded | Where | Frequency |
|----------|-----------------|-------|-----------|
| Artifact review log | Which artifacts were reviewed, by whom, on what date, and what was found | Section 6 of this document (review table) | Each governance review cycle and upon trigger events |
| Change log | Every version change — version number, date, author, summary, reason | `CHANGELOG.md` and `governance/change-log-table.md` | Each time an artifact is modified |
| Redaction status | Whether each artifact was inspected for sensitive data and what action was taken | Section 6 of this document (review table) | Each governance review cycle |

The DRI is responsible for keeping these records current. If this process package is adopted in a system with access logging capability (e.g., SharePoint, Confluence, a DMS), system-level access logs should be enabled and reviewed as part of each scheduled review.

---

## 6. AI Tool Handling

- Do not paste unredacted screenshots or real names into AI tools (including Claude Code)
- Share only redacted Markdown text for AI-assisted review
- The mock CSV dataset (T001–T018) is safe to share with AI tools — it contains no real names
- System URLs in Markdown source files are real but not sensitive credentials; sharing for documentation review is acceptable

---

## 7. Redaction Evidence — Artifact Review Table

The following table records the outcome of the Step 1 artifact audit (2026-03-24). Each artifact was reviewed for sensitive data. Status reflects action taken or confirmed.

### Markdown Source Files

| Artifact | Reviewed | Sensitive Data Found | Action Taken | Status |
|----------|----------|----------------------|--------------|--------|
| `docs/source/SOP_v1.md` | ✅ 2026-03-24 | None | None required | Clear |
| `docs/source/SOP_v1_annotated.md` | ✅ 2026-03-24 | Author name (intentional attribution) | None — intentional | Clear |
| `docs/source/KB_Page.md` | ✅ 2026-03-24 | Real system URL, IT Help Desk URL, real email, full name | Classified Internal; acceptable for staff-facing use; no redaction required for internal distribution | Internal — no redaction needed |
| `docs/source/Quick_Reference.md` | ✅ 2026-03-24 | Real system URL, IT Help Desk URL, real email | Same as KB_Page.md | Internal — no redaction needed |
| `docs/source/Checklist.md` | ✅ 2026-03-24 | Real system URL | Same as above | Internal — no redaction needed |
| `artifacts/examples/walkthrough-outline.md` | ✅ 2026-03-24 | None | None required | Clear |
| `measurement/measurement-plan.md` | ✅ 2026-03-24 | None — T-codes only, explicitly documented as mock | None required | Clear |
| `measurement/data/Q1-finalization-export.csv` | ✅ 2026-03-24 | None — T001–T018 anonymous IDs only; no real names | None required | Clear |
| `diagrams/bpmn/process.bpmn` | ✅ 2026-03-24 | None | None required | Clear |
| `diagrams/mermaid/process.mmd` | ✅ 2026-03-24 | None | None required | Clear |

### Screenshots

| File | Reviewed | Sensitive Data Found | Action Required Before A10 | Status |
|------|----------|----------------------|----------------------------|--------|
| `Email Sent screen.png` | ✅ 2026-03-24 | Real full name, real email address, recipient first name, profile photo | **Redact before A10 export** — blur or replace name, email, recipient name, and profile photo | ⚠️ Pending redaction |
| `Gradebook screen.png` | ✅ 2026-03-24 | Class name visible; student name column present but not confirmed readable at audit resolution | **Requires human visual confirmation** — if student names are readable, redact before A10 | ⚠️ Pending confirmation |
| `Tradional Grade Calc menu screen.png` | ✅ 2026-03-24 | Class name only ("8(A) Intro to Steam") — not PII | None required | Clear |
| `Qtr weights screen.png` | ✅ 2026-03-24 | Class/term info only — not PII | None required | Clear |
| `Weights screen.png` | ✅ 2026-03-24 | Class/term info only — not PII | None required | Clear |
| `Semester Weights screen.png` | ✅ 2026-03-24 | Class/term info only — not PII | None required | Clear |
| `Qtr final grade status screen.png` | ✅ 2026-03-24 | None — modal dialog only | None required | Clear |
| `S1 Final Grade status screen.png` | ✅ 2026-03-24 | None — modal dialog only | None required | Clear |

---

## 8. Open Redaction Items

Two items require action before the A10 submission package is finalized:

| # | Item | Action | Owner |
|---|------|--------|-------|
| 1 | `Email Sent screen.png` | Redact real name, email, recipient name, and profile photo before including in A10 | DRI |
| 2 | `Gradebook screen.png` | Visually confirm no readable student names; redact if present before including in A10 | DRI |

These items are tracked here and in `governance/audit-notes.md`. Step 7 (A10 package assembly) must not proceed until both items are resolved.

---

*This plan was authored based on the Step 1 artifact audit completed 2026-03-24. For full audit findings see `governance/audit-notes.md`.*
