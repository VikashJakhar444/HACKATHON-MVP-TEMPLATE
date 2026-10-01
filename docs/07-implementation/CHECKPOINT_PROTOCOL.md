# Mandatory Checkpoint Protocol

## Purpose
This document defines the quality gates and stage checkpoints required across the 24-hour hackathon lifecycle. It enforces disciplined phase transitions, prevents compounding errors, and guarantees that work is verified before progressing.

---

## 1. Project Quality Checkpoints

```text
[CHECKPOINT 0: Plan Lock] ──► [CHECKPOINT 1: Foundation] ──► [CHECKPOINT 2: Core Flow]
                                                                    │
[CHECKPOINT 5: Demo Build] ◄── [CHECKPOINT 4: Integration] ◄── [CHECKPOINT 3: Core Features]
        │
        ▼
[CHECKPOINT 6: Final Lock] ──► [READY FOR DEMO]
```

---

### CHECKPOINT 0 — PLAN LOCK (Pre-Implementation Gate)
*Verification criteria before authoring any application code:*
- [ ] Validated Problem Analysis documented (`docs/01-problem/`).
- [ ] Validated Gap Analysis documented (`docs/02-research/`).
- [ ] Product Requirements Document (PRD) locked (`docs/04-product/`).
- [ ] MVP Scope (Must/Should/Could/Out of Scope) finalized (`docs/03-requirements/`).
- [ ] Technical Requirements Document (TRD) and Architecture approved (`docs/05-technical/` & `docs/06-architecture/`).
- [ ] 14-Step Build Order established (`docs/07-implementation/BUILD_ORDER.md`).

---

### CHECKPOINT 1 — FOUNDATION GATE
*Verification criteria after project initialization:*
- [ ] Application starts reliably via a single command.
- [ ] Project skeleton and runtime environment verified.
- [ ] Storage layer / local database initializes and performs basic CRUD operations.
- [ ] No unhandled dependency or environment warnings.

---

### CHECKPOINT 2 — CORE FLOW GATE (Happy Path)
*Verification criteria for primary user journey:*
- [ ] Primary user interaction loop executes end-to-end without manual intervention.
- [ ] Core data ingestion, transformation, and output rendering function deterministically.
- [ ] Valid inputs produce expected outcomes.
- [ ] Application does not crash on boundary or null inputs.

---

### CHECKPOINT 3 — CORE FEATURES GATE
*Verification criteria for individual MVP capabilities:*
- [ ] All 4–5 core MVP features are individually implemented.
- [ ] Core differentiator / WOW mechanism operates with verified evidence.
- [ ] Each feature passes its dedicated test cases in `docs/08-testing/`.

---

### CHECKPOINT 4 — INTEGRATION GATE
*Verification criteria for cohesive system operation:*
- [ ] All features interoperate seamlessly without state corruption or race conditions.
- [ ] UI states (Empty, Loading, Success, Failure) transition smoothly.
- [ ] Error messages provide clear, non-technical guidance to users.

---

### CHECKPOINT 5 — DEMO BUILD GATE
*Verification criteria for presentation readiness:*
- [ ] Application launches cleanly from scratch in a fresh terminal session.
- [ ] Demo seed datasets load instantly and reliably.
- [ ] Zero broken controls, placeholder text, or debug print statements on screen.
- [ ] No exposed secrets, private tokens, or hardcoded sensitive credentials.

---

### CHECKPOINT 6 — FINAL LOCK GATE
*Strict feature freeze:*
- [ ] **NO NEW MAJOR FEATURES**: Feature development is completely closed.
- [ ] Only critical bug fixes, stability patches, and minor visual polish permitted.
- [ ] 3-minute pitch rehearsal completed and timed.

---

## 2. Checkpoint Governance & Blocker Rule

- **No Premature Advancement**: The AI agent must NEVER advance past a checkpoint while a critical blocker remains open.
- **Explicit Blocker Resolution**: A blocker may be resolved only by:
  1. Fixing the underlying defect and verifying the fix, OR
  2. Formally descoping the affected feature, updating documentation, and recording the decision in `.ai/BRAIN.md`.
- **Never Hide Blockers**: All defects and known limitations must be recorded in `docs/08-testing/BUG_LOG.md`.

---

## 3. No Last-Minute Feature Explosion

Once **CHECKPOINT 6** is reached:
- Strictly prohibit adding "just one more feature" or speculative enhancements.
- Channel 100% of remaining time into testing, rehearsing the live demo, and verifying presentation alignment.
