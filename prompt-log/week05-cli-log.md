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
