# Week 11 Discussion — SaaS vs. On-Prem Tradeoffs

**Status:** Draft v2 (hybrid framing)
**Last updated:** 2026-03-27

---

## Initial Post

My Grade Finalization process runs across two distinct layers, each with a different architecture — making this a **hybrid** design by deliberate choice.

The **operational tool** is PowerSchool, hosted by Meta Solutions (a third-party managed provider at `ps-co.metasolutions.net`). This layer is **SaaS by constraint** — the district has no on-prem alternative. Grade data, teacher rosters, and finalization workflows all live on vendor infrastructure outside district control.

The **SOP and governance documentation** — the process package, data handling plan, change log, and QA checklist — are maintained **on-premises**: on a district network drive (`\\COLUM-FILE\Faculty\...`) and in a private GitHub repository. This is a deliberate governance decision. Because the operational tool is SaaS and outside my control, the documentation layer is the only part of this process I actually own. Keeping it local means I control access, versioning, and audit records.

This hybrid design surfaces three governance risks I've addressed directly:

1. **Vendor data custody** — Student PII lives on Meta Solutions' infrastructure. My compensating control is a tiered data classification policy (Public / Internal / Confidential / Restricted) that prohibits sharing Confidential artifacts outside approved channels and bars unredacted data from any third-party tool.

2. **SOP drift** — PowerSchool's UI is vendor-controlled; an update can silently break documented steps. Per NIST AI RMF GOVERN principles, I compensate with a trigger-based review policy requiring the DRI to initiate an out-of-cycle review within five business days of any platform change.

3. **Documentation access gaps** — The on-prem network drive has no automated access logging. I compensate with manual audit records: a governance change log, a DRI-owned redaction evidence table, and a QA checklist with a signed review record.

The core insight: keeping sensitive data local while using the cloud tool for operations is not just a technical tradeoff — it's a governance boundary.

---

## Peer Responses

*(To be added after reading classmates' posts)*

---

## Notes / Revision Ideas

- Could add OWASP LLM risk reference if professor expects it (prompt injection / data leakage re: Claude Code use)
- "The documentation layer is the only part of this process I actually own" is the strongest line — keep it
- Meta Solutions detail (`ps-co.metasolutions.net`) is a concrete, accurate data flow detail — leave it in
