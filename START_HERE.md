# START_HERE.md — Master Hackathon Quickstart Guide

## 1. Welcome to the Hackathon MVP Template

> **IMPORTANT**: This repository is **NOT** a pre-built application or a collection of starter code. It is an **autonomous, AI-assisted engineering and governance system** designed to take any hackathon problem statement and rapidly build a genuinely working, verified, demonstrable MVP within approximately 24 hours.

---

## 2. The 11-Step Hackathon Workflow

When you arrive at the hackathon or receive your problem statement, follow these simple steps:

```text
[1. Create Folder] ──► [2. Open in AI Agent] ──► [3. Open Prompt] ──► [4. Paste Problem] ──► [5. Add Constraints]
                                                                                                    │
[10. Make PPT] ◄── [9. Run & Demo MVP] ◄── [8. Review Strategic Decisions] ◄── [7. AI Builds & Verifies] ◄── [6. ACTIVATE]
      │
      ▼
[11. Final Audit: READY]
```

### Step 1: Initialize Your Workspace
Clone or copy this clean template directory into your working project repository.

### Step 2: Open in Your AI Coding Environment
Open this project folder in your preferred AI coding environment (such as **Google Antigravity**, **OpenCode**, or any `AGENTS.md`-compatible agent).

### Step 3: Open the Activation Prompt
Open [HACKATHON_PROMPT.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/HACKATHON_PROMPT.md) in your editor.

### Step 4: Paste Your Problem Statement
Paste the raw hackathon problem statement into the designated field in [HACKATHON_PROMPT.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/HACKATHON_PROMPT.md) or [docs/01-problem/ACTIVATION_INPUT_TEMPLATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/docs/01-problem/ACTIVATION_INPUT_TEMPLATE.md).

### Step 5: Add Known Constraints (Optional)
Fill in any known parameters (time limit, mandatory sponsor APIs, judging criteria, team size, etc.). If unknown, leave blank—the AI will not hallucinate missing information.

### Step 6: Send Activation Prompt to the AI Agent
Copy the completed prompt from [HACKATHON_PROMPT.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/HACKATHON_PROMPT.md) and send it as your first message to the AI agent.

### Step 7: Autonomous Engineering Execution
The AI agent will autonomously:
1. Decompose and understand the problem (`docs/01-problem/`).
2. Perform targeted, time-boxed research and gap analysis (`docs/02-research/`).
3. Select a focused, coherent 4–5 core feature MVP (`docs/03-requirements/` & `docs/04-product/`).
4. Architect a simple, reliable stack and implementation plan (`docs/05-technical/` to `docs/07-implementation/`).
5. Incrementally build the working code in `src/`.
6. Run tests, verify empirical outputs, and record results (`docs/08-testing/`).
7. Prepare live demo scripts and presentation slide content (`docs/09-demo/`).

### Step 8: Strategic Human Review
The AI will prompt you **ONLY** if a critical decision requires human judgment (e.g., resolving a major requirement contradiction or choosing between two distinct product directions). All routine implementation is handled automatically.

### Step 9: Launch & Test Your MVP
Execute the single-command startup documented in [docs/09-demo/FINAL_HANDOFF.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/docs/09-demo/FINAL_HANDOFF.md) and verify the live happy path.

### Step 10: Build Your Pitch Deck
Use the structured narrative from [docs/09-demo/PRESENTATION_PLAN_TEMPLATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/docs/09-demo/PRESENTATION_PLAN_TEMPLATE.md) and the slide content from [docs/09-demo/PPT_CONTENT_TEMPLATE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/docs/09-demo/PPT_CONTENT_TEMPLATE.md) to generate your slides in PowerPoint, Google Slides, or Canva.

### Step 11: Execute Final Audit
Review [docs/09-demo/FINAL_AUDIT_CHECKLIST.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/docs/09-demo/FINAL_AUDIT_CHECKLIST.md) to verify that your project is **`READY`** for live judging.

---

## 3. Core Operating Philosophy
- **Working Code > Feature Quantity**: We build 4–5 rock-solid, verified features rather than 20 broken ones.
- **Evidence-Based Uniqueness**: Differentiation comes from solving real unmet workflow needs, not from buzzwords.
- **Traceability**: Every action, decision, and test result is permanently audited in [.ai/BRAIN.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/.ai/BRAIN.md).
