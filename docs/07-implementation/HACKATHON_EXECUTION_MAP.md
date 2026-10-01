# Master Hackathon Execution Map

## Purpose
This document provides a comprehensive end-to-end operational roadmap spanning the entire hackathon lifecycle across 13 structured phases (Phase 0 to Phase 12).

---

## The 13 Execution Phases

```text
[0. ACTIVATE] ──► [1. PROBLEM] ──► [2. GAP] ──► [3. MVP LOCK] ──► [4. TECH LOCK]
                                                                        │
[8. VERIFY] ◄── [7. INTEGRATE] ◄── [6. CORE BUILD] ◄── [5. FOUNDATION] ◄┘
    │
    ▼
[9. POLISH] ──► [10. DEMO PREP] ──► [11. PPT PREP] ──► [12. FINAL AUDIT] ──► [READY]
```

---

### PHASE 0 — ACTIVATE
- **Objective**: Ingest raw problem statement, parameters, constraints, and initialize project logs.
- **Required Inputs**: User problem statement in `ACTIVATION_INPUT_TEMPLATE.md`.
- **Expected Outputs**: Initialized `.ai/BRAIN.md` and `.ai/STATE.md`.
- **Exit Condition**: Problem statement captured verbatim; active state set to Phase 1.
- **Typical Risks**: Inventing unstated requirements; bypassing governance.

---

### PHASE 1 — UNDERSTAND PROBLEM
- **Objective**: Decompose the statement into users, context, pain points, and root causes.
- **Required Inputs**: Raw statement.
- **Expected Outputs**: Populated `PROBLEM_ANALYSIS_TEMPLATE.md`.
- **Exit Condition**: GATE 1 (Problem Lock) verified.
- **Typical Risks**: Jumping immediately to tech solutions without understanding user pain.

---

### PHASE 2 — VALIDATE GAP & RESEARCH
- **Objective**: Evaluate current solutions, substantiate the unmet need, and perform time-boxed research if needed.
- **Required Inputs**: Problem definition.
- **Expected Outputs**: Populated `GAP_ANALYSIS_TEMPLATE.md` and `RESEARCH_LOG.md`.
- **Exit Condition**: GATE 2 (Gap Lock) verified; research concluded.
- **Typical Risks**: Open-ended research rabbit holes; unsupported "unsolved problem" claims.

---

### PHASE 3 — LOCK MVP SCOPE
- **Objective**: Synthesize solution concept, evaluate candidate features, and select 4–5 core capabilities.
- **Required Inputs**: Problem analysis and gap analysis.
- **Expected Outputs**: Populated `SOLUTION_CONCEPT_TEMPLATE.md`, `MVP_SCOPE_TEMPLATE.md`, `MVP_DECISION_RECORD.md`, and `PRD_TEMPLATE.md`.
- **Exit Condition**: GATE 3 (MVP Lock) passed; explicit out-of-scope boundaries documented.
- **Typical Risks**: Scope creep; generic filler features (unnecessary auth, admin dashboards).

---

### PHASE 4 — LOCK TECHNICAL PLAN & ARCHITECTURE
- **Objective**: Select simplest reliable stack, design architecture, data models, APIs, and implementation plan.
- **Required Inputs**: PRD and MVP scope.
- **Expected Outputs**: Populated `TRD_TEMPLATE.md`, `TECH_STACK_DECISION.md`, `ARCHITECTURE_TEMPLATE.md`, `DATA_MODEL_TEMPLATE.md`, and `IMPLEMENTATION_PLAN_TEMPLATE.md`.
- **Exit Condition**: GATE 4 (Tech Lock) passed; Checkpoint 0 verified.
- **Typical Risks**: Over-engineering tech stack; premature microservices or cloud dependencies.

---

### PHASE 5 — BUILD FOUNDATION
- **Objective**: Initialize project skeleton, entry point, and local storage mechanisms.
- **Required Inputs**: Technical plan and build order.
- **Expected Outputs**: Runnable application skeleton and data layer in `src/`.
- **Exit Condition**: Checkpoint 1 (Foundation Gate) verified.
- **Typical Risks**: Unhandled dependency conflicts; broken environment setup.

---

### PHASE 6 — BUILD CORE FEATURES
- **Objective**: Implement the primary business logic engine and all 4–5 core features.
- **Required Inputs**: Feature specs and data layer.
- **Expected Outputs**: Core business logic modules and differentiator in `src/`.
- **Exit Condition**: Checkpoint 2 (Core Flow) and Checkpoint 3 (Core Features) verified.
- **Typical Risks**: Edge-case crashes; complex algorithms exceeding time limits.

---

### PHASE 7 — INTEGRATE
- **Objective**: Connect presentation layer (UI) to core business logic and handle state transitions.
- **Required Inputs**: UI views and core feature modules.
- **Expected Outputs**: End-to-end interactive application.
- **Exit Condition**: Checkpoint 4 (Integration Gate) verified.
- **Typical Risks**: UI/logic impedance mismatch; state corruption.

---

### PHASE 8 — VERIFY & TEST
- **Objective**: Execute automated/manual test suite, log verification evidence, and fix defects.
- **Required Inputs**: Integrated application.
- **Expected Outputs**: Populated test cases in `docs/08-testing/` and resolved `BUG_LOG.md`.
- **Exit Condition**: GATE 6 (Verify Gate) passed; all critical bugs resolved.
- **Typical Risks**: Relying on static inspection rather than empirical test execution.

---

### PHASE 9 — POLISH UI/UX & STATES
- **Objective**: Refine typography, contrast, spacing, error alerts, and empty states.
- **Required Inputs**: Verified working application.
- **Expected Outputs**: Polished, professional UI.
- **Exit Condition**: Checkpoint 5 (Demo Build Gate) passed.
- **Typical Risks**: Breaking core functionality during cosmetic styling.

---

### PHASE 10 — DEMO PREPARATION
- **Objective**: Lock feature development, verify seed demo fixtures, and rehearse 3-minute pitch.
- **Required Inputs**: Polished application.
- **Expected Outputs**: Populated `DEMO_READINESS_CHECKLIST.md`.
- **Exit Condition**: GATE 7 (Demo Lock) and Checkpoint 6 (Final Lock) verified.
- **Typical Risks**: Unrehearsed live presentation; relying on live network with no backup.

---

### PHASE 11 — PRESENTATION & SLIDE CONTENT
- **Objective**: Prepare structured slide deck content matching the real working product.
- **Required Inputs**: PRD, demo script, and verification records.
- **Expected Outputs**: Populated `PRESENTATION_PLAN_TEMPLATE.md` and `PPT_CONTENT_TEMPLATE.md`.
- **Exit Condition**: GATE 8 (Presentation Gate) verified.
- **Typical Risks**: Presenting mockups or future roadmap as current working capabilities.

---

### PHASE 12 — FINAL AUDIT
- **Objective**: Conduct comprehensive binary audit (`READY` / `NOT READY`).
- **Required Inputs**: All documentation, code, test logs, and demo assets.
- **Expected Outputs**: Signed-off `FINAL_AUDIT_CHECKLIST.md` and final `.ai/BRAIN.md` log.
- **Exit Condition**: GATE 9 (Final Audit) verified with `READY` verdict.
- **Typical Risks**: Subjective grading; unresolved critical blockers.
