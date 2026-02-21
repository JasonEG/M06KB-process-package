# Week 05 CLI Log

## Entry 1 — Mermaid Flowchart Generation

**Date:** 2026-02-11
**Tool:** Claude Code (CLI)

### Prompt

> Read SOP.md and generate Mermaid flowchart code (flowchart TD) that matches the procedure exactly.
> - Include explicit Start and End.
> - Every decision has labeled branches.
> - Do NOT invent steps. If missing, mark as [TBD] as a note.
> Write the output to diagrams/mermaid/process.mmd.

### What Was Done

1. Read `process-package/SOP.md` to extract the full procedure (10 steps, 3 decision points).
2. Generated a `flowchart TD` Mermaid diagram mapping every SOP step and decision to a node.
3. Wrote the output to `process-package/diagrams/mermaid/process.mmd`.

### Key Decisions

- Two End nodes were created: one for the normal completion path and one for the early "No action needed" exit (Step 1, "No" branch).
- Decision branches loop back exactly as described in the SOP (Decision 2 "No" → Step 4; Decision 3 "No" → Step 7).
- Secretary follow-up actions were noted as `[TBD]` since the SOP itself marks them as TBD.
- No steps were invented; every node maps directly to an SOP step or decision.

### Output

- `process-package/diagrams/mermaid/process.mmd`

---

## Entry 2 — Git Repository Setup and GitHub Publish

**Date:** 2026-02-13
**Tool:** Claude Code (CLI)

### Prompt

> Create a git repository for the process-package folder. Set up a .gitignore, make an initial commit, and create a remote repo under https://github.com/jasoneg.

### What Was Done

1. Initialized a new Git repository in `process-package/`.
2. Created a `.gitignore` with common OS and editor exclusions (Thumbs.db, .DS_Store, .vscode/, .idea/, etc.).
3. Staged all 10 project files and committed with the message "Initial commit: Module 05 CLI process package".
4. Installed the GitHub CLI (`gh`) via `winget` and authenticated via browser-based device flow.
5. Created a new public GitHub repository: `JasonEG/M05CLI-process-package`.
6. Pushed the initial commit to the `master` branch on the remote.

### Key Decisions

- Repository was created as **public** to align with typical coursework sharing requirements.
- Used `gh repo create` with `--source=.` and `--push` to create the remote and push in one step.
- The `.gitignore` covers Windows, macOS, and common editor artifacts without being overly broad.

### Output

- GitHub repository: https://github.com/JasonEG/M05CLI-process-package
- `.gitignore` added to project root

---

## Entry 3 — BPMN 2.0 XML Generation

**Date:** 2026-02-13
**Tool:** Claude Code (CLI)

### Prompt

> Using SOP.md, generate a BPMN 2.0 XML file for the process.
> - Start event + end event required.
> - Use tasks for steps, gateways for decisions.
> - Use lanes ONLY if roles differ materially.
> - Do NOT invent systems or approvals.
> Write to diagrams/bpmn/process.bpmn.

### What Was Done

1. Read `SOP.md` and the existing Mermaid diagram to understand the full process flow.
2. Generated a BPMN 2.0 XML file with a single Teacher pool (all steps performed by the same role).
3. Mapped all 10 SOP steps to tasks, 3 decision points to exclusive gateways, and included start/end events.
4. Included a BPMNDiagram section with layout coordinates for rendering in tools like bpmn.io.

### Key Decisions

- Used a single pool with no lanes initially, since all process steps are performed by the Teacher.
- Two end events: normal completion and early "No action needed" exit.
- Loop-backs match the SOP exactly (Gateway 2 "No" → Task 4; Gateway 3 "No" → Task 7).
- No systems or approvals were invented; every element maps directly to the SOP.

### Output

- `process-package/diagrams/bpmn/process.bpmn`

---

## Entry 4 — BPMN Lanes for Three Roles

**Date:** 2026-02-13
**Tool:** Claude Code (CLI)

### Prompt

> Edit the BPMN file to include roles for Teacher, Administrator, and Secretary.

### What Was Done

1. Restructured the BPMN file to use a single pool with three horizontal lanes: Administrator, Teacher, and Secretary.
2. Added `Task_SendReminder` ("Send grading reminder email to teachers") in the Administrator lane, mapped from the Principal's documented responsibility in the SOP.
3. Added `Task_ReceiveConfirmation` ("Receive grade confirmation email") in the Secretary lane, mapped from the Secretary's documented responsibility in the SOP.
4. Moved the start event to the Administrator lane and the process-complete end event to the Secretary lane.
5. All existing Teacher tasks, gateways, and loop-backs were preserved in the Teacher lane.

### Key Decisions

- Administrator lane maps to the SOP's "Principal" role (sends grading reminder).
- Secretary lane reflects the documented responsibility of receiving the confirmation email.
- Cross-lane sequence flows connect Admin → Teacher (reminder triggers decision) and Teacher → Secretary (email confirmation).
- The "No action needed" end event stays in the Teacher lane since that decision belongs to the Teacher.
- No steps were invented; both new tasks come directly from the SOP roles section.

### Output

- `process-package/diagrams/bpmn/process.bpmn` (updated with 3 lanes)

---

## Entry 5 — Diagram Rendering and README Documentation

**Date:** 2026-02-13
**Tool:** Claude Code (CLI)

### Prompt

> Render the BPMN diagram and Mermaid diagram and place them in the respective folders. Then update the README with clear instructions on how to regenerate documentation artifacts. Also update the CHANGELOG.

### What Was Done

1. Read both diagram source files (`process.bpmn` and `process.mmd`) to understand their content.
2. Rendered the Mermaid flowchart to SVG using `mmdc` (Mermaid CLI v11.12.0).
3. Rendered the BPMN diagram to PNG using `bpmn-to-image` (v0.10.0).
4. Expanded `README.md` from a single heading into a full project overview including:
   - Project description
   - Repository structure tree
   - Diagram regeneration instructions with prerequisites and CLI commands for both Mermaid and BPMN
5. Added a `[1.1.0] — 2026-02-13` entry to `CHANGELOG.md` documenting the new rendered diagrams and README updates.
6. Committed and pushed all changes to `origin/master` on GitHub.

### Key Decisions

- Used `mmdc -t default` for a clean, neutral theme on the Mermaid SVG.
- Regeneration instructions specify running commands from the `process-package/` directory to keep paths simple.
- Prerequisites section tells users to install both `@mermaid-js/mermaid-cli` and `bpmn-to-image` globally via npm.
- Version bumped to 1.1.0 (minor) since new content was added without breaking changes.

### Output

- `process-package/diagrams/mermaid/process.svg` (regenerated)
- `process-package/diagrams/bpmn/process.png` (regenerated)
- `process-package/README.md` (expanded)
- `process-package/CHANGELOG.md` (v1.1.0 added)

---

## Entry 6 — CLAUDE.md Git Repository Fix

**Date:** 2026-02-15
**Tool:** Claude Code (CLI)

### Prompt

> Check out the CLAUDE.md file and give me a rundown of the directory. Investigate why git is not detected and fix it.

### What Was Done

1. Discovered that Claude Code did not detect a git repository at the `M05CLI` root directory.
2. Investigated the prompt log and found that the git repo was initialized inside `process-package/` (Entry 2), not at the `M05CLI` root.
3. Confirmed the repo at `process-package/` was healthy — on branch `master`, up to date with `origin`, clean working tree, 7 commits.
4. Updated `CLAUDE.md` with a new **Git Repository** section documenting that the repo lives inside `process-package/` and all git operations must be run from there.
5. Moved `CLAUDE.md` from the `M05CLI` root into `process-package/` so it is tracked by the git repository.
6. Committed and pushed the change to `origin/master`.

### Key Decisions

- Added explicit git location guidance to `CLAUDE.md` to prevent future confusion about where the repo root is.
- Moved `CLAUDE.md` into the repo rather than restructuring the repo, since all other project files already live in `process-package/`.

### Output

- `process-package/CLAUDE.md` (moved from `M05CLI/CLAUDE.md`, updated with git repo section)

---

## Entry 7 — SOP / Mermaid / BPMN Validation

**Date:** 2026-02-15
**Tool:** Claude Code (CLI)

### Prompt

> Validate that the SOP, Mermaid diagram, and BPMN diagram all describe the same process. Record the results in a validation log file.

### What Was Done

1. Read all three artifacts (`SOP.md`, `process.mmd`, `process.bpmn`) and compared them step-by-step.
2. Verified that all 10 SOP steps, 3 decision points, and all loop-back targets match across all three artifacts.
3. Identified two intentional differences in the BPMN: `Task_SendReminder` (Administrator) and `Task_ReceiveConfirmation` (Secretary), which represent roles from the SOP's roles section but are not numbered steps.
4. Created `validation-log.md` in `process-package/` to record this and future validation checks.

### Key Decisions

- Result: **PASS** — all three artifacts are consistent.
- The BPMN's additional Admin/Secretary tasks were noted as intentional expansions, not inconsistencies.
- The Mermaid diagram was left as-is, scoped to the Teacher's 10 numbered steps.
- Created a dedicated validation log file rather than embedding results in the prompt log, to support future validation entries.

### Output

- `process-package/validation-log.md` (new file)

---

## Entry 8 — Glossary / SOP Validation

**Date:** 2026-02-15
**Tool:** Claude Code (CLI)

### Prompt

> Validate the glossary against the SOP.

### What Was Done

1. Compared every term in `glossary.md` (3 roles, 5 systems/tools, 3 process terms) against usage in `SOP.md`.
2. All 11 glossary entries matched the SOP accurately.
3. Identified one minor gap: "Traditional Grades" (Step 7 screen name) is not in the glossary, but user deemed it unnecessary to add.
4. Recorded results as Entry 2 in `validation-log.md`.
5. Updated `CLAUDE.md` with a "Where We Left Off" section to preserve session context.

### Key Decisions

- Result: **PASS** — all glossary entries are accurate.
- The "Traditional Grades" gap was noted but intentionally not addressed.
- Added session context to `CLAUDE.md` so future sessions know where to pick up.

### Output

- `process-package/validation-log.md` (Entry 2 added)
- `process-package/CLAUDE.md` (updated with validation status and next steps)

---

## Entry 9 — Screenshots and README Rework

**Date:** 2026-02-15
**Tool:** Claude Code (CLI)

### Prompt

> Add screenshots from the network drive to the artifacts folder (.png files only). Then rework the README to include: what this project is and why it matters, how to navigate the folder structure, how to regenerate diagrams (step-by-step), what files are source-of-truth vs generated, and where to find versioning and change history.

### What Was Done

1. Copied 8 `.png` screenshot files from `\\COLUM-FILE\Faculty\jgeanuracos\Desktop\UC Teach\IT7039 SS\M02 SOPv0\` to `artifacts/screenshots/`.
2. Rewrote `README.md` from scratch with five new sections:
   - **What This Project Is** — explains the purpose and why standardizing grade finalization matters.
   - **Folder Structure** — updated tree including the new screenshots, with inline annotations.
   - **Source of Truth vs. Generated Files** — table distinguishing authored files (SOP.md, glossary) from generated outputs (SVG, PNG).
   - **Regenerating Diagrams** — numbered step-by-step instructions (prerequisites, Mermaid, BPMN).
   - **Versioning and Change History** — points to CHANGELOG.md, validation-log.md, and git history.
3. Updated `CHANGELOG.md` with a `[1.2.0]` entry for the screenshots and README rework.

### Key Decisions

- Version bumped to 1.2.0 (minor) since new content was added (screenshots) and the README was substantially expanded.
- Screenshot filenames were kept as-is from the source to preserve recognizability.
- The README now explicitly labels `SOP.md` as the single source of truth, with a clear workflow: edit SOP first → update diagram sources → regenerate rendered outputs.
- Non-`.png` files in the source directory were intentionally excluded per user request.

### Output

- `process-package/artifacts/screenshots/` (8 new .png files)
- `process-package/README.md` (rewritten)
- `process-package/CHANGELOG.md` (v1.2.0 added)

---

## Entry 10 — M06 KB Docs Folder Structure and SOP_v1

**Date:** 2026-02-16
**Tool:** Claude Code (CLI)

### Prompt

> Inside of the process-package folder, create a docs folder with source and exports subfolders. Populate SOP_v1.md from the existing SOP.md.

### What Was Done

1. Created `docs/source/` and `docs/exports/` directories under `process-package/`.
2. Created three source Markdown files: `SOP_v1.md`, `KB_Page.md`, `Quick_Reference.md`.
3. Created three placeholder PDF files: `SOP_v1.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf` in `docs/exports/`.
4. Converted `SOP.md` (JSON format) into a clean, human-readable Markdown document and wrote it to `docs/source/SOP_v1.md`.
   - Structured with sections: Purpose, Scope, Roles & Responsibilities, Prerequisites, Inputs & Outputs, Procedure (10 steps with decision points), and Exceptions.
   - Used tables for Roles and Exceptions, blockquotes for decision points, and bold navigation paths.

### Key Decisions

- The JSON-structured SOP was converted to readable Markdown rather than copied verbatim, to serve as a polished knowledge-base-ready document.
- PDF files in `docs/exports/` are empty placeholders to be replaced once source files are finalized.
- `KB_Page.md` and `Quick_Reference.md` were created empty, to be populated in subsequent steps.

### Output

- `process-package/docs/source/SOP_v1.md` (populated from SOP.md)
- `process-package/docs/source/KB_Page.md` (empty)
- `process-package/docs/source/Quick_Reference.md` (empty)
- `process-package/docs/exports/SOP_v1.pdf` (placeholder)
- `process-package/docs/exports/KB_Page.pdf` (placeholder)
- `process-package/docs/exports/Quick_Reference.pdf` (placeholder)

---

## Entry 11 — KB_Page.md Population

**Date:** 2026-02-17
**Tool:** Claude Code (CLI)

### Prompt

> Convert this SOP into a scannable KB page with headings: TL;DR, When to use, Prerequisites, Roles, Steps (simplified), Exceptions/Troubleshooting, Links/Resources, Owner + Last updated. Do not invent steps. Flag missing info as [TBD].

### What Was Done

1. Read `docs/source/SOP_v1.md`, `SOP.md`, and `glossary.md` to gather all source content before writing.
2. Wrote `docs/source/KB_Page.md` with 8 sections derived strictly from SOP v1.5.
3. Simplified the 10 SOP steps into plain-language one-liners preserving nav paths and decision logic.
4. Exceptions section formatted as a 3-column table (Problem / What to Do / Escalate If…) matching the SOP's trigger/resolution/escalation structure.
5. Flagged 5 items as [TBD]: Secretary follow-up actions, process owner, KB page author, PowerSchool login URL, IT support link, review cycle.
6. In review, resolved all [TBD] items except Secretary follow-up actions:
   - Owner and KB page author: `jgeanuracos`
   - Review cycle: January and May
   - PowerSchool login URL: `https://ps-co.metasolutions.net`
   - IT Help Desk: `https://ww3.autotask.net/ClientPortal/login.aspx?ci=302139&accountId=431`

### Key Decisions

- Steps 5 and 6 from the SOP (verify weights / save and repeat) merged into one bullet with a "repeat per class" note — user confirmed this was appropriate for the KB format.
- "Do not use this process to enter individual assignment grades" line included from the SOP's out-of-scope section to set audience expectations.
- Relative links to SOP, glossary, and diagrams preserved as framework; noted for update if published to a portal.

### Output

- `process-package/docs/source/KB_Page.md` (populated)

---

## Entry 12 — Quick_Reference.md Population and Revision

**Date:** 2026-02-17
**Tool:** Claude Code (CLI)

### Prompt (initial)

> Work on Quick_Reference.md [condensed reference guide].

### Prompt (revision)

> Check what you just created against these parameters: a 1-page quick reference: 6–10 bullet steps max, include if/then decision points, include escalation/contact info, include common failure points. Preserve approvals and required checks.

### What Was Done

1. Wrote initial `Quick_Reference.md` with a 9-item checklist, Key Reminders table, Quick Troubleshooting table, and Key Links table.
2. Evaluated the initial version against the 5 stated parameters — identified three gaps: no if/then decision points, escalation contact not prominent, required checks not visually distinguished.
3. Rewrote the file to address all gaps:
   - Merged email + log out into one step, reducing to 8 steps (within 6–10).
   - Integrated inline if/then decision branches into Steps 1, 4, 6, and 7.
   - Added `[REQUIRED]` badge to Steps 4, 5, and 7 (required checks/approvals).
   - Expanded troubleshooting to a 3-column table (Problem / Fix / Escalate To) with escalation path per row.
   - Added a dedicated **Escalation** section with the IT Help Desk link.
   - Folded the 10%/90% weight detail directly into Step 5; removed the separate Key Reminders table.

### Key Decisions

- All content sourced strictly from SOP v1.5 — nothing invented.
- Secretary follow-up escalation not included (remains [TBD] in the SOP).
- Key Reminders section removed in revision; its content was redistributed inline where it is most actionable.

### Output

- `process-package/docs/source/Quick_Reference.md` (populated and revised)

---

## Entry 13 — Checklist.md Creation

**Date:** 2026-02-18
**Tool:** Claude Code (CLI)

### Prompt

> Convert the procedure into a checklist with checkboxes, using the format: [ ] action verb + object + success condition. Keep the same sequence and decision logic.

### What Was Done

1. Read `docs/source/SOP_v1.md` and `docs/source/Quick_Reference.md` for source content and existing step structure.
2. Created `docs/source/Checklist.md` with all 10 SOP steps converted to GitHub-flavored markdown checkboxes.
3. Applied the requested format to each step: `[ ] action verb + object + success condition`.
4. Preserved all three decision points from the SOP as inline if/then branches beneath the relevant steps (Steps 1, 7, and 9).
5. Updated `CHANGELOG.md` with a `[1.5.0]` entry.

### Key Decisions

- Created a new file rather than modifying Quick_Reference.md, since the checklist follows the full 10-step SOP sequence (Quick_Reference merged Steps 5 and 6).
- Decision logic rendered as indented `→ if X → do Y` lines rather than separate checkbox items, to keep them non-actionable and visually subordinate.
- Loop-back targets named explicitly (e.g., "return to Verify Grades (Step 4)") to match SOP cross-references.

### Output

- `process-package/docs/source/Checklist.md` (new file)
- `process-package/CHANGELOG.md` (v1.5.0 added)

---

## Entry 14 — KB_Page.md Cross-Artifact Validation and Fix

**Date:** 2026-02-18
**Tool:** Claude Code (CLI)

### Prompt

> Examine Checklist.md, Quick_Reference.md, and KB_Page.md against SOP_v1.md and check to see if we removed a prerequisite, approval, or decision rule.

### What Was Done

1. Read all four documents simultaneously and compared every prerequisite, approval gate, and decision rule from SOP_v1.md against each derived document.
2. Found all three decision points and all approval gates (Step 4 correction gate, Step 5 weight spec, Step 6 save requirement) correctly present in Checklist.md and Quick_Reference.md.
3. Identified two omissions in KB_Page.md:
   - **Step 8:** Missing "Save" after the Final Grade Status checkbox instruction. Checklist and Quick Reference both explicitly include Save at this step; KB_Page did not.
   - **Step 9:** Decision 3 ("Are all classes finalized?") was implicit only — "Repeat Steps 7–8 for all classes" — with no explicit Yes/No branches or loop-back target. Checklist and Quick Reference both state the decision explicitly.
4. Applied both fixes to `docs/source/KB_Page.md`.
5. Added CHANGELOG entry v1.5.1 and this prompt log entry.

### Key Decisions

- Step 8 fix phrased as "Save before exiting" to match the language used in Step 6 (same pattern: verify → save before exiting).
- Step 9 decision rewritten as an inline if/then: "If all classes are finalized → proceed to Step 10. If not → return to Step 7." — consistent with the style used in Steps 7 and 9 of Checklist.md.
- All prerequisites (credentials, class list, grading period) were confirmed present in KB_Page's prerequisites table; no changes needed there.
- Checklist and Quick Reference have no explicit prerequisites section — noted as expected for those formats, not flagged as a defect.

### Output

- `process-package/docs/source/KB_Page.md` (Step 8 and Step 9 corrected)
- `process-package/CHANGELOG.md` (v1.5.1 added)

---

## Entry 15 — Glossary URL Addition and README M06 Update

**Date:** 2026-02-18
**Tool:** Claude Code (CLI)

### Prompt

> Can we update the diagrams/glossary next? [followed by] Add the URL to the glossary PowerSchool entry. [followed by] Update the readme first please. [followed by] Yes, batch the changelog and prompt log now.

### What Was Done

1. Read all three diagram/glossary files simultaneously and compared against SOP_v1.md and the KB docs.
2. Confirmed both diagrams (Mermaid and BPMN) are accurate and consistent with SOP v1.5 — no changes needed.
3. Identified one glossary gap: the PowerSchool login URL (`ps-co.metasolutions.net`) is documented in `KB_Page.md` and `Quick_Reference.md` but was absent from the glossary's PowerSchool entry.
4. Added the login URL to the `glossary.md` PowerSchool entry.
5. Read `README.md` and identified three M06 gaps: module label still said "Module 05 — CLI"; the `docs/` folder was entirely absent from the folder structure tree; the Source of Truth table had no entries for any `docs/source/` files.
6. Applied three README fixes: updated module label to "Module 06 — KB"; added full `docs/` tree to the folder structure; added all four `docs/source/` files and `docs/exports/*.pdf` to the Source of Truth table.
7. Added CHANGELOG entry v1.5.2 and this prompt log entry.

### Key Decisions

- Diagrams required no changes — the process itself hasn't changed between M05 and M06, only the documentation deliverable format has.
- URL added as a markdown hyperlink inline in the glossary table cell, consistent with the link style used in KB_Page and Quick_Reference.
- Checklist.pdf not added to the folder structure or exports — no PDF placeholder was created for it in v1.3.0, and no PDF export has been requested yet.
- README Source of Truth table labels `docs/source/` files as "Authored" (not generated) since they are hand-edited Markdown, and `docs/exports/` as "Generated" since they will be produced from the source files.

### Output

- `process-package/glossary.md` (PowerSchool URL added)
- `process-package/README.md` (module label, folder structure, source of truth table updated)
- `process-package/CHANGELOG.md` (v1.5.2 added)

---

## Entry 16 — README "Start Here" Navigation Section

**Date:** 2026-02-19
**Tool:** Claude Code (CLI)

### Prompt

> Does our readme have an easy to find, accessible link to the KB document? [followed by] Yes, add that section near the top and please make it so it is welcoming to any user.

### What Was Done

1. Read `README.md` and confirmed no clickable links to any `docs/source/` files existed — only plain-text paths in the folder tree and Source of Truth table.
2. Added a "Start Here" section between "What This Project Is" and "Folder Structure" containing:
   - A 4-row navigation table linking directly to `KB_Page.md`, `Quick_Reference.md`, `Checklist.md`, and `SOP_v1.md` with plain-language descriptions of when to use each.
   - Role-based guidance directing teachers to the quick-reference docs and administrators/trainers to the full SOP and KB article.
   - A horizontal rule to visually separate the navigation section from the technical folder structure below.
3. Updated `CHANGELOG.md` with a `[1.5.3]` entry and updated `CLAUDE.md` to v1.5.3.

### Key Decisions

- Placed the section above the folder structure so any user landing on the README encounters navigation before technical detail.
- Used a table format for scannability — single-column bullet lists would have been harder to parse at a glance.
- Role guidance kept to two sentences to remain welcoming without being prescriptive.

### Output

- `process-package/README.md` ("Start Here" section added)
- `process-package/CHANGELOG.md` (v1.5.3 added)
- `process-package/CLAUDE.md` (updated to v1.5.3)

---

## Entry 17 — Narrated Walkthrough Outline

**Date:** 2026-02-19
**Tool:** Claude Code (CLI)

### Prompt

> Write a 1–3 minute narrated walkthrough outline with time stamps (0:00–0:15, etc.). Focus on why it matters, the main steps, where users get stuck, and where to get help.

### What Was Done

1. Read `docs/source/KB_Page.md` and `docs/source/Quick_Reference.md` for source content before writing.
2. Created `artifacts/examples/walkthrough-outline.md` — a narrated script outline targeting 1:45–2:00 with six timestamped segments:
   - `[0:00–0:15]` Hook — why grade finalization matters (stakes: transcript errors)
   - `[0:15–0:30]` When to start — principal/secretary email or end-of-period recognition
   - `[0:30–1:00]` Main steps — log in, Score Sheet verification, Traditional Grade Calculations weights
   - `[1:00–1:25]` Marking complete and notifying — Final Grade Status checkbox, secretary email, log out
   - `[1:25–1:45]` Where users get stuck — three documented failure points with fixes
   - `[1:45–2:00]` Where to get help — KB article and IT Help Desk portal
3. Included production notes on narration pace, screen recording guidance, closed captions, and chapter menu.
4. Updated `CHANGELOG.md` with a `[1.5.4]` entry and updated `CLAUDE.md` to v1.5.4.
5. Committed all v1.5.3 and v1.5.4 changes and pushed to `origin/master` on GitHub (commit `adcd883`).

### Key Decisions

- Tone specified as calm, direct, and encouraging — the audience is under a deadline and needs confidence, not formality.
- Failure points drawn strictly from the Exceptions/Troubleshooting table in `KB_Page.md` — nothing invented.
- Saved to `artifacts/examples/` since that directory is designated for supporting materials referenced by the SOP.
- Production notes included to make the outline usable by anyone recording the video, not just the original author.

### Output

- `process-package/artifacts/examples/walkthrough-outline.md` (new file)
- `process-package/CHANGELOG.md` (v1.5.4 added)
- `process-package/CLAUDE.md` (updated to v1.5.4)
- GitHub: commit `adcd883` pushed to `origin/master`

---

## Entry 18 — PDF Export of All Four Source Documents

**Date:** 2026-02-20
**Tool:** Claude Code (CLI)

### Prompt

> Export all four source documents to PDF and make sure all supporting files are updated.

### What Was Done

1. Used `md-to-pdf` to generate PDF exports of all four source Markdown files in `docs/source/`.
2. Replaced the three existing placeholder PDFs (`SOP_v1.pdf`, `KB_Page.pdf`, `Quick_Reference.pdf`) with the generated files in `docs/exports/`.
3. Created `docs/exports/Checklist.pdf` as a new export — no placeholder had existed for it previously.
4. Cross-validated all four PDFs against their source Markdown files to confirm no prerequisites, approval gates, or decision rules were missing from any document.
5. Updated `README.md`: added `Checklist.pdf` to the `docs/exports/` folder tree and added it to the Source of Truth table; removed "placeholder" labels from all four PDF entries.
6. Added CHANGELOG entry v1.6.0 and updated CLAUDE.md to v1.6.0.
7. Committed all changes and pushed to `origin/master` (commit `f2f9b19`).

### Key Decisions

- `md-to-pdf` used for all four exports to ensure consistent formatting across documents.
- Checklist.pdf added as a new file rather than a placeholder since it was ready to export.
- README "placeholder" labels removed to reflect that all exports now contain real content.

### Output

- `process-package/docs/exports/SOP_v1.pdf` (generated; replaced placeholder)
- `process-package/docs/exports/KB_Page.pdf` (generated; replaced placeholder)
- `process-package/docs/exports/Quick_Reference.pdf` (generated; replaced placeholder)
- `process-package/docs/exports/Checklist.pdf` (new; no prior placeholder)
- `process-package/README.md` (folder tree and Source of Truth table updated)
- `process-package/CHANGELOG.md` (v1.6.0 added)
- `process-package/CLAUDE.md` (updated to v1.6.0)
- GitHub: commit `f2f9b19` pushed to `origin/master`

---

## Entry 19 — KB_Page.md Editorial Improvements

**Date:** 2026-02-20
**Tool:** Claude Code (CLI)

### Prompt

> Review KB_Page.md for clarity and skimmability. Improve headings, replace jargon with plain language, and clean up link text — without changing any SOP step numbering, decision rules, or meaning.

### What Was Done

1. Read `docs/source/KB_Page.md` in full before making changes.
2. Renamed five section headings for clarity and plain language:
   - `## TL;DR` → `## Summary`
   - `## Steps (Simplified)` → `## Steps`
   - `## Exceptions / Troubleshooting` → `## Troubleshooting`
   - `## Links / Resources` → `## Related Documents and Tools`
   - `## Owner + Last Updated` → `## Document Info`
3. Replaced the `## Summary` paragraph with 4 scannable bullet points covering the core audience, trigger, actions, and outcome.
4. Replaced jargon throughout with plain language:
   - "grading window is open" → "grade finalization period has started"
   - "allocated as percentages or total points" → "split across other assignments or categories"
   - "grading-period drop-down" → "grading period menu"
   - "contact support" → "contact IT support" (two occurrences)
5. Cleaned up all link text: removed filenames and technical acronyms ("Mermaid", "BPMN") from link labels.
6. Bumped the Last Updated date to 2026-02-20.
7. Regenerated `docs/exports/KB_Page.pdf` from the updated source.
8. Added CHANGELOG entry v1.6.1 and updated CLAUDE.md to v1.6.1.
9. Committed all changes and pushed to `origin/master` (commits `3bdfe8c`, `cf67a62`).

### Key Decisions

- SOP step numbering, decision rules, and all procedural content preserved exactly — editorial changes only.
- TL;DR renamed to Summary because "TL;DR" is informal and may not be recognized by all users.
- Link text cleaned of filenames and tool names to be navigable without technical knowledge.

### Output

- `process-package/docs/source/KB_Page.md` (editorial improvements applied)
- `process-package/docs/exports/KB_Page.pdf` (regenerated from updated source)
- `process-package/CHANGELOG.md` (v1.6.1 added)
- `process-package/CLAUDE.md` (updated to v1.6.1)
- GitHub: commits `3bdfe8c` and `cf67a62` pushed to `origin/master`
