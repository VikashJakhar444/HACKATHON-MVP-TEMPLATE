# HACKATHON_START.md — Master Project Activation

## 1. Activation Overview
This is the **Master Activation Document** for the Hackathon MVP Template. When a user provides a new hackathon problem statement, this document instructs the AI agent on how to autonomously orchestrate the entire end-to-end engineering lifecycle—from problem decomposition to live demo and presentation preparation—without skipping quality gates or building unverified code.

---

## 2. Activation Input Format

To kick off a project, the user provides input following this schema (or pastes it into `docs/01-problem/ACTIVATION_INPUT_TEMPLATE.md`):

```text
HACKATHON PROBLEM STATEMENT: <Paste raw problem statement here>

[OPTIONAL METADATA]
HACKATHON NAME: <Name of event>
TIME LIMIT: <e.g., 24 Hours / 36 Hours> (Default: ~24 Hours)
TEAM SIZE: <Number of members>
MANDATORY TECHNOLOGY: <Specific frameworks/languages if enforced>
MANDATORY FEATURES: <Specific sponsor or hackathon requirements>
JUDGING CRITERIA: <Rubric criteria, e.g., Innovation 25%, Impact 25%, Technical 25%, Demo 25%>
SPECIAL CONSTRAINTS: <Offline-only, Mobile, Specific hardware, etc.>
AVAILABLE APIs / DATA: <Provided datasets, sponsor API keys, or SDKs>
DEPLOYMENT REQUIREMENT: <Localhost demo / Cloud deployment URL>
```

### Missing Information Rule:
- If optional parameters are omitted, mark them explicitly as `UNKNOWN`.
- **DO NOT** invent or fabricate constraints, sponsor requirements, or judging criteria.
- Proceed with known information; ask the user only if missing information materially changes the architecture or product direction.

---

## 3. The 21-Step Autonomous Activation Workflow

Once the problem statement is submitted, the AI agent executes this end-to-end pipeline:

$$\begin{aligned}
&\text{1. Ingest Statement} \longrightarrow \text{2. Decompose Problem} \longrightarrow \text{3. Evaluate Research Need} \longrightarrow \text{4. Time-Boxed Research (if needed)} \\
&\longrightarrow \text{5. Document Gap} \longrightarrow \text{6. Formulate Solution Concept} \longrightarrow \text{7. Generate Candidates} \longrightarrow \text{8. Select 4–5 Core MVP} \\
&\longrightarrow \text{9. Identify Differentiator} \longrightarrow \text{10. Lock PRD} \longrightarrow \text{11. Lock TRD} \longrightarrow \text{12. Select Stack} \\
&\longrightarrow \text{13. Design Architecture} \longrightarrow \text{14. Design Data/API} \longrightarrow \text{15. Lock Implementation Plan} \longrightarrow \text{16. Build Incrementally} \\
&\longrightarrow \text{17. Test \& Verify} \longrightarrow \text{18. Pass Checkpoints} \longrightarrow \text{19. Prepare Demo Script} \longrightarrow \text{20. Generate PPT Content} \\
&\longrightarrow \text{21. Execute Final Audit}
\end{aligned}$$

---

## 4. The 9 Mandatory Phase Gates

The agent must transition through these nine quality gates sequentially. No phase gate may be bypassed:

| Gate | Phase Name | Exit Requirement & Verification Criteria |
| :--- | :--- | :--- |
| **GATE 1** | **Problem Lock** | Problem analyzed, target user identified, core pain mapped, constraints extracted (`docs/01-problem/`). |
| **GATE 2** | **Gap Lock** | Existing approaches evaluated, unmet need substantiated, research stopped when sufficient (`docs/02-research/`). |
| **GATE 3** | **MVP Lock** | Solution concept established, 4–5 core features selected, out-of-scope boundaries locked (`docs/03-requirements/` & `docs/04-product/`). |
| **GATE 4** | **Tech Lock** | PRD, TRD, Tech Stack Decision, Architecture, Data Model, and Implementation Plan finalized (`docs/05-technical/` to `07-implementation/`). |
| **GATE 5** | **Build Gate** | Incremental coding executed in accordance with `BUILD_ORDER.md` (`src/`). |
| **GATE 6** | **Verify Gate** | All core logic and happy-path flows pass automated/manual tests with empirical evidence (`docs/08-testing/`). |
| **GATE 7** | **Demo Lock** | Primary end-to-end demonstration runs flawlessly without debug artifacts or manual overrides (`docs/09-demo/`). |
| **GATE 8** | **Presentation** | Pitch deck narrative and slide content finalized, strictly reflecting actual working capabilities (`docs/09-demo/`). |
| **GATE 9** | **Final Audit** | Project audit yields binary **`READY`** verdict (`docs/09-demo/FINAL_AUDIT_CHECKLIST.md`). |

---

## 5. Decision Escalation vs. Autonomous Action

- **Autonomous Execution**: The AI executes low-risk implementation tasks, component styling, routine bug fixes, test scripting, and standard refactoring autonomously.
- **Mandatory User Escalation**: The AI **MUST** halt and ask the user when:
  1. A major product direction or core use case is fundamentally ambiguous.
  2. Two critical constraints or requirements contradict each other.
  3. A technical choice would violate the 24-hour time constraint.
  4. A mandatory external credential, API key, or hardware dependency is unavailable.

---

## 6. Time & Scope Triage (24-Hour Timeline)

- **Default Time Budget**: Assume approximately 24 hours unless specified otherwise.
- **Continuous Classification**: Classify all work items as `CRITICAL`, `IMPORTANT`, or `OPTIONAL`.
- **Triage Under Pressure**:
  1. Protect core working functionality and primary user journey.
  2. Protect differentiating / WOW capability.
  3. Descope optional features and stretch goals immediately.
  4. Reduce UI complexity to maintain flawless execution.
  5. Never sacrifice test verification of the core MVP.

---

## 7. Audit & State Management Rules

- **On Activation**:
  - Record the activation timestamp, raw problem statement, and known constraints in `.ai/BRAIN.md`.
  - Update `.ai/STATE.md` with active phase (Phase 1: Understand Problem).
- **During Execution**:
  - Append every significant architectural decision, feature addition/removal, test failure, fix, and verification result in `.ai/BRAIN.md`.
  - Record ADRs in `.ai/DECISIONS.md`.
  - Maintain active task progress in `.ai/STATE.md`.
