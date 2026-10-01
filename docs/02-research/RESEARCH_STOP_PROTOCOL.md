# Research Stop & Time-Box Protocol

## Purpose
This document defines the hard stopping rules and decision gates for external research. It prevents open-ended research loops, analysis paralysis, and excessive documentation that drains the 24-hour hackathon build budget.

---

## 1. Pre-Research Definition Mandate

Before conducting ANY research query, the AI agent must define:

1. **The Exact Question**: What specific fact, API capability, or constraint is unknown?
2. **The Active Decision It Informs**: Which architectural choice, library selection, or product feature hinges on this answer?
3. **The Expected Use**: How will the answer be directly applied in the codebase?

> **Rule**: If a research inquiry cannot be directly linked to an active ADR or PRD feature, **DO NOT SEARCH**.

---

## 2. Hard Stopping Criteria

The AI agent **MUST HALT** research immediately when ANY of the following four conditions is met:

1. **Decision Sufficiency**: Enough evidence exists to make a reasonably confident engineering or product choice.
2. **Diminishing Returns**: Consulting additional articles or repositories will not alter the chosen direction.
3. **Time Budget Depletion**: The allocated time box (15–30 minutes per topic, max 60–90 minutes total) has expired.
4. **Actionability Limit**: Additional research will not change the actual implementation code to be written.

$$\text{DEFINE QUESTION} \longrightarrow \text{TARGETED INQUIRY} \longrightarrow \text{MAKE DECISION} \longrightarrow \text{STOP RESEARCH} \longrightarrow \text{START BUILDING}$$

---

## 3. The Research Hard Stop Rule

The AI agent must **NEVER** continue researching simply because:
- ❌ More documentation or articles exist on the topic.
- ❌ The topic is intellectually fascinating or novel.
- ❌ The agent seeks 100% academic certainty on a low-risk implementation detail.
- ❌ Competitor analysis or background reading "feels incomplete".
- ❌ The agent wants to expand documentation volume for presentation aesthetics.

> **Core Axiom**: The sole purpose of research in a hackathon is to **make the immediate architectural or product decision**. Once the decision is made, research is complete. Log the finding in `docs/02-research/RESEARCH_LOG.md` and proceed immediately to implementation.
