# Grade Finalization Process Package

Module 06 — KB Process Package

## What This Project Is

This repository is a **process package** that documents how teachers finalize quarter and semester grades in PowerSchool. It standardizes the end-of-term grading workflow — from verifying gradebook accuracy through storing final grades and notifying the school secretary — so that every teacher follows the same repeatable, auditable steps.

Getting this process right matters because grade finalization is high-stakes and time-sensitive. A missed weight setting or an un-stored grade can cascade into transcript errors. This package gives teachers a single reference they can follow step by step, and gives administrators a basis for training, auditing, and continuous improvement.

## Start Here

Not sure where to look? Here are the most useful documents for getting started:

| I want to… | Go here |
|---|---|
| Get a full explanation of the process | [Knowledge Base Article](docs/source/KB_Page.md) |
| See all steps at a glance | [Quick Reference Guide](docs/source/Quick_Reference.md) |
| Follow along step by step | [Procedural Checklist](docs/source/Checklist.md) |
| Read the complete, authoritative procedure | [Standard Operating Procedure](docs/source/SOP_v1.md) |

If you are a **teacher**, the [Quick Reference Guide](docs/source/Quick_Reference.md) and [Checklist](docs/source/Checklist.md) are the best places to start.
If you are an **administrator or trainer**, the [Knowledge Base Article](docs/source/KB_Page.md) and [SOP](docs/source/SOP_v1.md) have the full detail you need.

---

## Folder Structure

```
process-package/
├── README.md                  # You are here
├── SOP.md                     # Standard Operating Procedure (source of truth)
├── CHANGELOG.md               # Version history of process changes
├── glossary.md                # Domain-specific terminology
├── validation-log.md          # Cross-artifact consistency checks
│
├── diagrams/
│   ├── bpmn/
│   │   ├── process.bpmn       # BPMN 2.0 XML source
│   │   └── process.png        # Rendered BPMN diagram (generated)
│   └── mermaid/
│       ├── process.mmd        # Mermaid flowchart source
│       └── process.svg        # Rendered Mermaid diagram (generated)
│
├── artifacts/
│   ├── examples/              # Worked examples referenced by the SOP
│   └── screenshots/           # PowerSchool screen captures
│       ├── Complete Email.png
│       ├── Gradebook redacted.png
│       ├── Qtr final grade status.png
│       ├── Qtr weight.png
│       ├── S1 Final Grade status.png
│       ├── Sem Weight.png
│       ├── Trad Grade Calc.png
│       └── Weights screen.png
│
├── docs/
│   ├── source/
│   │   ├── SOP_v1.md          # Human-readable SOP (derived from SOP.md)
│   │   ├── KB_Page.md         # Knowledge-base article
│   │   ├── Quick_Reference.md # 1-page quick reference guide
│   │   └── Checklist.md       # Procedural checklist with checkboxes
│   └── exports/
│       ├── SOP_v1.pdf         # PDF export
│       ├── KB_Page.pdf        # PDF export
│       ├── Quick_Reference.pdf # PDF export
│       └── Checklist.pdf      # PDF export
│
└── prompt-log/
    └── week05-cli-log.md      # AI prompt interaction log
```

## Source of Truth vs. Generated Files

| File | Role |
|------|------|
| `SOP.md` | **Source of truth.** The authoritative description of the grade-finalization process. All other artifacts are derived from it. |
| `diagrams/mermaid/process.mmd` | Source file — Mermaid flowchart definition. |
| `diagrams/bpmn/process.bpmn` | Source file — BPMN 2.0 XML definition. |
| `diagrams/mermaid/process.svg` | **Generated** from `process.mmd`. Do not hand-edit. |
| `diagrams/bpmn/process.png` | **Generated** from `process.bpmn`. Do not hand-edit. |
| `glossary.md` | Authored reference — defines terms used in the SOP. |
| `validation-log.md` | Authored reference — records consistency checks between artifacts. |
| `docs/source/SOP_v1.md` | Authored — human-readable SOP derived from `SOP.md`. |
| `docs/source/KB_Page.md` | Authored — knowledge-base article derived from `SOP.md`. |
| `docs/source/Quick_Reference.md` | Authored — 1-page quick reference derived from `SOP.md`. |
| `docs/source/Checklist.md` | Authored — procedural checklist derived from `SOP.md`. |
| `docs/exports/SOP_v1.pdf` | **Generated** from `docs/source/SOP_v1.md`. Do not hand-edit. |
| `docs/exports/KB_Page.pdf` | **Generated** from `docs/source/KB_Page.md`. Do not hand-edit. |
| `docs/exports/Quick_Reference.pdf` | **Generated** from `docs/source/Quick_Reference.md`. Do not hand-edit. |
| `docs/exports/Checklist.pdf` | **Generated** from `docs/source/Checklist.md`. Do not hand-edit. |

When making process changes, always update **SOP.md first**, then update the diagram source files to match, and finally regenerate the rendered outputs.

## Regenerating Diagrams

The rendered diagram files (`process.svg` and `process.png`) are generated from their source files. After editing a source file, regenerate the rendered output using the steps below.

> All commands should be run from the `process-package/` directory.

### 1. Install Prerequisites

Install both CLI tools globally via npm (one-time setup):

```bash
npm install -g @mermaid-js/mermaid-cli bpmn-to-image
```

Verify they are available:

```bash
mmdc --version
bpmn-to-image --help
```

### 2. Regenerate the Mermaid Flowchart

**Source:** `diagrams/mermaid/process.mmd`
**Output:** `diagrams/mermaid/process.svg`

```bash
mmdc -i diagrams/mermaid/process.mmd -o diagrams/mermaid/process.svg -t default
```

### 3. Regenerate the BPMN Diagram

**Source:** `diagrams/bpmn/process.bpmn`
**Output:** `diagrams/bpmn/process.png`

```bash
bpmn-to-image "diagrams/bpmn/process.bpmn:diagrams/bpmn/process.png"
```

## Versioning and Change History

- **CHANGELOG.md** — Lists every version of the process package with dated entries describing what was added, changed, or removed. Follows [Keep a Changelog](https://keepachangelog.com/) format.
- **validation-log.md** — Records cross-artifact consistency checks (e.g., verifying the SOP, Mermaid diagram, and BPMN diagram all describe the same workflow).
- **Git history** — The repository is version-controlled with Git. Use `git log` for the full commit-level history.
