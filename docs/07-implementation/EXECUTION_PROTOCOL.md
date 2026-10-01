# Implementation Execution Protocol

## Purpose
This document establishes the mandatory operational cycle for authoring and verifying code during MVP development. It prevents premature declarations of completion and ensures that every code change is executed, tested, verified, and logged before proceeding.

---

## 1. The 15-Step Implementation Loop

For every distinct development task, the AI agent must execute this sequence without exception:

$$\begin{aligned}
&\text{1. READ} \longrightarrow \text{2. INSPECT} \longrightarrow \text{3. UNDERSTAND} \longrightarrow \text{4. PLAN} \longrightarrow \text{5. LOG DECISION (if needed)} \\
&\longrightarrow \text{6. IMPLEMENT} \longrightarrow \text{7. RUN} \longrightarrow \text{8. TEST} \longrightarrow \text{9. INSPECT RESULT} \longrightarrow \text{10. FIX} \\
&\longrightarrow \text{11. RE-RUN} \longrightarrow \text{12. VERIFY} \longrightarrow \text{13. DOCUMENT} \longrightarrow \text{14. UPDATE STATE} \longrightarrow \text{15. NEXT TASK}
\end{aligned}$$

1. **READ**: Read the specific feature specification (`FEATURE_SPEC_TEMPLATE.md`) and requirements.
2. **INSPECT**: Inspect relevant existing source files, functions, and module interfaces.
3. **UNDERSTAND**: Understand existing dependencies, data models, and potential side effects.
4. **PLAN**: Outline the minimal code modifications required.
5. **LOG DECISION**: If an architectural trade-off is required, record it in `.ai/DECISIONS.md`.
6. **IMPLEMENT**: Write the targeted code change. Do not perform unrelated refactoring.
7. **RUN**: Execute the code, launch the script, or trigger the server runtime.
8. **TEST**: Run automated unit tests or interactive verification inputs.
9. **INSPECT RESULT**: Scrutinize actual output, console logs, and return codes.
10. **FIX**: If defects or errors are detected, diagnose and patch immediately.
11. **RE-RUN**: Execute the test again to ensure the patch resolved the issue.
12. **VERIFY**: Confirm that observed results strictly match the expected acceptance criteria.
13. **DOCUMENT**: Record task output, verification evidence, and bugs in `docs/08-testing/` and `.ai/BRAIN.md`.
14. **UPDATE STATE**: Update `.ai/STATE.md` to reflect task completion.
15. **NEXT TASK**: Proceed to the next prioritized task in `docs/07-implementation/BUILD_ORDER.md`.

---

## 2. Implementation Safety & Scope Increment Rules

- **Small Coherent Increments**: Author one functional unit or component at a time. Never implement multiple large, unrelated features in a single batch before testing.
- **Inspect Before Modifying**: Never edit a file without reading its complete contents and understanding its callers first.
- **Execution Over Static Inspection**: Never declare that code works based purely on reading syntax. Execution and observed output are mandatory.
- **Regression Check**: After modifying any shared module, re-run tests for previously completed features to ensure no regressions were introduced.

---

## 3. Task Completion Record Schema

When recording task execution in `.ai/BRAIN.md` or implementation notes, use this schema:

- **Task ID**: `[e.g., TASK-2.1]`
- **Objective**: *[Specific capability implemented]*
- **Files Affected**: *[List of modified or created file paths]*
- **Implementation Summary**: *[Key logic or functions added]*
- **Test Performed**: *[Command, test script, or manual verification steps]*
- **Observed Result**: *[Actual output, exit codes, and UI responses]*
- **Verification Status**: `NOT STARTED` | `IN PROGRESS` | `BLOCKED` | `FAILED` | `VERIFIED` | `COMPLETED`
- **Timestamp**: `[YYYY-MM-DD HH:MM:SS LOCAL TIME]`

> **Rule**: A task status cannot transition to `COMPLETED` unless its status is first `VERIFIED`.

---

## 4. Failure Recovery & Triage Protocol

When an implementation step fails or encounters a blocker:
1. **Stop Expanding Scope**: Immediately halt new feature development on that branch.
2. **Diagnose Root Cause**: Classify whether the failure is a code bug, missing dependency, environment mismatch, architectural flaw, or invalid requirement.
3. **Apply Minimal Fix**: Attempt the smallest targeted fix and re-verify.
4. **Deploy Fallback Heuristic**: If external service or algorithm fails, activate the pre-planned fallback (e.g., local seed data or deterministic heuristic).
5. **Descope if Necessary**: If resolution cannot be achieved within the 24-hour time constraint:
   - Formally descope the feature from the MVP.
   - Document the rationale in `.ai/BRAIN.md` and `docs/08-testing/BUG_LOG.md`.
   - Protect and stabilize the remaining working MVP.
