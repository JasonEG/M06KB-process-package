# Prompt Log — Week 11: Discussion Post

**Module:** 11 — SaaS vs. On-Premises Tradeoffs (Canvas: Module 11 Discussion)
**Deliverable:** Discussion post — initial post + 2 peer responses
**Due:** (check Canvas)

---

## Entry 38 — 2026-03-27 — Week 11 Discussion Draft (SaaS vs. On-Prem)

**Prompt summary:** User needed to draft a Canvas discussion post on SaaS vs. on-prem tradeoffs, grounded in their actual process package. Session included clarifying the correct architecture through discussion, then drafting and revising the post.

**Actions taken:**
- User initially misunderstood architecture — thought to frame as pure SaaS
- Clarified PowerSchool URL (`ps-co.metasolutions.net`) confirms Meta Solutions managed hosting — SaaS by constraint, not direct PowerSchool cloud
- User clarified that SOP/documentation is maintained on-premises (network drive + private GitHub) — architecture is **hybrid**
- Drafted initial post (SaaS-only framing, ~230 words)
- Revised to hybrid framing: PowerSchool/Meta Solutions = SaaS (operational tool, district-mandated); network drive + GitHub = on-prem (documentation layer, deliberate governance decision)
- Key argument: the on-prem documentation layer is the compensating control for not owning the SaaS layer
- Three governance risks identified: vendor data custody (PII in Meta Solutions), SOP drift (vendor UI changes break documented steps), documentation access gaps (no automated logging on network drive)
- NIST AI RMF GOVERN principles referenced for trigger-based review policy

**Files created this session:**
- `discussions/week11-saas-vs-onprem.md` — Draft v2 (hybrid framing), ~245 words; peer response placeholder and revision notes included

**Files modified this session:**
- `CHANGELOG.md` — v1.9.1 entry added
- `CLAUDE.md` — Session summary added

**Outcome:** Discussion draft saved; ready to post to Canvas after final read-through. Peer responses to be added after classmates post.
