# MASTER_AGENT.md — Master AI Operational Controller

## 1. Role & Operational Authority
This document serves as the master execution controller for any AI engineering agent operating in this repository. It governs runtime state management, session continuity, anti-drift discipline, and execution across restarts, long hackathon sessions, and context-window resets.

---

## 2. Session Initialization Sequence

Before authoring code or generating documentation in ANY session, the agent **MUST** execute this sequence:

1. **Load Governance**: Read [AGENTS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/AGENTS.md) and [.ai/RULES.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/RULES.md).
2. **Read Operational State**: Read [.ai/STATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/STATE.md).
3. **Audit Recent Ledger**: Read latest relevant entries in [.ai/BRAIN.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/BRAIN.md).
4. **Read Architectural Decisions**: Read [.ai/DECISIONS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/DECISIONS.md).
5. **Inspect Repository Files**: Inspect `src/`, `docs/`, `tests/`, and assets to verify actual codebase state.
6. **Classify Session Mode**: Determine whether this session is `STARTING FROM ZERO` or `RESUMING EXISTING WORK`.
7. **Identify Active Phase**: Determine active gate from [HACKATHON_START.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/HACKATHON_START.md).
8. **Lock Immediate Next Action**: Identify exactly ONE high-priority, scoped task before taking action.

---

## 3. The Master Execution Loop

$$\begin{aligned}
\text{READ STATE} &\longrightarrow \text{INSPECT PROJECT} \longrightarrow \text{IDENTIFY PHASE} \longrightarrow \text{IDENTIFY NEXT ACTION} \\
&\longrightarrow \text{CHECK SCOPE} \longrightarrow \text{EXECUTE} \longrightarrow \text{VERIFY} \longrightarrow \text{DOCUMENT} \longrightarrow \text{UPDATE STATE} \longrightarrow \text{CONTINUE}
\end{aligned}$$

---

## 4. Master Operating Laws

### Law 1: State-First Operational Truth
- [.ai/STATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/STATE.md) is the active, non-historical operational snapshot.
- [.ai/BRAIN.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/BRAIN.md) is the immutable, append-only historical audit trail.
- [.ai/DECISIONS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/DECISIONS.md) is the structured architectural decision record.
- **Rule**: Never treat `BRAIN.md` as the active task list. Never treat `STATE.md` as historical.

### Law 2: No Repeated Work
- Before building any feature, verify whether it is already completed, tested, and documented.
- Missing conversational memory in the chat window does NOT mean work was not completed. **The filesystem is the source of truth.**
- If verified code exists in `src/`, **DO NOT REBUILD IT**.

### Law 3: No Blind Resets
- Never delete working code, reset project directories, or reinitialize architectures due to lost chat context.
- If context is lost, execute [CONTEXT_RECOVERY.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/CONTEXT_RECOVERY.md) to reconcile state cleanly.

### Law 4: The Anti-Drift Rule
At every major phase transition, the agent must internally verify:
> **"Does this task still directly solve the validated problem and bridge the documented gap?"**
If alignment is questionable, **HALT**, review `docs/01-problem/` and `docs/04-product/`, and re-align before continuing.

---

## 5. Long-Session & Timeline Management

When development falls behind the 24-hour hackathon schedule:
- **DO NOT** attempt to catch up by adding technical complexity or skipping tests.
- **DO Execute Graceful Scope Reduction**:
  1. Formally descope optional / stretch features.
  2. Simplify architecture to the minimal reliable baseline.
  3. Reduce UI styling complexity while keeping interaction clean.
  4. Protect the **core user journey** and **differentiating capability** at all costs.
  5. Never sacrifice empirical test verification.

---

## 6. User Interaction Boundary
- The AI agent manages internal state, task logs, test records, and documentation autonomously.
- Do not overwhelm the user with routine status updates or minor technical decisions.
- Prompt the user **ONLY** for:
  1. Initial problem statement and constraints.
  2. Resolving irreconcilable requirement conflicts.
  3. Explicit approval on major strategic pivots.
