# Presentation & PPT Execution Protocol

## Purpose
This document governs the creation, content verification, and delivery of hackathon pitch decks. It guarantees that presentation materials strictly reflect working software capabilities and present a compelling, evidence-backed narrative to judges.

---

## 1. Operational Presentation Workflow

### Default AI Deliverables:
Unless explicitly commanded to generate a binary presentation file, the AI agent produces the complete presentation assets in Markdown:
1. **Pitch Narrative Architecture** (`docs/09-demo/PRESENTATION_PLAN_TEMPLATE.md`)
2. **Slide-by-Slide Content & Visual Specs** (`docs/09-demo/PPT_CONTENT_TEMPLATE.md`)
3. **Timed Speaker Script & Demo Cue Points**
4. **Empirical Claim-to-Evidence Matrix**

The human developer can then paste the structured content into PowerPoint, Google Slides, Keynote, or Canva in minutes.

---

## 2. The "After-Working-Code" Presentation Rule

> **MANDATORY RULE**: Final presentation slide content MUST be drafted **AFTER** the core MVP is functional and verified (post-Checkpoint 4/5). Never design a presentation around speculative features that were never implemented.

The AI must maintain clear, unambiguous boundaries:
- **`IMPLEMENTED`**: Operational in `src/` and verified with test logs.
- **`PLANNED`**: Actively being finalized before demo lock.
- **`FUTURE / ROADMAP`**: Post-hackathon horizons, explicitly labeled as future vision.

---

## 3. Claim-to-Evidence Verification Audit

Every quantitative, competitive, or capability claim on a slide must pass this verification test:

$$\text{SLIDE CLAIM} \longrightarrow \text{EVIDENCE / BENCHMARK SOURCE} \longrightarrow \text{WORKING CODE IMPLEMENTATION STATUS}$$

### Strict Presentation Constraints:
- ❌ **NO INVENTED METRICS**: Never invent fake market sizes (e.g., "$50B TAM"), fabricated survey statistics ("95% of users want this"), or unsupported speed/accuracy claims.
- ❌ **NO FAKE BENCHMARKS**: Do not claim superiority over competitors without documented tests in `docs/02-research/GAP_ANALYSIS_TEMPLATE.md`.
- ❌ **NO MOCKED RESULTS AS REAL**: If demo data is used, transparently state that it is a verified seed scenario.

---

## 4. The Demo-First Pitch Narrative

Structure the presentation so that the live demonstration serves as the central empirical proof of the concept:

$$\begin{aligned}
\text{Problem (Hook)} &\longrightarrow \text{The Unaddressed Gap} \longrightarrow \text{Our Solution Concept} \longrightarrow \text{How It Works} \\
&\longrightarrow \mathbf{LIVE\ WORKING\ DEMO} \longrightarrow \text{Core Differentiator} \longrightarrow \text{Real-World Impact} \\
&\longrightarrow \text{Honest Limitations} \longrightarrow \text{Future Roadmap \& Conclusion}
\end{aligned}$$

---

## 5. Time-Constrained Delivery Rules

- **3-Minute Pitch (Standard Hackathon)**:
  - Slide Count: 8–10 slides.
  - Time Budget: 45s Problem/Gap $\rightarrow$ 90s Live Demo & Differentiator $\rightarrow$ 45s Impact & Closing.
- **5-Minute Pitch**:
  - Slide Count: 12–13 slides (Full Deck).
  - Time Budget: 60s Problem/Gap $\rightarrow$ 120s Deep Live Demo $\rightarrow$ 60s Architecture & Security $\rightarrow$ 60s Impact, Roadmap & Closing.
