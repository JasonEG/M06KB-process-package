# Discovery Notes — In-Home Dog Boarding Intake and Care

**Consultant:** Jason Geanuracos
**Partner / Process Owner:** Abbey Cohen
**Subject Process:** In-Home Dog Boarding Intake and Care
**Source Document:** `capstone/Sample Process Outline DOG BOARDING.pdf` (Abbey Cohen, 2026-04-05)
**Discovery Method:** Written process outline submitted by partner
**Notes Date:** 2026-04-07

---

## Source Summary

Abbey submitted a structured process outline covering the full lifecycle of a dog boarding engagement — from initial client inquiry through post-stay follow-up. The outline is well-organized with clearly defined phases, decision points, and exception handling. No live interview was conducted; the written outline is the primary discovery artifact.

---

## Process at a Glance

| Field | Value |
|---|---|
| **Trigger** | Client submits a boarding request or inquiry |
| **End State** | Dog returned to owner; care complete; follow-up sent |
| **Primary Role** | Dog Sitter (Abbey Cohen) |
| **Secondary Role** | Dog Owner (Client) |
| **Phase Count** | 9 |

---

## Phase-by-Phase Analysis

| Phase | Name | Decision Points | Notes |
|---|---|---|---|
| 1 | Client Inquiry and Screening | Accept or decline based on availability/fit | — |
| 2 | Information Gathering | Hold booking if info incomplete | Follow up before confirming |
| 3 | Meet and Greet | **If applicable** — see Gap G-01 below | Accept or decline after meeting |
| 4 | Booking Confirmation and Preparation | — | — |
| 5 | Dog Drop-Off | — | Verbal re-confirmation of care instructions |
| 6 | Daily Care Routine | Food refusal, behavioral issues, signs of illness | Three inline decision points |
| 7 | Issue and Exception Handling | Minor / Moderate / Emergency triage | Triggered by Phase 6 decisions — see Gap G-03 |
| 8 | Pickup and Completion | — | Verbal summary provided to owner |
| 9 | Post-Stay Follow-Up | — | Review/feedback request optional |

---

## Gaps and Decisions

| # | Gap | Status | Resolution |
|---|---|---|---|
| G-01 | Phase 3 marked "if applicable" — conditions not defined | Resolved by consultant | Modeled as XOR gateway: new client → required; established repeat client → skip to Phase 4 |
| G-02 | No definition of "repeat client" threshold | Open — acceptable ambiguity | Left to dog sitter's discretion; noted in SOP as such |
| G-03 | Phase 7 (Issue Handling) overlaps Phase 6 decision paths | Resolved by consultant | Modeled as Step 7 (own step, triggered by Phase 6); returns to daily care loop when resolved |
| G-04 | Booking platform not specified (Rover, Wag, text, etc.) | Out of scope for v1.0 | Not included |
| G-05 | No payment/deposit process mentioned | Confirmed out of scope | Not included |

---

## Open Questions for Abbey

| # | Question | Status |
|---|----------|--------|
| 1 | Is the meet and greet decision rule (new vs. repeat client) accurate, or does she use a different trigger? | **Resolved** — Abbey reviewed SOP v1.1 on 2026-04-12 and confirmed no concerns; decision rule accepted as modeled |
| 2 | What booking platform or channel does she primarily use (app, text, Rover, etc.)? | **Out of scope** — not addressed in v1.0; platform documented as "app, text, or direct message" per Abbey's outline |
| 3 | Is there a maximum number of dogs she boards at one time? | **Out of scope** — not addressed in v1.0 |
| 4 | Is a preferred emergency vet predetermined, or does the owner provide it at drop-off? | **Resolved** — SOP Step 5 captures preferred vet at drop-off; Abbey confirmed no concerns |

---

## Notes for BPMN Diagram

- Two swimlanes: **Dog Sitter** (primary) and **Dog Owner** (active at Phases 1, 5, 8)
- Phase 3 gateway: XOR — new client vs. repeat client; second XOR after meet and greet (concerns → decline; no concerns → proceed)
- Phase 6 is a repeating loop (daily care runs for duration of stay)
- Phase 7 is a subprocess triggered from Phase 6 decision paths; returns to Phase 6 on resolution
- Two end events: normal end (Phase 9 complete) and decline end (Phase 1 or Phase 3 incompatibility)

---

## AI Usage This Session

- **Tool:** Claude Code (claude-sonnet-4-6)
- **Used for:** Analyzing Abbey's PDF, identifying gaps, drafting discovery notes, drafting SOP v1.0
- **Accuracy check:** All phase content and decision logic drawn directly from Abbey's outline; Gap G-01 and G-03 resolutions are consultant judgment calls, not AI-generated assumptions
