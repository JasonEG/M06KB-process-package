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

**Additional work — Step 6/7 escalation clarification:**
- Discussed Step 6 → Step 7 trigger ambiguity — three options presented (A: clear handoff trigger, B: Step 7 as triage hub, C: collapse into Step 6)
- User selected Option A
- Updated `capstone/SOP.md` Steps 6 and 7: Step 6 now handles only inline daily-loop resolutions; explicit trigger line added; Step 7 reframed as escalation path with Minor/Moderate/Emergency severity tiers
- SOP bumped to v1.1; governance header updated

**Files modified (additional):**
- `capstone/SOP.md` — v1.0 → v1.1 (Step 6/7 Option A escalation model)

**Outcome:** M13 Week 1 build complete. SOP v1.1 ready for Abbey's review. BPMN diagram is next.

---

## Entry 41 — 2026-04-09 — SOP Verification, G-02 Fix, BPMN Draft, PDF Export

**Prompt summary:** Session focused on pre-send QA of SOP v1.1 and building the BPMN diagram as a visual aid for Abbey's review. Verified SOP format and content against capstone requirements, applied one gap fix, built the full BPMN 2.0 file, and exported a PDF. Second BPMN layout pass completed to address box sizing and connector spacing; connector line cleanup deferred to next session.

**Actions taken:**
- Read `capstone/SOP.md` (v1.1), `capstone/README.md`, `capstone/discovery-notes.md`, and `docs/source/SOP_v1.md` (template reference)
- Ran full format verification: all 7 required SOP sections present; all 9 phases covered; gateways at Steps 1/3/6 confirmed; Step 7 escalation model confirmed; exceptions table confirmed
- Applied G-02 fix: Step 3 decision callout updated — "Established repeat client" now explicitly noted as at dog sitter's discretion
- Confirmed `bpmn-to-image` (v0.10.0) available globally
- Created `capstone/process.bpmn` — BPMN 2.0 XML with two swimlanes, all gateways, daily care loop, Step 7 escalation, two decline end events, one normal end event
- Generated `capstone/process.pdf` via bpmn-to-image (first pass: 100×80 tasks)
- Revised BPMN DI section: tasks increased to 160×90, gateways to 54×54, pool widened to 2800×600, all connector waypoints rerouted; regenerated PDF
- Connector line cleanup identified as needed; specific lines to be addressed next session

**Files created this session:**
- `capstone/process.bpmn` — Full BPMN 2.0 diagram
- `capstone/process.pdf` — PDF export of BPMN diagram

**Files modified this session:**
- `capstone/SOP.md` — G-02 discretion note added to Step 3 (still v1.1)
- `CHANGELOG.md` — v2.2.0 entry added

**AI tool usage:**
- **Tool:** Claude Code (claude-sonnet-4-6)
- **Tasks:** SOP format verification, G-02 gap fix, BPMN XML authoring, DI layout design, PDF export
- **Quality check:** SOP verified section-by-section against template and capstone requirements; BPMN process XML matches SOP logic exactly

**Outcome:** SOP v1.1 verified and ready. BPMN draft complete with PDF. Connector line cleanup is the only remaining layout task before sending to Abbey.

---

## Entry 42 — 2026-04-10 — BPMN Connector Cleanup, PDF Regeneration, Abbey Review Sent

**Prompt summary:** Session focused on resolving BPMN connector label visibility issues and sending the review package to Abbey. User identified that connector line labels were stacked and obscured by the connector lines themselves. Added explicit `BPMNLabel` bounds to position labels off the lines; user then made additional manual edits in bpmn.io to complete the cleanup. Final PDF regenerated and confirmed clean. SOP v1.1 + process.pdf sent to Abbey via Teams for review.

**Actions taken:**
- Identified root cause of label visibility issue: no explicit `BPMNLabel` bounds, causing labels to render on top of connector lines
- Added `<bpmndi:BPMNLabel>` bounds to `Flow_G1_Yes` (label above horizontal line) and `Flow_G1_No` (label right of vertical line) as the fix pattern
- User completed remaining connector label fixes manually in bpmn.io and saved corrected `process.bpmn`
- Regenerated `capstone/process.pdf` twice (once after Claude edits, once after user's manual corrections)
- Confirmed PDF visually clean
- User sent `capstone/SOP.md` (v1.1) + `capstone/process.pdf` to Abbey Cohen via Microsoft Teams for partner review

**Files modified this session:**
- `capstone/process.bpmn` — Connector label positions fixed (BPMNLabel bounds added; user manual edits applied)
- `capstone/process.pdf` — Regenerated from corrected BPMN
- `CHANGELOG.md` — v2.3.0 entry added

**AI tool usage:**
- **Tool:** Claude Code (claude-sonnet-4-6)
- **Tasks:** BPMN label fix pattern, PDF regeneration
- **Quality check:** PDF visually confirmed by user before sending

**Outcome:** BPMN connector cleanup complete. Review package sent to Abbey. Awaiting her feedback before SOP v1.2. Next work: build `capstone/governance.md` while waiting for Abbey's response.

---

## Entry 43 — 2026-04-12 — Capstone Checkpoint Package

**Prompt summary:** Session focused on building the full Capstone Checkpoint submission package. Started by auditing all checkpoint requirements against existing artifacts. Drafted all missing checkpoint documents in order, assembled the A-capstone/ submission folder, and updated logs.

**Actions taken:**
- Audited Track A checkpoint requirements against existing capstone files — identified 5 missing documents
- Created `capstone/checkpoint-project-snapshot.md` — process overview, partner summary, scope changes since Week 12
- Created `capstone/checkpoint-partner-reaction.md` — honest review status (no response from Abbey), rationale, consultant self-assessment of usability gaps (G-02, Step 6/7 boundary, BPMN notation)
- Created `capstone/checkpoint-remaining-work-plan.md` — Week 14/15 task table with owners and risk/contingency
- Created `capstone/checkpoint-memo.md` — all four required checkpoint questions answered
- Created `capstone/checkpoint-ai-usage-note.md` — session-by-session AI usage with human judgment accounting
- User converted project snapshot, partner reaction, checkpoint memo, and AI usage note to Word and edited to personal voice
- Created `A-capstone/` folder with 8 numbered submission files

**Files created this session:**
- `capstone/checkpoint-project-snapshot.md`
- `capstone/checkpoint-partner-reaction.md`
- `capstone/checkpoint-remaining-work-plan.md`
- `capstone/checkpoint-memo.md`
- `capstone/checkpoint-ai-usage-note.md`
- `A-capstone/` — 8 files (01–08, numbered for instructor navigation)

**Files modified this session:**
- `CHANGELOG.md` — v2.4.0 entry added

**AI tool usage:**
- **Tool:** Claude Code (claude-sonnet-4-6)
- **Tasks:** Requirement audit, drafting all 5 checkpoint documents, assembling submission folder
- **Quality check:** All documents grounded in existing project artifacts (discovery notes, SOP, BPMN, prompt log); user reviewed and edited each Word doc before inclusion in submission package

**Outcome:** Capstone Checkpoint package complete and ready for Canvas submission. Next session: build `capstone/governance.md` (does not depend on Abbey's feedback).
