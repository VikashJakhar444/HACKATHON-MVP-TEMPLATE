# TEMPLATE_USAGE.md — Template Architecture & Usage Model

## 1. What This Template Is
The **Hackathon MVP Template** is a complete, reusable, AI-assisted engineering and governance framework. It enables solo developers, small teams, and autonomous AI agents to transform an ambiguous hackathon problem statement into a verified, demonstrable, and high-impact working prototype within a 24-to-48-hour build window.

---

## 2. What This Template Is NOT
- ❌ **NOT a Finished Application**: It does not contain pre-written product features.
- ❌ **NOT a Locked Tech Stack**: It does not enforce React, Next.js, Django, or Docker prior to analyzing problem requirements.
- ❌ **NOT a Fixed UI Theme**: It does not enforce a rigid design layout before understanding the user context.
- ❌ **NOT a Generic Feature Dump**: It explicitly rejects boilerplate user authentication, admin panels, and disconnected chatbots unless mandated by the problem.

---

## 3. The End-to-End Operational Lifecycle

$$\begin{aligned}
\text{Problem Statement} &\longrightarrow \text{Problem Analysis} \longrightarrow \text{Targeted Gap Research} \longrightarrow \text{Solution Concept} \\
&\longrightarrow \text{4–5 Core Feature MVP} \longrightarrow \text{Technical Architecture} \longrightarrow \text{Incremental Build} \\
&\longrightarrow \text{Empirical Test Verification} \longrightarrow \text{Live Demo Rehearsal} \longrightarrow \text{Pitch Slide Specs} \longrightarrow \text{Final Ready Audit}
\end{aligned}$$

---

## 4. Supported Development Style
This framework is optimized for:
- **Disciplined AI-Assisted Engineering**: Pairing developers with advanced AI agents where AI acts as a disciplined engineer rather than an unconstrained code generator.
- **"Vibe Coding" with Quality Gates**: Fast, intuitive ideation governed by strict verification pipelines ($\text{IMPLEMENT} \rightarrow \text{RUN} \rightarrow \text{TEST} \rightarrow \text{VERIFY}$).
- **24-Hour Feasibility**: Rapid decision-making, minimal viable complexity, and ruthless scope triage under strict time limits.
- **Local & Monolithic Architectures**: Fast, self-contained runtimes (Python, Vanilla Web, SQLite, Local APIs) that eliminate deployment friction during live demos.

---

## 5. AI Coding Agent Compatibility
This template is stack-agnostic and environment-neutral. It is engineered to operate seamlessly with any modern AI coding agent that can:
1. Ingest workspace instructions (`AGENTS.md` / `MASTER_AGENT.md`).
2. Read, edit, and create files across the directory tree.
3. Execute shell commands (launching dev servers, running test suites, verifying terminal output).
4. Inspect runtime results and terminal output.

*Fully compatible with Google Antigravity, OpenCode, Claude Code, Cursor, Aider, and standard command-line AI workflows.*
