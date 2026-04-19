# Capstone Checkpoint — Partner Reaction / Usability Note

**Consultant:** Jason Geanuracos
**Partner / Process Owner:** Abbey Cohen
**Date:** 2026-04-12

---

## Partner Review Status

The current SOP draft (v1.1) and BPMN process diagram (PDF) were sent to Abbey Cohen via Microsoft Teams on 2026-04-10. The message included an explicit invitation for feedback:

> "Let me know if you have any changes to suggest and I would be more than happy to look over your SOP/BPMN."

On 2026-04-12, Abbey responded: **"It looks great!"** She raised no concerns and requested no modifications.

This constitutes explicit partner validation of the SOP and BPMN as accurate representations of her process. The SOP remains at v1.1 — no revisions were required as a result of the review.

The review outcome is consistent with how the draft was built. The SOP was constructed directly from Abbey's own written process outline (submitted 2026-04-05). The consultant's contributions were formalizing the language, resolving two structural ambiguities (G-01: meet and greet trigger; G-03: Step 6/7 escalation boundary), and explicitly labeling two items as out of scope (booking platform, payment processing). Abbey's confirmation indicates these decisions were accurate.

The BPMN diagram — which introduced swimlane organization, XOR gateway notation, and a looping construct not present in Abbey's original outline — was also accepted without revision. This validates the structural interpretation the consultant applied.

---

## Consultant Self-Assessment — Likely Usability Gaps

In the absence of explicit partner feedback, the following issues are the most likely points of confusion for a first-time reader of the current draft:

**1. The "repeat client" threshold (G-02)**
The SOP states that the meet and greet decision is "at the dog sitter's discretion" for established repeat clients. This is intentionally vague — the gap was documented in the discovery notes and left open because Abbey did not define a threshold. A new user following the SOP would not know when they had crossed that threshold. This is the most likely question Abbey herself might raise upon close reading.

**2. The Step 6 / Step 7 trigger boundary**
The daily care loop (Step 6) and the escalation path (Step 7) were restructured from Abbey's original outline, which treated them as overlapping. The current SOP draws a clear trigger line — Step 7 activates when an issue cannot be closed within the normal loop. This is a consultant design decision, not something Abbey specified. It is logical but unfamiliar, and a reader encountering it for the first time might not immediately understand what "cannot be closed within the normal loop" means in practice.

**3. The BPMN gateway notation**
The BPMN diagram uses standard XOR gateway symbols and swimlane layout, which are not formats Abbey's original outline used. A reader unfamiliar with BPMN notation would need to be told what the diamond symbols mean. This is a presentation gap, not a content gap — the underlying logic matches the SOP.
