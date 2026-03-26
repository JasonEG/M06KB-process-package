# Governance Plan — Grade Finalization Process Package

**Version:** 1.0
**Published:** 2026-03-24
**DRI:** Jason Geanuracos, Process Documentation Lead
**Next Review Date:** 2027-02-16 (or upon PowerSchool UI change, grading policy update, or documented error in SOP)
**Applies to:** All artifacts in the Grade Finalization Process Package (M06KB-process-package)

---

## 1. Purpose

This governance plan establishes the minimum viable governance structure for the Grade Finalization Process Package. It defines who is responsible for keeping the process documentation accurate, how often it is reviewed, how changes are approved and recorded, and what escalation paths exist when issues arise.

---

## 2. Directly Responsible Individual (DRI)

| Field | Value |
|-------|-------|
| **Name** | Jason Geanuracos |
| **Role** | Process Documentation Lead |
| **Responsibilities** | Maintain SOP accuracy; schedule and conduct reviews on cadence and upon trigger events; approve or reject proposed changes; maintain the change log; escalate issues per Section 6 |

The DRI is the single accountable owner for this process package. All questions about the documentation, proposed changes, and review scheduling are directed to the DRI.

---

## 3. RACI

| Activity | DRI | IT Operations | Building Admin | Dept Head |
|----------|-----|---------------|----------------|-----------|
| Maintain and update SOP | **R/A** | C | C | — |
| Review on scheduled cadence | **R/A** | — | C | — |
| Approve minor changes (formatting, clarification) | **A** | — | — | — |
| Approve major changes (scope, roles, policy) | **R** | C | C | **A** |
| Escalate compliance or data issues | **R** | **A** | — | C |
| Publish updated artifacts | **R/A** | — | — | — |

**Key:** R = Responsible, A = Accountable, C = Consulted, — = Not involved

---

## 4. Review Cadence

### Routine Reviews

The process package is reviewed on a **semi-annual schedule** — once every six months — aligned to the academic calendar:

| Review Window | Target Date |
|---------------|-------------|
| Mid-year review | January 2027 |
| End-of-year review | July 2027 |
| Next formal review deadline | **2027-02-16** |

### Trigger-Based Reviews

An immediate out-of-cycle review is required if any of the following occurs:

- PowerSchool UI changes that affect documented steps or screenshots
- A grading policy update that changes roles, timing, or procedures
- A new compliance or data privacy requirement affecting stored artifacts
- A documented error in the SOP reported by a staff member or administrator
- A failed QA checklist review

Trigger-based reviews are initiated by the DRI within **five business days** of the triggering event.

---

## 5. Change Control

All changes to artifacts in this process package follow this workflow:

1. **Request** — A change is identified by the DRI, IT Operations, or building administration
2. **DRI review** — DRI evaluates the change against current SOP, diagrams, and related artifacts
3. **Consultation** — If the change affects system configuration (IT Operations) or grading policy (Building Admin), those parties are notified and given opportunity to review
4. **Approval** — Minor changes (formatting, typo correction, clarification) are approved by the DRI alone. Major changes (scope, roles, policy impact) require Dept Head sign-off
5. **Documentation** — An entry is added to `CHANGELOG.md` and the governance change log table (`governance/change-log-table.md`) with: version, date, author, summary, and reason
6. **Version bump** — The artifact version is incremented following semantic versioning conventions (patch for minor fixes, minor for content changes, major for scope changes)
7. **Publication** — Updated artifacts are committed to the repository; exported PDFs are regenerated for any modified source files

---

## 6. Escalation

| Situation | Step 1 | Step 2 | Step 3 |
|-----------|--------|--------|--------|
| Error in SOP or documentation | DRI corrects and documents in change log | — | — |
| Disputed change (content or scope) | DRI documents dispute and rationale | Escalate to Dept Head for decision | — |
| Compliance or data privacy risk | DRI documents risk and initiates review | Escalate to IT Operations | Escalate to compliance lead if unresolved |
| System change breaks documented procedure | DRI initiates trigger review within 5 days | Consult IT Operations on updated behavior | Publish revised SOP before next finalization window |

---

## 7. Sunset and Refresh

This process package has a **12-month active review commitment** from its publication date.

| Milestone | Date |
|-----------|------|
| Package published | 2026-02-16 |
| Governance layer added | 2026-03-24 |
| Next scheduled review | 2027-02-16 |
| Sunset evaluation | 2027-02-16 — DRI determines whether to renew, archive, or deprecate |

If PowerSchool is replaced or the grade finalization process is fundamentally restructured before the sunset date, the DRI initiates a trigger review and updates this plan accordingly. At the sunset evaluation, the DRI documents the decision (renew, archive, or deprecate) in the change log.

---

*This governance plan applies to all artifacts in the Grade Finalization Process Package as listed in README.md. For the full artifact change history, see CHANGELOG.md and governance/change-log-table.md.*
