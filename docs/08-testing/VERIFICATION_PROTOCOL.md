# Verification & Completion Protocol

## Purpose
This document establishes the formal criteria and empirical evidence requirements for verifying software capabilities in this repository. It prevents the AI agent from treating written code or surface rendering as completed functionality.

---

## 1. The Four Completion States

To eliminate ambiguity between authoring code and delivering working features, adhere strictly to these definitions:

$$\text{IMPLEMENTED} \longrightarrow \text{TESTED} \longrightarrow \text{VERIFIED} \longrightarrow \text{COMPLETED}$$

1. **`IMPLEMENTED`**:
   - Source code has been written and saved to the file system.
   - *Status*: The capability is unproven; no execution has occurred.
2. **`TESTED`**:
   - The code has been executed against automated assertions or interactive inputs.
   - *Status*: Execution occurred, but output has not yet been audited against acceptance criteria.
3. **`VERIFIED`**:
   - Empirical, observed output has been audited and matches the expected acceptance criteria with zero unhandled errors.
   - *Status*: Working functionality is proven by evidence.
4. **`COMPLETED`**:
   - The capability is `VERIFIED`, documented, integrated into the primary application, and has no open blockers or regressions.

---

## 2. Prohibited Completion Anti-Patterns

A feature or task must **NEVER** be marked as `COMPLETED` merely because:
- ❌ The code compiles without syntax errors.
- ❌ The web page renders or static HTML is displayed.
- ❌ The AI agent assumes or believes the logic should work.
- ❌ A UI button or form control physically exists on screen.
- ❌ A hardcoded or fabricated mock response appears without real processing (unless explicitly designated and documented as `MOCKED`).

---

## 3. Mandatory Verification Evidence Schema

Whenever marking a feature or milestone as `VERIFIED`, record the empirical proof using this format:

```text
==================================================
VERIFICATION EVIDENCE RECORD
==================================================
TARGET FEATURE: <Feature Name / ID>
TIMESTAMP: <YYYY-MM-DD HH:MM:SS LOCAL TIME>
COMMAND EXECUTED: <Terminal command or invocation script>
TEST PERFORMED: <Description of test case executed>
EXPECTED OUTPUT: <Precise expected result>
OBSERVED ACTUAL OUTPUT: <Verbatim output, response payload, or console log>
VERIFICATION RESULT: VERIFIED / FAILED
NOTES: <Any observed latency or boundary behavior>
==================================================
```

> **CRITICAL RULE**: Never fabricate, extrapolate, or falsify test results. If an execution fails or cannot be run, mark the status honestly as `FAILED` or `BLOCKED`.
