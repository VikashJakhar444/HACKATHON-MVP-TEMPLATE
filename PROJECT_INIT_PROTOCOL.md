# PROJECT_INIT_PROTOCOL.md — Fresh Project Initialization Protocol

## Purpose
This document defines the rules and baseline configuration for initializing a fresh hackathon project from this template. It ensures that every new hackathon starts from a clean, unpolluted state while retaining the complete governance and workflow infrastructure.

---

## 1. Fresh Project Baseline Rules

When creating a new project instance from this template:

### What MUST Be Preserved:
- ✅ **Complete AI Governance Layer**: `.ai/RULES.md`, `.ai/BRAIN.md` schema, `.ai/STATE.md` structure, `.ai/DECISIONS.md` format.
- ✅ **Standard Documentation Pipeline**: All templates under `docs/01-problem/` through `docs/09-demo/`.
- ✅ **Root Control Files**: `AGENTS.md`, `MASTER_AGENT.md`, `HACKATHON_START.md`, `START_HERE.md`, `HACKATHON_PROMPT.md`.
- ✅ **Empty Source & Asset Directories**: `src/`, `tests/`, `scripts/`, `assets/`, `data/`.

### What MUST NOT Be Carried Over From Prior Hackathons:
- ❌ **Old Source Code & Binaries**: Ensure `src/` is completely empty.
- ❌ **Old Problem Statements & Research**: Ensure `docs/` templates are clean and unpopulated with prior hackathon notes.
- ❌ **Prior Architectural Choices**: No pre-selected tech stacks or third-party SDKs carried over.
- ❌ **Old Test Datasets & API Keys**: Ensure `data/` and environment configs are clean.

---

## 2. Initial State Baseline

Every fresh project instance initializes with this exact state:

```text
==================================================
FRESH PROJECT INITIALIZATION STATE
==================================================
PROJECT STATUS: NEW PROJECT
PROBLEM GATE: NO PROBLEM LOCKED
MVP GATE: NO MVP LOCKED
TECH GATE: NO TECH LOCKED
APPLICATION CODE: NO APPLICATION CODE (src/ is empty)
DEPENDENCIES: NONE INSTALLED
GIT STATUS: NOT INITIALIZED (until user sets up repository)
==================================================
```

---

## 3. Project Naming Protocol

- **Provided Name**: If the user or hackathon provides an explicit product/project name in the activation prompt, use it immediately.
- **Concept-Derived Name**: If no name is provided, use `[TEMPORARY_PROJECT_NAME]` during Phase 1 (Problem Understanding) and assign a clean, descriptive product name in Phase 3 (Lock MVP Scope) based on the core value proposition.
- **Rule**: Never invent a generic, marketing-heavy, or misleading product name prior to understanding the problem.
