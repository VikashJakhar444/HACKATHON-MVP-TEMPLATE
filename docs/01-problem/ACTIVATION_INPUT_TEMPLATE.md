# Hackathon Activation Input

> **Instructions**: When starting a new hackathon, paste the raw problem statement and optional parameters below to activate the autonomous engineering workflow.

---

## 1. Required Input

### Problem Statement:
```text
[PASTE RAW HACKATHON PROBLEM STATEMENT HERE]
```

---

## 2. Optional Metadata & Constraints

- **Hackathon Name**: *[e.g., Global AI Hackathon 2026]*
- **Time Limit**: *[e.g., 24 Hours / 36 Hours / 48 Hours]* *(Default: ~24 Hours)*
- **Team Size & Composition**: *[e.g., Solo / 3 Developers]*
- **Judging Criteria & Rubric**: *[e.g., Innovation (30%), Technical Execution (30%), Demo/Pitch (20%), Impact (20%)]*
- **Mandatory Technologies / Stacks**: *[e.g., Python / None]*
- **Mandatory Features / Sponsor Requirements**: *[e.g., Must integrate Sponsor API / None]*
- **Available Datasets / Seed Files**: *[e.g., Path to local dataset / None]*
- **Available APIs & Credentials**: *[e.g., OpenAI API Key, Stripe Test Keys / None]*
- **Deployment Requirement**: *[e.g., Localhost presentation / Public Vercel URL]*
- **Other Constraints**: *[e.g., Offline capability, zero GPU requirement]*

---

## 3. AI Agent Operating Instructions
Upon ingestion of this activation input, the AI agent MUST:
1. Initialize the audit log in `.ai/BRAIN.md` with the verbatim problem statement and parameters.
2. Update `.ai/STATE.md` to indicate Phase 1 (Problem Understanding) is active.
3. Decompose the problem in `docs/01-problem/PROBLEM_ANALYSIS_TEMPLATE.md` using `PROBLEM_ANALYSIS_GUIDE.md`.
4. Strictly follow the 9 Phase Gates and the 21-step workflow defined in `HACKATHON_START.md`.
5. Never invent missing constraints or skip directly to code generation.
