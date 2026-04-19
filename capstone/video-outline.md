# Video Essay Outline — Capstone Track A

**Target length:** 8–9 minutes. Hard cap: 10 minutes.
**Format:** Screen recording with voiceover. Pull up `capstone-package.pdf` for the walkthrough section.
**Status:** Draft — review and approve before recording.

---

## Section 1 — Introduction (0:30)

- Who you are, what the project is: "I worked as a consultant to document a real process for a partner — Abbey Cohen, who runs an in-home dog boarding service."
- One-sentence preview: "I'll walk through how I worked with Abbey, how I captured the process, how I used AI, and what the final package looks like."

---

## Section 2 — Partner Interactions (1:45)

**What worked:**
- Abbey submitted a structured written process outline — 9 phases, clear trigger and end state, decision points already identified. Solid foundation without needing multiple live interviews.
- Sent draft SOP and BPMN for review via Teams on 2026-04-10. Abbey responded on 2026-04-12: "It looks great!" — no modifications requested.

**What was difficult / what surprised you:**
- Entire discovery phase based on a written document, not a live interview. Ambiguity had to be resolved through analysis or flagged as a documented gap — no real-time follow-up.
- Abbey's outline left a few things undefined — most notably when a meet and greet is required and what counts as a repeat client. Had to make judgment calls, document them, and send back for confirmation.
- Her quick confirmation was validating but also surprising — expected more back-and-forth. Did she carefully review it, or trust you got it right? You interpreted it as confirmation and noted open questions in the discovery notes — but that's a limitation worth naming honestly.

---

## Section 3 — How You Captured the Process (1:30)

- **Source material:** One written process outline, submitted by Abbey as a PDF. No live interview.
- **Method:** Read the outline in full, built a phase-by-phase analysis in discovery notes — what each phase does, what decision points exist, where the outline left things undefined.
- **Gap analysis:** Five gaps documented (G-01 through G-05).
  - G-01 and G-03: Resolved by consultant (meet and greet trigger; Step 6/7 escalation boundary)
  - G-04 and G-05: Scoped out (booking platform; payment)
  - G-02: Left as acceptable ambiguity (repeat client threshold — sitter's discretion)
- **Derivation chain:** Discovery notes → SOP → BPMN → Governance plan. One clear line.

---

## Section 4 — AI Usage: Specific and Honest (2:45)

**Where AI was genuinely useful:**
- Structuring Abbey's outline into a formal SOP — translated informal phase descriptions into correctly formatted procedural steps with decision callouts, actors, and exceptions in one pass.
- Writing the BPMN XML from scratch — valid BPMN 2.0 XML with swimlanes, gateways, sequence flows, and loop characteristics on the first attempt.
- Governance plan drafting — complete document (DRI, RACI, review cadence, change control, escalation) from a prompt. Structure was solid.
- Cross-artifact consistency checking — at the end of the project, AI read all four artifacts simultaneously and caught a real inconsistency (SOP review date didn't match the governance plan cadence). Easy to miss manually.

**Where AI fell short and what you had to fix:**

1. **Step 6/7 escalation model** — AI presented three structural options. Choosing between them required judgment about what Abbey actually meant. AI couldn't make that call. You chose Option A and had to own that decision.

2. **BPMN connector labels** — AI added label positioning to the XML, but labels still rendered on top of connector lines in the visual output. Had to open bpmn.io and manually reposition several labels. Fix pattern was correct; execution was incomplete.

3. **Governance tone** — First draft was too formal for a one-person operation. Language didn't sound like it belonged to Abbey's process. Had it revised to conversational — a direction call AI couldn't anticipate without being told.

4. **The repeat client gap (G-02)** — AI flagged the ambiguity and suggested leaving it to the sitter's discretion. Probably right — but it's a judgment call about when acceptable ambiguity is actually acceptable. AI doesn't know Abbey's business well enough to make that call confidently. You made it, documented it, confirmed it with Abbey.

**Honest summary:** AI was a strong drafting and structural tool. It didn't hallucinate facts — it stayed close to Abbey's outline. But it needed direction at every decision point, and outputs needed human review before going to a real partner.

---

## Section 5 — Package Walkthrough (2:15)

*Pull up `capstone-package.pdf` on screen.*

- **Part I — SOP:** Governance header (version, DRI, review date, partner confirmation). Scope section and 9-step procedure — point out decision callouts at Steps 1, 3, 6 and the Step 7 severity table. Exceptions table.
- **Part II — BPMN Diagram:** Landscape page. Two swimlanes. XOR gateways and daily care loop. Maps to SOP steps.
- **Part III — Stakeholder Identification:** Handoff table — four explicit handoffs (meet and greet, drop-off, emergency escalation, pickup).
- **Part IV — Governance:** DRI (Abbey), quarterly review cadence, trigger-based review conditions.
- **Part V — Improvement Recommendations:** Name both briefly — intake form and pre-stay vet authorization. Grounded in existing SOP gaps, not invented.

---

## Section 6 — Closing (0:30)

- What you'd do differently: more live interaction with Abbey — even one conversation would have closed the open questions faster and made the confirmation feel more solid.
- What you learned: a good written process outline is enough to build from, but it moves faster and produces better results when you can ask questions in real time.

---

## Timing Summary

| Section | Target |
|---------|--------|
| Intro | 0:30 |
| Partner interactions | 1:45 |
| Process capture | 1:30 |
| AI usage | 2:45 |
| Package walkthrough | 2:15 |
| Closing | 0:30 |
| **Total** | **~9:15** |

---

*~45 seconds of buffer before the 10-minute cap.*
*Next step: review this outline, then record. Consider converting to a spoken script for any sections that feel thin.*
