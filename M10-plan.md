# M10 Execution Plan — Governance Package

**Module:** 10 — Governance & Privacy (Canvas: Module 11)
**Deliverable:** A10 — Governance Package
**Due:** Sunday, March 29, 2026 by 11:59 PM ET
**Graded artifact:** Governance plan + redaction plan + updated SOP/diagram + change log + QA checklist

---

## Assignment Summary

Add a minimum viable governance structure to the existing PowerSchool grade finalization process package. This is not a new artifact stack — it is a governance layer on top of what already exists.

Five deliverables:
1. **Governance plan** (1–2 pages) — DRI, RACI, review cadence, change control, sunset date, escalation
2. **Redaction & data handling plan** — classification, redaction rules, storage, access, audit logging + evidence of redaction applied to artifacts
3. **Updated SOP and diagram headers** — add governance block (DRI, version, next review date, change summary) to SOP_v1.md and diagram source files
4. **Comprehensive change log** — formalize existing CHANGELOG into a table: Version / Date / Author / Summary / Reason for change
5. **Repeatable QA checklist** — standalone template covering structure, clarity, diagram alignment, redaction, link validation, approval sign-off

---

## Execution Steps

### Step 1 — Artifact audit (20 min)
Scan all existing artifacts for governance gaps and sensitive data before writing anything.

**Artifacts to scan:**
- `docs/source/SOP_v1.md` — governance header gaps, sensitive data
- `docs/source/SOP_v1_annotated.md` — same
- `docs/source/KB_Page.md`, `Quick_Reference.md`, `Checklist.md`
- `diagrams/bpmn/process.bpmn`, `diagrams/mermaid/process.mmd`
- `artifacts/screenshots/` — highest redaction risk (real PowerSchool UI)
- `artifacts/examples/walkthrough-outline.md`
- `measurement/data/Q1-finalization-export.csv` — mock data, but confirm no real names
- `measurement/measurement-plan.md`

**Flag for each artifact:**
- Missing governance metadata (version, DRI, review date)
- Sensitive data patterns (real names, credentials, URLs, student/teacher IDs, email addresses)
- Anything that should not leave the local environment

**Output:** Internal audit notes — used to populate Steps 2 and 3.

---

### Step 2 — Governance plan (30 min)
Create `governance/governance-plan.md` (1–2 pages).

**Required elements:**

| Element | Content |
|---------|---------|
| DRI | Process Documentation Lead (Jason Geanuracos) — responsible for accuracy, version control, review scheduling, and change approvals |
| Responsibilities | Keep SOP current; review on cadence and upon trigger events; approve changes; maintain change log; escalate issues |
| RACI | DRI = Accountable/Responsible; IT Ops = Consulted (system changes); Building Admin = Consulted (policy changes); Dept Head = Approver for major revisions |
| Review cadence | Routine: semi-annual (every 6 months). Trigger-based: immediate review if PowerSchool UI changes, grading policy updates, new compliance requirements, or documented error in SOP |
| Change control | Request → DRI review → Consulted parties notified if needed → Approver sign-off for major changes → CHANGELOG entry → version bump → publish updated copy |
| Sunset/refresh date | 12 months from publication date (2026-02-16 → next review by 2027-02-16) |
| Escalation | Step 1: DRI corrects and documents. Step 2: If disputed or policy-impacting, escalate to Dept Head. Step 3: If compliance or data risk, escalate to IT/compliance lead |

---

### Step 3 — Redaction & data handling plan (30 min)
Create `governance/redaction-data-handling-plan.md`.

**Classification tiers for this process package:**

| Tier | Definition | Examples in this package |
|------|-----------|--------------------------|
| Public | Safe for external distribution | SOP procedures, diagrams (no data), QA checklist |
| Internal | Appropriate for staff, not external | KB_Page.md, Quick_Reference.md, measurement plan |
| Confidential | Restricted — redact before sharing externally | Screenshots (PowerSchool UI), any real teacher/student names |
| Restricted | Must stay local; do not pass to third-party AI tools | Raw screenshots before redaction audit |

**Redaction rules:**
- Real teacher names → `[TEACHER_NAME]` or `[TEACHER_ID: T###]`
- Real student names/IDs → `[STUDENT_ID]`
- System credentials / passwords → `[CREDENTIAL_REDACTED]`
- Real email addresses → `[EMAIL_ADDRESS]`
- Real system URLs → `[SYSTEM_URL]`
- PowerSchool login screen data → blur or label `[SCREENSHOT_REDACTED: login screen]`

**Storage & access:**
- Source of truth: Git repo (`https://github.com/JasonEG/M06KB-process-package.git`)
- Local working copy: `\\COLUM-FILE\Faculty\jgeanuracos\Desktop\UC Teach\IT7039 SS\M06 KB\process-package\`
- Exported PDFs (A10/ folder): shareable — must be redacted versions only
- Raw screenshots (pre-redaction): local only, not committed to repo if they contain live data

**AI tool handling:**
- Do not paste unredacted screenshots or real names into AI tools
- Share only redacted Markdown text for AI-assisted review

**Evidence of redaction applied:** Audit table in the plan confirming which artifacts were reviewed and any redactions made or confirmed clear.

---

### Step 4 — Update SOP and diagram headers (20 min)
Add a governance block to `docs/source/SOP_v1.md` immediately below the existing version/date header.

**Governance block to add:**

```
**Version:** 1.6
**Published:** 2026-02-16
**DRI:** Jason Geanuracos, Process Documentation Lead
**Next Review Date:** 2027-02-16 (or upon PowerSchool UI change / grading policy update)
**Change Summary:** v1.6 adds governance header, redaction verification, and QA checklist reference. See CHANGELOG for full history.
```

Also update `docs/source/SOP_v1_annotated.md` with the same block.

For diagrams: add DRI and version in a comment block in `process.bpmn` and `process.mmd` source files.

---

### Step 5 — Formalize change log (20 min)
The existing `CHANGELOG.md` is detailed but in prose/header format. The assignment requires a table format.

**Action:** Add a new `governance/change-log-table.md` with a formal table summarizing all major versions:

| Version | Date | Author | Summary | Reason |
|---------|------|--------|---------|--------|
| 1.0 | ... | ... | ... | ... |

Pull from existing CHANGELOG.md — no need to rewrite history, just reformat as a governance-facing table. Include versions 1.0 through 1.6 (new governance version).

Note: `CHANGELOG.md` at the repo root remains the running developer log. The governance table is the submission-facing summary.

---

### Step 6 — QA checklist (20 min)
Create `governance/qa-checklist.md` — a reusable template, not specific to this process.

**Sections:**
1. SOP structure (required sections present: Purpose, Scope, Roles, Steps, Glossary ref, Change log ref)
2. Clarity & completeness (steps are sequential, decision points explicit, no ambiguous language)
3. Diagram alignment (SOP steps map 1:1 to BPMN/Mermaid; no orphaned nodes; roles match)
4. Redaction & sensitivity review (no PII, credentials, or live system data in published artifacts)
5. Link & reference validation (no broken cross-references; PDF exports current)
6. Version & governance metadata (version number, DRI, review date present in all artifacts)
7. Approval sign-off (DRI sign-off recorded in change log before publication)

---

### Step 7 — A10 package + prompt log + wrap-up (20 min)
- Create `A10/` submission folder with clean-named copies of all deliverables
- Update `prompt-log/week10-governance-log.md` (Entry 35+)
- Update `README.md` — add `governance/` folder tree, `A10/`, Source of Truth entries
- Update `CHANGELOG.md` (v1.9.0)
- Update `CLAUDE.md` with M10 completion status
- Commit and push

---

## Submission Checklist

- [ ] `governance/governance-plan.md` — DRI, RACI, cadence, change control, sunset, escalation
- [ ] `governance/redaction-data-handling-plan.md` — classification, rules, storage, access, redaction evidence table
- [ ] `docs/source/SOP_v1.md` — governance block added (v1.6)
- [ ] `docs/source/SOP_v1_annotated.md` — governance block added
- [ ] `governance/change-log-table.md` — formal version table (v1.0 → v1.6)
- [ ] `governance/qa-checklist.md` — reusable template
- [ ] `A10/` — submission package (PDFs + prompt log)
- [ ] Prompt log updated (Entry 35+)
- [ ] README, CHANGELOG, CLAUDE.md updated
- [ ] Committed and pushed

---

## Key Decisions (Pre-Made)

- **DRI:** Named individual role (Jason Geanuracos, Process Documentation Lead) — not a committee
- **RACI:** Kept minimal — 3 parties total (DRI, IT Ops, Dept Head). No approval committee.
- **Review cadence:** Semi-annual routine + event-based triggers. Matches the risk level of an internal school process.
- **Redaction stance:** Screenshots are the primary risk. CSV mock data is already anonymized (T001–T018, no real names). Markdown source files have no PII.
- **Change log:** Keep existing CHANGELOG.md as-is; add governance table as a separate submission artifact.
- **Governance plan length:** Target 1.5 pages. No padding.
- **SOP version bump:** v1.5 → v1.6 for governance header addition (minor, not a content change)

---

## Notes

- Do not over-engineer. This is minimum viable governance for a student process package, not an enterprise compliance framework.
- The process package already has strong version history, a detailed CHANGELOG, and no real PII in Markdown source. The work here is mostly structure and formalization.
- Screenshots are the one genuine redaction risk — audit those carefully in Step 1.
- Prompt log is internal only (not a submission requirement, but keep it updated).
