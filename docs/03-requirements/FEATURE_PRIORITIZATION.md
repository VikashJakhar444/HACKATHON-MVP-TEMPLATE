# Feature Prioritization & Selection Framework

## Purpose
This document establishes the structured methodology for prioritizing, selecting, and constraining features for a 24-hour hackathon MVP. It ensures that the resulting product is tightly scoped, cohesive, feasible, and directly aligned with the validated problem and gap.

---

## 1. Feature Evaluation Dimensions

Every proposed feature candidate must be evaluated across eight critical dimensions:

1. **Problem Relevance**: Does this feature directly alleviate the primary user pain point?
2. **User Value**: Does the user gain immediate, tangible utility from this feature?
3. **Gap Alignment**: Does this feature address the specific limitation of existing tools?
4. **Demonstrability**: Can this feature's impact and operation be clearly showcased in a 3-minute live presentation?
5. **Implementation Feasibility**: Can this feature be reliably built and tested within the 24-hour window?
6. **Technical Risk**: Does this introduce complex unverified APIs, brittle algorithms, or excessive dependencies?
7. **Time Cost**: What is the estimated development and debugging time budget?
8. **Differentiation Value**: Does this feature distinguish the solution from generic alternatives?

---

## 2. Feature Classification Categories

Do NOT rely on an arbitrary composite score as the sole decision mechanism. Instead, classify candidate features into four explicit operational tiers:

- **`CORE`**: Absolute non-negotiables required to solve the core problem and complete the primary demo loop. Must be feasible, high-value, and verified.
- **`SUPPORTING`**: Essential infrastructure or secondary flows (e.g., input parsing, structured validation) that enable CORE features to operate smoothly.
- **`OPTIONAL`**: Secondary enhancements, extra export formats, or convenience features built only if CORE is finished and verified early.
- **`OUT OF SCOPE`**: Distractions, heavy boilerplate, unverified tech stacks, or features with disproportionate time/risk profiles.

> **Target Scope**: **4–5 meaningful, genuinely working CORE features** that form one coherent end-to-end user journey. If the problem genuinely requires fewer, do not add filler.

---

## 3. The 12-Step Feature Selection Workflow

When a real problem statement is provided, execute this sequence:

$$\begin{aligned}
\text{Problem Analysis} &\longrightarrow \text{Gap Analysis} \longrightarrow \text{Solution Concept} \longrightarrow \text{Generate Candidates} \\
&\longrightarrow \text{Map to Gap} \longrightarrow \text{Evaluate Feasibility} \longrightarrow \text{Prune Generic Filler} \longrightarrow \text{Select 4–5 Core} \\
&\longrightarrow \text{Identify WOW/Differentiator} \longrightarrow \text{Define Scope Boundary} \longrightarrow \text{Write PRD} \longrightarrow \text{Technical Architecture}
\end{aligned}$$

1. **Read Problem Analysis**: Review validated pain points and root causes.
2. **Read Gap Analysis**: Confirm specific competitor and tooling limitations.
3. **Define Solution Concept**: Establish the overarching value hypothesis.
4. **Generate Candidate Capabilities**: Brainstorm direct functional interventions.
5. **Map Candidates to Problem/Gap**: Reject any candidate that lacks a direct link to an identified gap.
6. **Evaluate Feasibility**: Assess technical risk and time budget against the 24-hour limit.
7. **Prune Generic Filler**: Remove non-essential boilerplate and generic features.
8. **Select Smallest Coherent MVP**: Select 4–5 core capabilities that complete a full user loop.
9. **Identify WOW / Differentiating Capability**: Ensure one prominent feature clearly highlights the core advantage (when justified).
10. **Define MVP Boundary**: Formally document what is excluded in `MVP_SCOPE_TEMPLATE.md`.
11. **Draft PRD & Feature Specs**: Detail behavior, inputs, outputs, error states, and acceptance criteria.
12. **Proceed to Technical Architecture**: Move to `docs/05-technical/` and `docs/06-architecture/`.

---

## 4. The WOW Feature Rule

A "WOW Feature" is NOT an excuse for gratuitous complexity or buzzwords. It is a high-leverage capability that:
- Is immediately understandable to an observer in seconds.
- Produces visible, undeniable value on screen.
- Directly demonstrates the solution's core differentiation.
- Actually works end-to-end during a live demonstration.
- Fits comfortably within the 24-hour feasibility budget.

### Examples of Legitimate WOW Mechanisms:
- **Instant Workflow Compression**: Transforming a cumbersome 10-step manual process into a single automated, transparent action.
- **Actionable Real-Time Synthesis**: Delivering instant, structured decision support from raw unstructured data.
- **Visual Clarity**: Visualizing a complex, hard-to-understand system state intuitively.
- **Proactive Error/Anomaly Detection**: Automatically flagging edge-case risks that humans routinely miss.

> **Rule**: Never force a WOW feature if the problem does not justify one. Substance and reliability always outweigh gimmickry.

---

## 5. The "No Generic Feature" Rule

Do NOT automatically add the following generic patterns unless the problem statement explicitly mandates them as core functionality:
- ❌ User authentication & role management (use simple session context or direct user selection)
- ❌ Admin management panels & settings dashboards
- ❌ User profile management & avatar uploaders
- ❌ Generic conversational chatbots with no domain grounding
- ❌ Unnecessary blockchain, IoT, or web3 integrations
- ❌ Complex billing, subscription, or payment systems
- ❌ Non-essential notifications, dark-mode toggles, or cosmetic settings

---

## 6. Feature Coherence Rule

The selected features must form **ONE unified, logical product journey**.
- A judge or user must immediately understand the narrative:
  $$\text{PROBLEM} \longrightarrow \text{SOLUTION} \longrightarrow \text{CORE FEATURES} \longrightarrow \text{MEASURABLE OUTCOME}$$
- Avoid building multiple disconnected utility demos bundled under one navigation bar.

---

## 7. The 24-Hour Engineering Priority Order

When timeline constraints require trade-offs during implementation, resolve them strictly in this order:

1. **Core Working Functionality** (Primary computation, logic, or data transformation)
2. **Primary User Journey (Happy Path)** (Flawless end-to-end execution)
3. **Core Differentiating Capability** (Key competitive advantage)
4. **Reliable Data & Edge Validation** (No silent crashes or invalid data leaks)
5. **Clean & Professional UI/UX** (Intuitive layouts, clear labels, modern styling)
6. **Explicit Error Handling** (Graceful, understandable failure messages)
7. **Secondary / Supporting Features** (Supplemental workflows)
8. **Nice-to-Have Polish** (Cosmetic animations and stretch goals)
