# Runtime State Management Protocol

## Purpose
This document establishes the formal structure, update triggers, and time-tracking rules for `.ai/STATE.md`. It guarantees that `.ai/STATE.md` remains an accurate, high-fidelity operational snapshot of the live hackathon project.

---

## 1. Standard STATE.md Operational Schema

The `.ai/STATE.md` document must conform to this standard schema throughout active development:

```markdown
# Project State

## 1. Operational Overview
- **Project Name**: <Name of hackathon project>
- **Project Status**: <NEW | ACTIVE | BLOCKED | DEMO_PREP | FINAL_AUDIT | COMPLETED>
- **Current Phase**: <Phase 0 to Phase 12 - Name>
- **Current Active Task**: <Task ID & Short Title>
- **Task Status**: <NOT_STARTED | IN_PROGRESS | VERIFYING | BLOCKED>
- **Last Verified Milestone**: <e.g., Checkpoint 2: Core Flow Verified>
- **Last Updated**: <YYYY-MM-DD HH:MM:SS LOCAL TIME>

---

## 2. Timeline & Budget Tracking
- **Start Time**: <Timestamp of activation>
- **Hackathon Deadline**: <Target timestamp / e.g., 24 Hours from Start>
- **Estimated Time Remaining**: <Hours / Minutes remaining>
- **Scope Triage Level**: <NORMAL | TIME_CONSTRAINED | CRITICAL_PATH_ONLY>

---

## 3. Work Status Breakdown
- **Completed Milestones**:
  - [x] Milestone 1
  - [x] Milestone 2
- **In-Progress Tasks**:
  - [ ] Task ID: Description
- **Active Blockers**:
  - <None | Blocker description and impacted component>
- **Known Issues & Technical Debt**:
  - <Itemized list of non-critical edge cases>
- **Active Risks & Mitigations**:
  - <Identified risk and active fallback path>

---

## 4. Next Immediate Action
- **Immediate Next Step**: <Exact single action to execute next>
```

---

## 2. State Update Triggers & Rules

Update `.ai/STATE.md` **ONLY** upon meaningful lifecycle events:

### Update Required When:
- Completing a Phase Gate (e.g., Gate 1 Problem Lock $\rightarrow$ Gate 2 Gap Lock).
- Passing a Project Checkpoint (e.g., Checkpoint 1 Foundation $\rightarrow$ Checkpoint 2 Core Flow).
- Transitioning between implementation tasks in `BUILD_ORDER.md`.
- Formally resolving or descoping a blocker.
- Discovering a new critical defect that blocks a path.
- Making an explicit scope reduction or architectural trade-off.

> **Anti-Noise Rule**: Do not update `STATE.md` on every trivial line edit or scratch execution. Update it when a milestone, task state, or blocker changes.

---

## 3. Time Remaining & Scope Adjustments

If a project deadline is known:
- Compute time remaining at each phase transition.
- **Trigger Triage Rules**:
  - If $< 8$ hours remain and core features are unverified: Activate `CRITICAL_PATH_ONLY` mode. Formally descope all `OPTIONAL` and `SHOULD-HAVE` features.
  - If $< 3$ hours remain: Freeze all feature development immediately. Enter Phase 10 (Demo Prep) and Phase 11 (Presentation Prep).
