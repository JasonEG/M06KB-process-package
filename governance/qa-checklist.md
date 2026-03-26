# QA Checklist — Process Package Review

**Version:** 1.0
**Published:** 2026-03-26
**DRI:** Jason Geanuracos, Process Documentation Lead
**Next Review Date:** 2027-02-16 (or upon PowerSchool UI change / grading policy update)
**Applies to:** All artifacts in the Grade Finalization Process Package (M06KB-process-package)

> This checklist is a reusable template for reviewing the process package before any publication, submission, or scheduled governance review. Complete all sections. Record the reviewer name, date, and outcome at the bottom. Do not publish or submit until all items are marked Pass or explicitly accepted with a documented exception.

---

## Section 1 — SOP Structure

Verify that the SOP contains all required sections in the correct order.

| # | Check | Pass / Fail / N/A | Notes |
|---|-------|-------------------|-------|
| 1.1 | Purpose section is present and describes the goal of the process | | |
| 1.2 | Scope section defines start trigger, end state, in-scope items, and out-of-scope items | | |
| 1.3 | Roles & Responsibilities section is present and lists all actors | | |
| 1.4 | Prerequisites section identifies required access, tools, and information | | |
| 1.5 | Procedure section contains numbered, sequential steps with actor labels | | |
| 1.6 | Exceptions / error handling section is present | | |
| 1.7 | Glossary reference is present or inline terms are defined | | |
| 1.8 | Change log reference is present (inline or linked to CHANGELOG.md) | | |

---

## Section 2 — Clarity & Completeness

Verify that the SOP is unambiguous and complete enough for a new staff member to follow without assistance.

| # | Check | Pass / Fail / N/A | Notes |
|---|-------|-------------------|-------|
| 2.1 | Steps are sequential with no gaps in the procedure | | |
| 2.2 | All decision points include explicit Yes/No branches with clear outcomes | | |
| 2.3 | No ambiguous language (e.g., "as needed", "when appropriate") without a defined condition | | |
| 2.4 | Each step has a named actor (Teacher, Secretary, Principal) | | |
| 2.5 | All system references (menu names, button labels) match current PowerSchool UI | | |
| 2.6 | All role names are consistent across sections (no [TBD] or conflicting labels) | | |

---

## Section 3 — Diagram Alignment

Verify that the BPMN and Mermaid diagrams match the SOP procedure exactly.

| # | Check | Pass / Fail / N/A | Notes |
|---|-------|-------------------|-------|
| 3.1 | Number of steps in SOP matches number of nodes in diagrams | | |
| 3.2 | Decision points in SOP match decision diamonds in diagrams | | |
| 3.3 | All swim lane / role assignments in diagrams match the Roles section of the SOP | | |
| 3.4 | No orphaned nodes (nodes with no inbound or outbound connections) | | |
| 3.5 | Start and end events are present and correctly placed | | |
| 3.6 | Diagram source files (`.bpmn`, `.mmd`) and rendered files (`.png`, `.svg`) are in sync | | |

---

## Section 4 — Redaction & Sensitivity Review

Verify that no sensitive data is present in any artifact intended for external distribution or submission.

| # | Check | Pass / Fail / N/A | Notes |
|---|-------|-------------------|-------|
| 4.1 | No real staff names in published Markdown source files (unless intentional attribution) | | |
| 4.2 | No real student names or IDs in any artifact | | |
| 4.3 | No credentials, passwords, or session tokens in any artifact | | |
| 4.4 | Screenshots reviewed — real names, emails, and profile photos redacted or confirmed absent | | |
| 4.5 | CSV / dataset files confirmed to contain mock data only (no real identifiers) | | |
| 4.6 | Redaction evidence table in `governance/redaction-data-handling-plan.md` is current | | |
| 4.7 | No unredacted artifacts included in the submission package (A10/) | | |

---

## Section 5 — Link & Reference Validation

Verify that all internal cross-references and external links resolve correctly.

| # | Check | Pass / Fail / N/A | Notes |
|---|-------|-------------------|-------|
| 5.1 | All internal Markdown links (e.g., `[SOP](docs/source/SOP_v1.md)`) resolve to existing files | | |
| 5.2 | All screenshot references in KB_Page.md point to files that exist in `artifacts/screenshots/` | | |
| 5.3 | All OP codes referenced in SOP_v1_annotated.md exist in improvement-backlog-v1.md | | |
| 5.4 | PDF exports exist for all source files that require them | | |
| 5.5 | PDF exports are current — regenerated after any source file change | | |
| 5.6 | README Source of Truth table includes all current artifacts | | |

---

## Section 6 — Version & Governance Metadata

Verify that all primary artifacts carry required governance metadata.

| # | Check | Pass / Fail / N/A | Notes |
|---|-------|-------------------|-------|
| 6.1 | `docs/source/SOP_v1.md` has version number, published date, DRI, next review date, and change summary | | |
| 6.2 | `docs/source/SOP_v1_annotated.md` has the same governance block | | |
| 6.3 | `diagrams/bpmn/process.bpmn` has governance comment block (DRI, version, review date, change summary) | | |
| 6.4 | `diagrams/mermaid/process.mmd` has governance comment block (DRI, version, review date, change summary) | | |
| 6.5 | `governance/governance-plan.md` has version, DRI, and next review date | | |
| 6.6 | `governance/redaction-data-handling-plan.md` has version, DRI, and next review date | | |
| 6.7 | `governance/change-log-table.md` is current through the latest package version | | |
| 6.8 | `CHANGELOG.md` has an entry for every version listed in the change log table | | |

---

## Section 7 — Approval Sign-Off

Verify that the DRI has reviewed and approved the package before publication or submission.

| # | Check | Pass / Fail / N/A | Notes |
|---|-------|-------------------|-------|
| 7.1 | DRI has reviewed all artifacts in this checklist | | |
| 7.2 | All Fail items from prior sections are resolved or have a documented exception | | |
| 7.3 | CHANGELOG.md has an entry for the current version with date and author | | |
| 7.4 | Submission package (A10/) contains only redacted, final versions of all deliverables | | |
| 7.5 | DRI sign-off recorded below before package is submitted or published | | |

---

## Review Record

| Field | Value |
|-------|-------|
| Reviewer | |
| Review Date | |
| Package Version Reviewed | |
| Overall Outcome | Pass / Fail / Pass with Exceptions |
| Exceptions (if any) | |
| DRI Sign-Off | |

---

*This checklist template is maintained by the DRI. For governance policy, see `governance/governance-plan.md`. For redaction rules, see `governance/redaction-data-handling-plan.md`.*
