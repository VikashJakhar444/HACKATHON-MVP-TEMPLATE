# Hackathon MVP Template

> **A reusable, autonomous engineering & governance system for building professional, genuinely working, and demonstrable MVPs in ~24 hours with AI-assisted development.**

---

## Quickstart: How to Use in a Hackathon

1. Open **[START_HERE.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/START_HERE.md)** for human-facing instructions.
2. Fill out **[HACKATHON_PROMPT.md](file:///c:/Users/vikas/Desktop/HACKATHON-MVP-TEMPLATE/HACKATHON_PROMPT.md)** with your problem statement.
3. Paste the prompt into your AI coding assistant (**Antigravity**, **OpenCode**, or any `AGENTS.md`-compatible agent).
4. Let the AI autonomously execute the 9 Phase Gates from problem analysis to verified code and pitch deck generation.

---

## Directory Architecture

```
HACKATHON-MVP-TEMPLATE/
│
├── .ai/                                  # Project AI Governance & State Layer
│   ├── BRAIN.md                          # Append-only chronological activity & decision ledger
│   ├── DECISIONS.md                      # Architectural Decision Records (ADRs)
│   ├── RULES.md                          # 14 permanent engineering & scope rules
│   └── STATE.md                          # Active operational project state
│
├── docs/                                 # Structured Documentation & Process Pipeline
│   ├── 01-problem/                       # Problem analysis guide, template & activation input
│   ├── 02-research/                      # Research protocol, gap analysis & stopping rules
│   ├── 03-requirements/                  # MVP scope, feature prioritization & specs
│   ├── 04-product/                       # Solution concept, PRD & user flows
│   ├── 05-technical/                     # TRD & tech stack selection framework
│   ├── 06-architecture/                  # Architecture, data model & API specifications
│   ├── 07-implementation/                # Build order, execution protocol & checkpoint gates
│   ├── 08-testing/                       # Test strategy, test cases, verification & bug log
│   └── 09-demo/                          # Demo checklist, PPT plan, slide specs & final audit
│
├── src/                                  # Clean application source code (to be built)
├── tests/                                # Test suites and automated verification scripts
├── scripts/                              # Utility and startup scripts
├── assets/                               # Media, diagrams, and static assets
├── data/                                 # Local data fixtures and seed files
│
├── AGENTS.md                             # AI instruction bridge & operating authority
├── MASTER_AGENT.md                       # Master operational controller & anti-drift laws
├── HACKATHON_START.md                    # Master activation guide & 9 Phase Gates
├── START_HERE.md                         # Human-facing 11-step quickstart guide
├── HACKATHON_PROMPT.md                   # Primary copy-paste activation prompt
├── SESSION_START.md                      # 7-step session startup procedure
├── CONTEXT_RECOVERY.md                   # Zero-history context loss recovery protocol
├── PROJECT_INIT_PROTOCOL.md              # Clean project initialization rules
├── TEMPLATE_USAGE.md                     # Template usage model & capabilities
├── TEMPLATE_READINESS_AUDIT.md           # Master template verification sign-off (READY)
└── README.md                             # Master repository index
```

---

## The 9 Phase Gates

| Gate | Phase Name | Deliverables & Exit Criteria |
| :--- | :--- | :--- |
| **GATE 1** | **Problem Lock** | Problem decomposed, target user & pain isolated (`docs/01-problem/`). |
| **GATE 2** | **Gap Lock** | Competitor limitations & unmet need substantiated (`docs/02-research/`). |
| **GATE 3** | **MVP Lock** | 4–5 core features selected, out-of-scope locked (`docs/03-requirements/` & `04-product/`). |
| **GATE 4** | **Tech Lock** | PRD, TRD, Architecture, and Data Models finalized (`docs/05-technical/` & `06-architecture/`). |
| **GATE 5** | **Build Gate** | Incremental coding executed in accordance with `BUILD_ORDER.md` (`src/`). |
| **GATE 6** | **Verify Gate** | Core logic & flows verified with empirical evidence (`docs/08-testing/`). |
| **GATE 7** | **Demo Lock** | Primary happy-path runs live without manual interventions (`docs/09-demo/`). |
| **GATE 8** | **Presentation** | Pitch deck narrative & slide specs finalized (`docs/09-demo/`). |
| **GATE 9** | **Final Audit** | Binary project audit yields **`READY`** verdict (`docs/09-demo/FINAL_AUDIT_CHECKLIST.md`). |

---

## Core Principles

- **Working Software Over Feature Bloat**: Target 4–5 core, high-value, genuinely working features.
- **Verification Before Completion**: $\text{IMPLEMENTED} \rightarrow \text{TESTED} \rightarrow \text{VERIFIED} \rightarrow \text{COMPLETED}$.
- **No Fake Functionality**: Zero fabricated metrics, mock data presented as live, or non-functional placeholder buttons.
- **24-Hour Feasibility**: Lightweight, self-contained runtimes (Python / Vanilla Web / SQLite) prioritized for reliable local demonstrations.
