# Prompt Log — Week 12: Capstone

**Module:** 12 — Capstone Project (Track A: Consultant)
**Deliverable:** Full process package for partner's real-world process (SOP, BPMN diagram, governance documentation)
**Partner:** Abbey Cohen
**Subject process:** In-Home Dog Boarding Intake and Care
**Due:** (check Canvas)

---

## Entry 39 — 2026-04-05 — Capstone Setup and Process Outline Review

**Prompt summary:** Session focused on capstone organization setup. User confirmed Track A (Consultant), partner Abbey Cohen confirmed. Abbey submitted her dog boarding process outline as a PDF. Analyzed outline and confirmed it is usable as-is for full deliverable build.

**Actions taken:**
- Confirmed Track A selection and partner (Abbey Cohen) from prior session context
- Deleted `capstone/project-brief.md` (no longer needed)
- Located and read `capstone/Sample Process Outline DOG BOARDING.pdf` — Abbey's submission
- Analyzed outline: 9 phases, clear trigger/end state, decision points at Phases 1/3/6, exception handling in Phases 2/7, role and inputs defined
- Identified one gap: Phase 3 (Meet & Greet) marked "if applicable" — needs decision branch clarification in BPMN
- Confirmed outline is complete enough to build SOP, BPMN, and governance directly from it
- Created `prompt-log/week12-capstone-log.md` (this file)
- Added v2.0.0 entry to `CHANGELOG.md`

**Files created this session:**
- `prompt-log/week12-capstone-log.md` — This log (Entry 39)

**Files modified this session:**
- `CHANGELOG.md` — v2.0.0 entry added

**Outcome:** Organization established. Ready to build capstone deliverables from Abbey's process outline.

---

## Entry 40 — 2026-04-07 — Module 13 Setup: Discovery Notes, SOP v1.0, Prompt Log Consolidation

**Prompt summary:** User provided Module 13 instructions (Track A: discovery + drafting). Confirmed Week 12 Canvas submission complete (partner name, project description, Track A selection). Reviewed Abbey's process outline PDF in full. Built three new artifacts: discovery notes, SOP v1.0, and consolidated this prompt log. Renamed this file from `week12-capstone-log.md` to `capstone-log.md` to cover the full capstone arc (Weeks 12–15).

**Actions taken:**
- Read Module 13 instructions — confirmed Track A deliverables: discovery notes + draft SOP + rough BPMN by end of week
- Confirmed Week 12 Canvas submission complete (no action needed)
- Read Abbey's `Sample Process Outline DOG BOARDING.pdf` — all 9 phases, 2 pages
- Renamed `prompt-log/week12-capstone-log.md` → `prompt-log/capstone-log.md` via git mv
- Created `capstone/discovery-notes.md` — phase analysis, gap/decision table, open questions for Abbey, BPMN notes, AI usage log
- Created `capstone/SOP.md` (v1.0) — 9 steps, 3 roles, 6 exceptions, governance header, decision callouts at Steps 1/3/6

**Files created this session:**
- `capstone/discovery-notes.md` — Source analysis, gaps G-01 through G-05, BPMN notes, open questions
- `capstone/SOP.md` — Full SOP v1.0

**Files renamed this session:**
- `prompt-log/week12-capstone-log.md` → `prompt-log/capstone-log.md`

**AI tool usage:**
- **Tool:** Claude Code (claude-sonnet-4-6)
- **Tasks:** PDF analysis, gap identification, drafting discovery notes, drafting SOP v1.0
- **Quality check:** All content traced to Abbey's outline; Gap G-01 (meet and greet gateway) and G-03 (Phase 7 as subprocess) are consultant judgment calls documented explicitly in discovery notes

**Outcome:** M13 Week 1 deliverables complete. SOP v1.0 draft ready for Abbey's review. BPMN diagram is next.
