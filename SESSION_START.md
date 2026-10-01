# SESSION_START.md — Standard Session Startup Procedure

## Purpose
This document defines the mandatory 7-step startup protocol that any AI agent must execute at the beginning of every interaction session to re-establish situational awareness rapidly and reliably.

---

## The 7-Step Startup Protocol

### Step 1 — Load Governance & State Layer
Read the authoritative governance files:
- [AGENTS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/AGENTS.md)
- [.ai/RULES.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/RULES.md)
- [.ai/STATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/STATE.md)
- [.ai/BRAIN.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/BRAIN.md) (recent entries)
- [.ai/DECISIONS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/DECISIONS.md)

### Step 2 — Inspect Physical Repository
Inspect actual disk contents:
- `src/` (source files created, entry point existence)
- `docs/` (phase documentation completed)
- `tests/` and `docs/08-testing/` (test cases, verification records, bug logs)
- `scripts/`, `assets/`, `data/`

### Step 3 — Classify Project State
Determine the high-level operating status:
- `NEW PROJECT`: Problem statement not yet ingested.
- `ACTIVE PROJECT`: Problem defined; planning or implementation in progress.
- `BLOCKED PROJECT`: Critical blocker encountered requiring diagnosis or descoping.
- `DEMO PREPARATION`: Implementation complete; rehearsals and slide deck in progress.
- `FINAL AUDIT`: Project undergoing binary readiness check.
- `COMPLETED`: Project verified and ready for judging.

### Step 4 — Determine Current Phase
Map repository status to the 13 phases in [docs/07-implementation/HACKATHON_EXECUTION_MAP.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/docs/07-implementation/HACKATHON_EXECUTION_MAP.md).

### Step 5 — Identify Next Immediate Action
Identify precisely ONE high-priority, actionable task from `.ai/STATE.md` or the active phase plan.

### Step 6 — Check Scope Bounds
Ensure the target action belongs strictly to the current phase gate and does not violate 24-hour feasibility.

### Step 7 — Execute & Verify
Follow the appropriate phase protocol (`EXECUTION_PROTOCOL.md`, `CHECKPOINT_PROTOCOL.md`, etc.).

---

## Internal Session Initialization Summary

At the conclusion of the startup sequence, the AI agent must establish this internal state baseline before taking action:

```text
==================================================
SESSION INITIALIZATION BASELINE
==================================================
PROJECT: <Project Name / "Hackathon MVP Template">
PROJECT STATE: <NEW | ACTIVE | BLOCKED | DEMO_PREP | FINAL_AUDIT | COMPLETED>
CURRENT PHASE: <Phase Number & Name>
CURRENT TASK: <Single Active Task ID & Title>
COMPLETED MILESTONES: <List of completed gates/features>
OPEN BLOCKERS: <None | Specific Blocker ID>
NEXT ACTION: <Immediate actionable step to execute>
TIME CONSTRAINT: <e.g., 24 Hours / Unknown>
SCOPE LIMIT: <4–5 Core Features / Focused MVP>
==================================================
```

> **Discipline Rule**: Do not spend session turns producing lengthy narrative recaps for the user. Establish state internally, state the immediate next action concisely, and execute.
