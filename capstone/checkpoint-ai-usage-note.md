# Capstone Checkpoint — AI Usage Note

**Consultant:** Jason Geanuracos
**Date:** 2026-04-12
**Tool:** Claude Code (claude-sonnet-4-6) via Anthropic CLI

---

## Overview

AI has been used throughout this capstone project as a drafting and scaffolding tool. Every substantive decision — what to include, how to resolve ambiguities, what to flag as a gap — was made by the consultant. AI accelerated the translation of those decisions into structured documents.

---

## Specific Uses by Session

**2026-04-05 — Process outline analysis**
Uploaded Abbey's written process outline (PDF) and used AI to read and summarize the 9 phases, identify the trigger and end state, and flag one structural gap (Phase 3 marked "if applicable" with no defined condition). This replaced a manual read-through and gave me a structured starting point faster. I then reviewed the analysis against Abbey's original document to confirm accuracy before proceeding.

**2026-04-07 — Discovery notes and SOP v1.0**
Used AI to draft `discovery-notes.md` and `SOP.md` (v1.0) from Abbey's outline. The phase content, role definitions, and exceptions table all came directly from Abbey's document. The two consultant judgment calls — how to model the Phase 3 gateway (G-01) and how to separate Phase 6 from Phase 7 (G-03) — were my decisions, not AI suggestions. AI drafted three options for the Step 6/7 escalation model; I selected Option A and AI revised the SOP accordingly. SOP bumped to v1.1.

**2026-04-09 — SOP verification and BPMN authoring**
Used AI to run a section-by-section format check of SOP v1.1 against the capstone requirements before sending to Abbey. AI also authored the BPMN 2.0 XML file (`process.bpmn`) — the two-swimlane layout, XOR gateway placement, daily care loop, and escalation subprocess were all translated from the SOP logic I had already approved. I reviewed the rendered PDF output and directed layout revisions (box sizing, pool width, connector routing).

**2026-04-10 — BPMN connector label fix**
AI identified the root cause of a label visibility problem in the BPMN diagram (missing explicit label bounds in the XML) and applied the fix pattern to two connectors. I completed the remaining fixes manually in bpmn.io and did a final visual review of the PDF before sending it to Abbey.

**2026-04-12 — Checkpoint package drafting**
Used AI to draft the project snapshot, partner reaction note, remaining work plan, checkpoint memo, and this AI usage note. Each was based on information I provided — the facts of the project, my own answers to the four memo questions, and my honest assessment of where things stand. I converted each document to Word and edited it to reflect my own voice before including it in the submission.

---

## Where Human Judgment Did the Real Work

- Selecting Track A and choosing Abbey as a partner
- Deciding to use Teams instead of Canvas for communication
- Resolving G-01 (meet and greet gateway rule) and G-03 (Step 6/7 boundary) — these are the two structural decisions in the SOP that Abbey did not specify; I made the calls and documented them in the discovery notes
- Selecting Option A for the Step 6/7 escalation model from three AI-presented options
- Completing the BPMN connector label fixes manually in bpmn.io
- Reviewing and editing all AI-drafted documents before submission
- All partner communication (Abbey's outline, Teams messages, review request)
