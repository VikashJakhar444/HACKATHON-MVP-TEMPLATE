# Problem Analysis Guide

## Purpose
This guide defines the disciplined 8-step reasoning process that an AI agent or engineering team must execute whenever a new hackathon problem statement is introduced. It prevents premature solutioning and ensures every feature is rooted in a validated user problem, verified gap, and practical hackathon constraint.

---

## The 8-Step Problem Analysis Workflow

$$\text{READ} \longrightarrow \text{EXTRACT} \longrightarrow \text{SEPARATE} \longrightarrow \text{UNDERSTAND} \longrightarrow \text{ROOT CAUSE} \longrightarrow \text{DEFINE} \longrightarrow \text{OPPORTUNITY} \longrightarrow \text{RESEARCH DECISION}$$

---

### Step 1 — READ: Comprehensive Ingestion
- Read the complete problem statement carefully from start to finish.
- Do not skim or jump immediately to technology choices.
- Preserve the original text verbatim in `PROBLEM_ANALYSIS_TEMPLATE.md`.

### Step 2 — EXTRACT: Explicit Requirement Identification
- Extract all explicit requirements, designated users, technical constraints, mandatory objectives, and expected deliverables.
- Highlight specific domain vocabulary, regulatory bounds, or platform expectations.

### Step 3 — SEPARATE: Epistemic Categorization
Categorize all extracted information into three distinct buckets:
1. **Facts**: Explicitly stated or empirically verified information.
2. **Assumptions**: Reasonable hypotheses or working assumptions that require validation.
3. **Unknowns / Missing Information**: Ambiguities or data gaps requiring clarification or research.

> **Rule**: Never present assumptions or inferences as verified facts.

### Step 4 — UNDERSTAND: Context & Workflow Mapping
Synthesize the operational reality:
- **User**: Who is hurting the most? Who has the problem daily?
- **Context**: Where and under what exact conditions does the problem manifest?
- **Pain Point**: What is the immediate friction, delay, cost, or error?
- **Current Workflow**: How is the job handled today without our solution?
- **Failure Point**: At what precise step does the existing workflow break down?

### Step 5 — ROOT CAUSE: Deep Causal Attribution
- Identify the underlying structural, technical, or procedural reasons why the failure point occurs.
- Avoid superficial symptoms (e.g., "users forget passwords" vs. "authentication requires 14 disconnected steps without persistent sessions").
- Do not claim absolute causal certainty if evidence is incomplete.

### Step 6 — DEFINE: Synthesized Testable Problem Statement
- Formulate a single, sharp, testable problem definition statement following the standard formula:
  $$\text{"[User X] struggles with [Pain Y] during [Context Z] due to [Root Cause W], resulting in [Negative Impact V]."}$$

### Step 7 — OPPORTUNITY: Value Vector Mapping
- Identify high-potential opportunity areas where a targeted solution creates measurable leverage.
- Focus on leverage points (e.g., automating manual handoffs, eliminating redundant steps, providing real-time validation).
- **Critical Discipline**: Do NOT convert opportunity areas into rigid feature lists or code architectures at this stage.

### Step 8 — DECIDE: Research Evaluation
Evaluate whether external research is required:
- *Is research needed to validate an uncertain technical approach, domain regulation, or competitor gap?*
- If **YES**: Proceed to `docs/02-research/RESEARCH_PROTOCOL.md` and time-box the investigation.
- If **NO**: Proceed directly to product requirements and MVP planning (`docs/03-requirements/` & `docs/04-product/`).

---

## Core Guiding Principles

### 1. Real-World Problem Principle
Before proposing any major feature, the AI must be able to answer:
1. **What real problem does this solve?**
2. **Who experiences that problem?**
3. **What is insufficient about the current approach?**
4. **What evidence supports the existence of this gap?**
5. **Why is this feature appropriate for a 24-hour MVP?**

If these five questions cannot be answered with clarity, the feature must NOT be added to the MVP scope.

### 2. Uniqueness Principle
Genuine product uniqueness does NOT come from buzzword technology:
- ❌ **NOT Uniqueness**: Adding gratuitous AI, blockchain, IoT, unnecessary real-time websockets, or complex dashboards for demo vanity.
- ✔️ **True Differentiation**:
  - A real, verified unmet need
  - A vastly streamlined workflow
  - Better accessibility and speed
  - Superior usability and clarity
  - Actionable decision support
  - High reliability and graceful error recovery
  - Context-specific ergonomics tailored to target users

### 3. The 24-Hour Constraint
- Problem analysis and research must be strictly proportional to the 24-hour timeframe.
- Achieve confident problem clarity rapidly (typically within 30–60 minutes of project kickoff).
- Do not spend half the hackathon researching or analyzing.
- Once sufficient clarity is reached:
  $$\text{STOP RESEARCH} \longrightarrow \text{DOCUMENT} \longrightarrow \text{MOVE TO PRODUCT DESIGN}$$
