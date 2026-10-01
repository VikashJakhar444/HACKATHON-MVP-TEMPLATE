# Tech Stack Selection & Decision Framework

## Core Principle: Technology Serves the Problem
Never choose a technology because it is fashionable, impressive, or familiar if a simpler, more reliable option satisfies the requirement. The tech stack must prioritize rapid implementation, transparent debugging, AI-agent compatibility, zero-dependency overhead, and bulletproof live demonstration during a 24-hour hackathon.

---

## 1. Default Hackathon Stack Preferences

For rapid MVP development, default to lightweight, self-contained, and easily debugged technologies:

- **Frontend**: Vanilla HTML5, Vanilla CSS3 (modern flex/grid, custom properties, glassmorphism), Vanilla JavaScript (ES6+).
- **Backend (when needed)**: Python (Flask or FastAPI) or Node.js (Express / HTTP native).
- **Desktop GUI (when appropriate)**: Python (Tkinter / CustomTkinter / PyQt).
- **Data Persistence**: SQLite, Local JSON storage, or In-Memory State.
- **Visualization**: Chart.js, Canvas API, or lightweight SVG rendering.

> **Note**: These are sensible defaults, NOT dogmatic mandates. The validated problem and technical requirements determine the final stack.

---

## 2. Technology Selection Evaluation Template

For every major technology choice (Language, Framework, Database, External Service), complete this decision block:

### Decision Component: [e.g., Application Backend / UI Runtime / Data Storage]

1. **Requirement**: What capability does the product genuinely require?
2. **Candidate Options**:
   - Option A: *[Candidate 1]*
   - Option B: *[Candidate 2]*
3. **Evaluation Matrix**:
   - *Implementation Speed*: How quickly can this be built from scratch?
   - *Reliability*: Does it behave deterministically without complex configuration?
   - *Complexity & Overhead*: How many configuration files or build steps are required?
   - *AI-Agent Compatibility*: Can AI coding assistants easily author, refactor, and verify this code?
   - *Debuggability*: Are error stack traces clear and actionable?
   - *Local / Offline Capability*: Can the demo run without active internet connectivity?
   - *Demo Reliability*: Is there zero chance of cold-start delays or build failures?
4. **Selected Decision**: *[Chosen technology]*
5. **Concrete Rationale**: Why this is the simplest reliable choice.
6. **Acknowledged Trade-offs**: What capability or optimization is intentionally deferred.
7. **Fallback Plan**: What simpler tool will be substituted immediately if this choice encounters blockers.

---

## 3. The 6-Question Stack Decision Rule

Before approving any library, framework, service, or database, answer these six questions:

1. **Why is it needed?** (Direct link to a required functional feature)
2. **Why this specific technology?** (Direct advantage over simpler built-in tools)
3. **What simpler alternative was considered?** (Why was the minimal choice insufficient?)
4. **What is the implementation and debugging cost?** (Hours required to integrate and test)
5. **What happens if it fails during the hackathon?** (Fallback mitigation path)
6. **Can the team/AI agent debug it in 15 minutes under pressure?** (Inspectability)

If these six questions cannot be answered convincingly, **reject the technology** and select the simpler alternative.

---

## 4. What NOT to Add Automatically

Do NOT select the following tools unless the explicit problem requirements leave no reasonable alternative:
- ❌ Microservices or multi-process service meshes (use a modular monolith).
- ❌ React / Next.js / Angular / Vue for basic interactive pages where Vanilla JS + HTML suffices.
- ❌ Docker / Kubernetes containerization for simple local scripts or single-server web apps.
- ❌ Remote Cloud Databases (PostgreSQL / MongoDB Atlas / DynamoDB) when local SQLite or JSON suffices.
- ❌ Heavy ORM suites (Prisma, SQLAlchemy full migrations) when lightweight query helpers suffice.
- ❌ Cloud-only AI services without local mocking or fallback caching.

---

## 5. Failure-First Planning
For every technically risky component (external API, complex algorithm, hardware interface):
- **Failure Mode**: What can break? (e.g., API timeout, invalid format, rate limiting).
- **Detection**: How does the application detect the failure immediately?
- **Fallback**: What pre-computed dataset, cached response, or deterministic heuristic takes over?
- **Scope-Reduction Option**: Can this feature be gracefully downgraded to a supporting mode without breaking the primary demo journey?
