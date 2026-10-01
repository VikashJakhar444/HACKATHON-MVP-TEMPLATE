# AGENTS.md — AI Agent Operating Instructions

## 1. Project Identity
This repository is a reusable **Hackathon MVP Template**. It is **not** a finished product or single-purpose application yet. Its purpose is to enable developers and AI agents to take any hackathon problem statement and rapidly engineer a professional, genuinely functional, reliable, and demonstrable MVP within approximately 24 hours.

---

## 2. Authoritative Source of Truth
The `.ai/` directory serves as the project's authoritative governance and state-management layer. Any AI agent operating within this repository **MUST** read and respect the governance files before taking meaningful project actions:
- [.ai/RULES.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/RULES.md) — Master operating principles, constraints, and engineering rules.
- [.ai/BRAIN.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/BRAIN.md) — Chronological, append-only project activity ledger and reasoning audit trail.
- [.ai/STATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/STATE.md) — Current active project state, tasks, blockers, and next action.
- [.ai/DECISIONS.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/DECISIONS.md) — Architectural, product, technical, and UX decision records (ADRs).

---

## 3. Instruction Authority Hierarchy
When conflicting instructions or context arise, agents must resolve them strictly in the following priority order:
1. **Explicit current user instruction** (Highest authority)
2. **`.ai/RULES.md`** (Master project rules)
3. **Current project requirements & documented decisions** (`docs/` & `.ai/DECISIONS.md`)
4. **`.ai/STATE.md`** (Active project state)
5. **Existing project implementation** (`src/`, `tests/`, `scripts/`)
6. **AI assumptions & defaults** (Lowest authority)

> **Rule**: An AI agent must never silently override a higher-level authority.

---

## 4. Project Memory & Governance System
- **`BRAIN.md`**: Permanent, immutable, append-only chronological ledger tracking all significant context, actions, decisions, results, and impacts.
- **`DECISIONS.md`**: Structured records of high-impact architectural, technical, product, and UX trade-offs.
- **`STATE.md`**: Active snapshot of the project lifecycle, completed milestones, current task, blockers, and immediate next steps.
- **`RULES.md`**: Permanent non-negotiable engineering principles governing all implementation work.

---

## 5. Required AI Behavior & Execution Cycle
Before undertaking any meaningful project task, follow this sequential cycle:
$$\text{READ} \longrightarrow \text{INSPECT} \longrightarrow \text{UNDERSTAND} \longrightarrow \text{DECIDE} \longrightarrow \text{DOCUMENT} \longrightarrow \text{IMPLEMENT} \longrightarrow \text{TEST} \longrightarrow \text{VERIFY} \longrightarrow \text{DOCUMENT RESULT} \longrightarrow \text{UPDATE STATE}$$

---

## 6. Brain Audit Trail Requirement
- Every significant decision, architectural transition, and meaningful implementation step must be logged in `.ai/BRAIN.md`.
- **Append-only rule**: Never delete, rewrite, remove failed attempts, or silently compress historical entries.
- Use actual local system timestamps for all entries.

---

## 7. Scope & Dependency Discipline
- Do not expand project scope beyond the problem statement, documented requirements, or explicit user requests.
- Do not introduce libraries, frameworks, third-party services, databases, or complex patterns without explicit necessity and documentation.
- Target a focused baseline of **4–5 core, high-value, genuinely working features**.

---

## 8. Research Discipline
- Conduct research only when findings directly affect an active architectural, technical, or product decision.
- Never perform research for idle curiosity.
- Always document relevant research outcomes concisely in `docs/02-research/` or `.ai/BRAIN.md`.

---

## 9. Working Software & Verification Pipeline
- Code is not done upon creation. A feature is only `COMPLETE` after passing:
  $$\text{IMPLEMENTED} \longrightarrow \text{EXECUTED} \longrightarrow \text{TESTED} \longrightarrow \text{VERIFIED} \longrightarrow \text{DOCUMENTED}$$
- Never present unexecuted or unverified code as working functionality.

---

## 10. Existing Code Preservation
- Always inspect existing files and modules before authoring new code.
- Reuse existing logic, utilities, and components wherever possible.
- Never refactor or remove working functionality without clear justification and documentation.

---

## 11. Hackathon Priorities
Optimize for:
- Genuine working functionality
- Clear real-world user value
- Minimal viable complexity
- Clean and professional UX/UI
- High reliability and graceful error handling
- Live demonstrability
- 24-hour feasibility

Do **NOT** optimize for:
- Superficial feature count
- Architecture over-engineering
- Unnecessary abstractions
- Dependency bloat

---

## 12. No Fake Functionality
- Static mocks, hardcoded data, fake AI outputs, fake metrics, or dummy buttons must never be represented as real capabilities.
- Any intentional mockup created solely for demonstration must be explicitly labeled as `MOCKED`.

---

## 13. Security & Credentials
- Never hardcode secrets, API keys, private tokens, or passwords.
- Use environment variables (`.env`) or local configuration templates.

---

## 14. User Alignment & Decision Escalation
- If a decision materially changes product direction, architecture, or scope, and cannot be determined from available requirements or rules, ask the user for clarification.
- For low-impact routine technical choices, select the simplest effective approach and document it.
