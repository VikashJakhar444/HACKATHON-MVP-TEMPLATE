# CONTEXT_RECOVERY.md — Context Loss & Session Recovery Protocol

## Purpose
This document establishes the recovery procedure when chat context is truncated, conversation history is lost, a session restarts, or development moves across different AI agents or machines.

---

## 1. Zero-History Recovery Sequence

When conversational memory is missing, **DO NOT** prompt the user to re-explain project history. Reconstruct operational context directly from the repository using this 9-step protocol:

1. **Read Governance Root**: Read [AGENTS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/AGENTS.md) and [.ai/RULES.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/RULES.md).
2. **Read Operational State**: Read [.ai/STATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/STATE.md) to inspect the last logged active phase and task.
3. **Audit Chronological Ledger**: Read the last 5–10 entries in [.ai/BRAIN.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/BRAIN.md) to understand recent reasoning, completed tasks, and failures.
4. **Read Decision Records**: Read [.ai/DECISIONS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/DECISIONS.md) to identify approved architectural trade-offs.
5. **Inspect Physical Files**: Read directory listings in `src/`, `docs/`, and `tests/` to verify physical deliverables.
6. **Execute Consistency Audit**: Compare logged status in `STATE.md` against actual code and test files.
7. **Identify Unfinished Tasks**: Inspect `docs/07-implementation/` to locate active or incomplete task IDs.
8. **Reconcile Discrepancies**: If files on disk differ from state claims, reconcile `STATE.md` to match reality.
9. **Resume from Last Verified State**: Pick up execution from the exact verified milestone.

---

## 2. Recovery Consistency Check

Always validate state claims against empirical artifacts:

| Dimension | State Claim | Repository Evidence Source | Action if Inconsistent |
| :--- | :--- | :--- | :--- |
| **Problem / PRD** | Phase 1–3 Complete | `docs/01-problem/` & `docs/04-product/PRD_TEMPLATE.md` | Re-generate missing PRD sections before coding. |
| **Architecture** | Phase 4 Complete | `docs/05-technical/` & `docs/06-architecture/` | Lock architecture before authoring features. |
| **Core Features** | "Feature X Complete" | `src/` code + `docs/08-testing/` test evidence | If test evidence missing, run test before marking complete. |
| **Working App** | "Application Runnable" | Execute run command (`python app.py` / `npm start`) | If execution fails, fix startup before authoring new features. |

> **Rule**: If state claims and repository evidence conflict, **HALT** and reconcile state before writing new code. Never trust a stale state file over physical code reality.

---

## 3. Partial Task Recovery (In-Progress Tasks)

If an interrupted task was marked `IN_PROGRESS`:

1. **Identify Modified Files**: Check recent files modified in `src/` or `tests/`.
2. **Test Application Integrity**: Execute the application entry point to verify it still compiles/runs.
3. **Run Unit / Functional Tests**: Execute test suite to see which assertions pass or fail.
4. **Evaluate Safe Resume vs. Rollback**:
   - If changes are coherent and close to completion: Complete the logic, run tests, and verify.
   - If changes introduced unrecoverable syntax errors or broken state: Revert the unverified edits to the last working checkpoint and restart that single task cleanly.
5. **Update State & Resume**: Log the recovery in `.ai/BRAIN.md` and continue.
