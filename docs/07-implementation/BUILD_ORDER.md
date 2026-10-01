# Implementation Build Order & Engineering Discipline

## Purpose
This document establishes the mandatory build order and operational discipline for implementing hackathon MVPs. It ensures that development efforts are strictly prioritized toward functional completeness, reliability, and demonstrability before cosmetic refinement.

---

## 1. The 14-Step Default Build Order

To guarantee that working software is delivered within the 24-hour limit, follow this sequential order strictly:

$$\begin{aligned}
&\text{1. Confirm Requirements} \longrightarrow \text{2. Create Project Skeleton} \longrightarrow \text{3. Establish Entry Point} \\
&\longrightarrow \text{4. Establish Data Layer} \longrightarrow \text{5. Implement Core Logic} \longrightarrow \text{6. Implement Primary Flow} \\
&\longrightarrow \text{7. Implement Core Features} \longrightarrow \text{8. Connect UI \& Logic} \longrightarrow \text{9. Add Error States} \\
&\longrightarrow \text{10. Test Functionality} \longrightarrow \text{11. Fix Regressions} \longrightarrow \text{12. Polish UI/UX} \\
&\longrightarrow \text{13. Prepare Demo Script} \longrightarrow \text{14. Final Verification}
\end{aligned}$$

1. **Confirm Requirements & PRD**: Validate that scope, inputs, outputs, and acceptance criteria are unambiguous.
2. **Create Minimal Project Skeleton**: Initialize minimal directory structure and single configuration file.
3. **Establish Application Entry Point**: Create the primary runnable file (e.g., `app.py`, `index.html`, `server.js`).
4. **Establish Data & Storage Layer**: Implement schema definitions, local SQLite/JSON helpers, and seed fixtures.
5. **Implement Core Business Logic Engine**: Author the core algorithms, transformations, or calculations in isolation.
6. **Implement Primary User Flow (Happy Path)**: Wire the central input-to-output loop.
7. **Implement Remaining Core Features (4–5 total)**: Complete supporting logic and the core differentiator.
8. **Connect UI & Logic**: Integrate the presentation layer with backend/computation services.
9. **Add Validation & Explicit Error States**: Harden inputs, handle exceptions, and display clear user alert states.
10. **Test Functionality & Execute Verification**: Run unit tests and manual end-to-end verification scripts.
11. **Fix Failures & Regressions**: Resolve all blockers before attempting visual upgrades.
12. **Polish UI/UX & Aesthetics**: Enhance spacing, typography, colors, animations, and micro-interactions.
13. **Prepare Demo Scenario & Pitch Script**: Finalize the 3-minute presentation narrative and verified seed data.
14. **Final Verification**: Perform an uninterrupted live dry run of the entire demo flow.

> **CRITICAL RULE**: Never spend the first half of the hackathon polishing UI before the core business logic and primary flow are fully operational and verified.

---

## 2. AI Implementation Discipline

When active coding begins, the AI coding agent must strictly adhere to these engineering rules:

- **Inspect Before Editing**: Always read existing files, dependencies, and module exports before creating new files or modifying code.
- **Make Small, Incremental Changes**: Implement single functions or components at a time; verify each step.
- **Reuse Existing Code**: Leverage existing utilities, styling tokens, and helper functions rather than duplicating logic.
- **Verify After Changes**: Execute code and run tests immediately after modifying files. Never declare a task complete without verification.
- **Do Not Rewrite Unrelated Files**: Avoid collateral refactoring of working code.
- **Do Not Install Dependencies Without Justification**: Every package must be justified in `TECH_STACK_DECISION.md`.
- **Do Not Silently Change Architecture**: Document any necessary architectural pivots in `.ai/DECISIONS.md`.
- **Maintain Audit Trail**: Log significant actions, milestones, and results in `.ai/BRAIN.md`.
- **Update Active State**: Reflect milestone completions and active blockers in `.ai/STATE.md`.
