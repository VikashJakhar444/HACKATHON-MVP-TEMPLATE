# Test Case Template

> **Instructions**: Use this template to document specific test cases for core features and integration flows. Every test case requires observable evidence before it can be marked as `PASS`.

---

## 1. Test Overview
- **Test ID**: `TC-001`
- **Target Feature**: *[e.g., Data Transformation Engine / FEAT-001]*
- **Test Type**: `SMOKE` | `FUNCTIONAL` | `INTEGRATION` | `ERROR_PATH` | `MANUAL_UI`
- **Objective**: *[Specific behavior or contract being validated]*

---

## 2. Test Execution Details

### Preconditions
- Application running on target port/environment.
- Test seed dataset initialized or empty state prepared.

### Test Inputs & Parameters
```json
{
  "test_input": "Sample test payload",
  "mode": "standard"
}
```

### Step-by-Step Execution Procedure
1. Navigate to target view or invoke test function.
2. Provide specified test input parameters.
3. Trigger processing action.
4. Observe system response and output data.

---

## 3. Results & Verification Evidence

### Expected Result
*Precise description of expected outcome, return value, or UI state.*

- 

### Actual Observed Result
*Verbatim log output, return payload, or visual UI observation.*

- 

### Execution Evidence
*Command output, terminal snippet, or observed log:*
```text
[Insert terminal command output or assertion log here]
```

---

## 4. Test Evaluation & Status
- **Status**: `PASS` | `FAIL` | `BLOCKED`
- **Execution Timestamp**: `[YYYY-MM-DD HH:MM:SS LOCAL TIME]`
- **Tester / Agent**: AI Agent / Developer
- **Notes / Observations**: 

> **RULE**: A test case CANNOT be marked `PASS` without documented, observed output matching the expected result.
