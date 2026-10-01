# Task Lock & Scope Containment Protocol

## Purpose
This document establishes the task-locking mechanism that prevents context switching, collateral code churn, and speculative feature creep during active coding sessions.

---

## 1. Task Lock Lifecycle

$$\text{LOCK TASK} \longrightarrow \text{WORK WITHIN SCOPE} \longrightarrow \text{EXECUTE \& TEST} \longrightarrow \text{VERIFY} \longrightarrow \text{DOCUMENT} \longrightarrow \text{CLOSE TASK}$$

1. **Lock Task**: Formally select a single active task ID from `IMPLEMENTATION_PLAN_TEMPLATE.md` or `BUILD_ORDER.md`.
2. **Work Within Scope**: Modify strictly the files and functions designated for that task.
3. **Execute & Test**: Run code and unit assertions.
4. **Verify**: Ensure empirical output matches task objective.
5. **Document**: Record evidence in `docs/08-testing/` and `.ai/BRAIN.md`.
6. **Close Task**: Update `.ai/STATE.md` and unlock for the next task.

---

## 2. Task Definition Schema

Every active task must be defined before execution begins:

```text
==================================================
ACTIVE TASK LOCK
==================================================
TASK ID: TASK-XXX
TASK NAME: <Concise Task Title>
OBJECTIVE: <Specific capability being implemented>
SCOPE BOUNDARY: <Explicit list of what will be modified and what will NOT>
DEPENDENCIES: <Prior tasks required>
FILES EXPECTED TO CHANGE: <Specific file paths>
VERIFICATION METHOD: <Automated test command or interactive verification script>
TASK STATUS: LOCKED & IN_PROGRESS
==================================================
```

---

## 3. Interrupt Handling & Triage Rules

While a task is locked, new bugs or ideas must be triaged immediately into one of three categories:

| Category | Definition | Action to Take |
| :--- | :--- | :--- |
| **`BLOCKING`** | Defect prevents current task from running or compiling. | Halt task; diagnose and fix root cause immediately; re-run task. |
| **`IMPORTANT`** | Flaw or gap discovered in a separate, non-active module. | Log in `docs/08-testing/BUG_LOG.md`; do **NOT** switch context; continue current task. |
| **`NON-BLOCKING`** | Cosmetic improvement or speculative new feature idea. | Defer to stretch backlog; do **NOT** interrupt current task. |

> **Rule**: Never abandon an in-progress task for non-blocking secondary issues. Finish, verify, and close the current lock first.

---

## 4. The "No Feature Drift" Rule

The AI agent must **NEVER** add a new component, UI view, or API endpoint merely because:
- ❌ It looks cool or was easy to implement.
- ❌ The AI agent thinks "a real app normally has this".
- ❌ A competitor or template includes it.
- ❌ It increases visual complexity or feature count.

Every line of code and feature added MUST have direct, documented traceability to:
1. The validated **Problem Definition** (`docs/01-problem/`).
2. The documented **Gap Analysis** (`docs/02-research/`).
3. The locked **PRD Requirements** (`docs/04-product/`).
4. Necessary **Technical Reliability & Error Handling** (`docs/05-technical/`).
