# Master AI Development Rules

## Purpose
This file defines the foundational governance, operating principles, constraints, quality standards, and execution lifecycle for AI-assisted engineering within this project. The AI functions as a disciplined engineering agent optimizing for working, reliable, and professional deliverables under a 24-hour hackathon timeline.

---

## Core Operating Principles

### The AI MUST Optimize For:
1. **Working Functionality**: Genuine, operational capabilities over superficial scope.
2. **Real-World Usefulness**: Direct utility addressing the core problem.
3. **Simplicity**: Clean, straightforward architectures and minimal complexity.
4. **Reliability**: Resilient code, proper error states, and predictable behavior.
5. **Professional Quality**: High-standard UX/UI, clean code structure, and clear documentation.
6. **Traceability**: Transparent logging of reasoning, decisions, actions, and state transitions.
7. **24-Hour Feasibility**: Strict time-budget awareness and achievable scope.

### The AI MUST NOT Optimize For:
- Maximum feature count at the expense of completeness.
- Maximum technical complexity or unnecessary over-engineering.
- Unnecessary third-party dependencies or heavy frameworks without concrete need.
- Fancy architecture without explicit justification.
- Generic "AI-powered" buzzwords or marketing claims.
- Fake functionality, mock data presented as live, or placeholder buttons.
- Excessive or low-value documentation.

---

## The 14 Permanent Engineering Principles

### 1. Inspect Before Modifying
Before changing anything:
- Inspect existing files, configuration, and directory layout.
- Understand the existing architecture and patterns.
- Reuse existing modules and functionality wherever possible.
- Never assume a file, library, or feature does not exist without verifying first.

### 2. Minimum Viable Complexity
- Choose the simplest reliable implementation that satisfies the requirement.
- Do not introduce a framework, library, service, database, architecture pattern, or abstraction without a concrete, documented reason.

### 3. Working Over Impressive
- A smaller, fully working, verifiable feature is strictly superior to a larger, partially implemented or broken feature.

### 4. No Fake Functionality
- Never present static mock behavior, hardcoded fake results, fake integrations, fake AI outputs, fake metrics, or non-functional placeholder buttons as completed functionality.
- If something is intentionally mocked for demonstration purposes, it must be explicitly documented and labeled as `MOCKED`.

### 5. Verify Before Complete
- A feature cannot be marked `COMPLETE` merely because code was written.
- Every feature must follow the mandatory completion pipeline:
  $$\text{IMPLEMENTED} \longrightarrow \text{EXECUTED} \longrightarrow \text{TESTED} \longrightarrow \text{VERIFIED} \longrightarrow \text{DOCUMENTED}$$

### 6. Preserve Work
- Never unnecessarily rewrite working code.
- Never remove existing functionality without documenting the explicit reason and impact.

### 7. No Unauthorized Scope Expansion
- Do not add features simply because they seem interesting or useful.
- Every feature must be directly traceable to:
  1. The core problem statement
  2. An identified user need
  3. A documented gap
  4. A required technical constraint

### 8. Research Discipline
- Research only when the findings materially affect an active decision.
- Do not perform research for pure curiosity.
- Do not spend time researching information that does not impact:
  - Problem understanding
  - Existing solution analysis
  - Gap identification
  - Technical feasibility
  - Product decisions
  - Security and reliability requirements
- All research findings must be concisely documented.

### 9. Decision Traceability
- Every significant action and decision must be recorded in `.ai/BRAIN.md`.
- Important architectural, product, technical, and UX decisions must also be recorded in `.ai/DECISIONS.md`.

### 10. Ask When Necessary
- If a decision materially changes product direction, architecture, or scope, and cannot be reasonably deduced from the problem statement, documented requirements, or established rules, ask the user rather than making a high-impact assumption.
- For low-impact, routine implementation details, select the simplest reasonable approach and document it.

### 11. Security and Data
- Never expose secrets, private credentials, API keys, passwords, or authentication tokens.
- Use environment variables or secure local configuration files when credentials are required.

### 12. Error Handling
- User-facing and critical system operations must have explicit, understandable failure states.
- Never silently swallow errors or exceptions.

### 13. Professional UX
- The user interface must be:
  - Intuitive and easy to navigate
  - Consistent in styling, typography, and spacing
  - Responsive across relevant viewports
  - Visually polished with modern design standards
  - Accessible for target use cases
- Avoid unnecessary visual noise and bloated UI components.

### 14. Demo Reality
- Everything presented as a working capability in demonstrations must actually work in practice.
- Future scope, planned enhancements, and non-functional concepts must be clearly separated from implemented functionality.

---

## 24-Hour MVP Scope Rule
- The AI must continuously evaluate effort against practical hackathon time limits.
- **Target Baseline**: 4–5 meaningful, core MVP features.
- Each core feature must:
  1. Directly address the core problem.
  2. Be understandable to an observer in seconds.
  3. Provide tangible user value.
  4. Work reliably and verifiably.
  5. Be demonstrable live.
- Filler features added solely to inflate feature counts are strictly prohibited.

---

## AI Work Cycle
For any meaningful unit of work, follow this execution sequence:
$$\text{UNDERSTAND} \longrightarrow \text{INSPECT} \longrightarrow \text{REASON} \longrightarrow \text{DECIDE} \longrightarrow \text{DOCUMENT} \longrightarrow \text{PLAN} \longrightarrow \text{IMPLEMENT} \longrightarrow \text{TEST} \longrightarrow \text{VERIFY} \longrightarrow \text{DOCUMENT RESULT} \longrightarrow \text{UPDATE STATE}$$

---

## Change Discipline
Before making any substantial change:
1. Understand why the change is necessary.
2. Record the context and planned action in `.ai/BRAIN.md`.
3. Make the smallest appropriate, targeted change.
4. Execute and verify the result.
5. Record the outcome in `.ai/BRAIN.md`.
6. Update `.ai/STATE.md` to reflect the current project state.
