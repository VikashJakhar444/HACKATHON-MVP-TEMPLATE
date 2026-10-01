# Bug & Defect Tracking Log

## Purpose
This document is the permanent, append-only ledger for tracking defects, runtime exceptions, and regressions discovered during development, testing, and rehearsals.

## Operating Rules
- **Append-Only**: Never delete, rewrite, or hide historical bugs.
- **Triage Discipline**: Critical bugs impacting the primary demo path must be resolved immediately or the affected feature must be formally descoped before checkpoint advancement.
- **Verification Requirement**: A bug cannot be marked `RESOLVED` without a verified re-test record.

---

## Bug Log Schema
```text
[YYYY-MM-DD HH:MM:SS LOCAL TIME]

BUG ID: BUG-XXX
DISCOVERED DURING: <Unit Test / Integration / Manual UI / Demo Rehearsal>
FEATURE: <Feature Name / ID>
DESCRIPTION: <Clear explanation of defect or crash>
SEVERITY: CRITICAL | HIGH | MEDIUM | LOW
REPRODUCTION STEPS:
1. <Step 1>
2. <Step 2>
EXPECTED: <Expected system behavior>
ACTUAL: <Actual observed error or behavior>
ROOT CAUSE: <Underlying defect identified>
FIX: <Summary of code changes made>
VERIFICATION: <Command and output proving fix works>
STATUS: OPEN | IN_PROGRESS | RESOLVED | DESCOPED
```

---

## Logged Defects

*(No defects logged yet. Log initialized and ready for development.)*
