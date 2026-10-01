# Research Protocol

## Purpose
This document establishes the controlled, disciplined protocol for conducting external research during a 24-hour hackathon build. It ensures that research is strictly time-boxed, purposeful, evidence-based, and directly linked to architectural or product decisions.

---

## When Research is REQUIRED vs. NOT REQUIRED

### Research IS REQUIRED When:
- **Existing Solutions**: Understanding current state-of-the-art or competitor capabilities materially affects product positioning or architecture.
- **Unknown Constraints**: The problem domain contains unfamiliar regulatory, legal, or industry-specific constraints.
- **Technical Feasibility**: An API, algorithm, SDK, or framework compatibility is uncertain for the target feature.
- **Claim Verification**: A core assumption regarding user behavior, market data, or domain mechanics must be validated.
- **Gap Identification**: Available information is insufficient to substantiate an unmet user need.

### Research IS NOT REQUIRED When:
- The domain and technical implementation patterns are already well-understood and verified.
- The outcome of the research would not alter product design, technology stack, or architecture.
- It is initiated out of casual curiosity or speculative edge-case exploration.
- It consumes valuable hackathon time without directly resolving an active blocker or decision.

---

## Source Hierarchy & Priority

When conducting research, prioritize information sources in this order:

1. **Tier 1: Official / Primary Sources**
   - Official API documentation, SDK specifications, source repositories, official regulatory standards.
2. **Tier 2: Reliable Technical & Domain Sources**
   - Peer-reviewed engineering publications, official cloud architecture guides, reputable industry benchmarks.
3. **Tier 3: Credible Secondary Sources**
   - Industry reports, established tech publications, verified case studies.
4. **Tier 4: Community & Practitioner Sources**
   - Stack Overflow discussions, GitHub issue threads, community forums (primarily for practical troubleshooting and real-world edge cases).

---

## Research Entry Schema
For every distinct research task, log the findings in `docs/02-research/RESEARCH_LOG.md` using this standard schema:

- **Question**: Specific question being investigated.
- **Why It Matters**: How this affects the project direction or architecture.
- **Source**: Exact URL, document, or reference consulted.
- **Key Finding**: Concise summary of what was learned.
- **Confidence**: Level of confidence (`HIGH` | `MEDIUM` | `LOW`).
- **Decision Affected**: Specific ADR or product feature influenced.
- **Follow-Up**: Whether additional investigation is strictly necessary.

---

## 24-Hour Time-Boxing & Discipline
- **Strict Time Limits**: Allocate a maximum of 15–30 minutes per research topic. Total initial research across the project should rarely exceed 60–90 minutes.
- **Never Open-Ended**: Define the exact question and decision criteria *before* beginning search/reading.
- **Stopping Rule**: As soon as sufficient evidence exists to make a confident architectural or product choice:
  $$\text{STOP RESEARCH} \longrightarrow \text{LOG FINDINGS} \longrightarrow \text{APPLY TO DECISION} \longrightarrow \text{PROCEED TO IMPLEMENTATION}$$
