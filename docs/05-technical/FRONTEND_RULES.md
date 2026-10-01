# Frontend Engineering Standards

## Purpose
This document establishes framework-agnostic frontend engineering standards for hackathon MVP development. It ensures the client interface is clean, robust, accessible, highly responsive, and strictly connected to real capabilities without forcing any particular UI framework.

---

## 1. Frontend Architecture & Simplicity

- **Default Preference**: Prefer the simplest frontend architecture that reliably satisfies requirements.
  - **Vanilla HTML5 + Modern CSS + Vanilla ES6+ JavaScript** is the primary default when client-side state is straightforward.
  - **Component Frameworks** (e.g., React, Vue, Svelte) are permitted **ONLY** when complex interactive state, reactive UI graphs, or rich client-side data workflows genuinely justify them.
- **No Automatic Boilerplate**: Do not introduce heavy frontend scaffolding or multi-megabyte bundle tooling merely out of habit.
- **Minimal Abstraction**: Avoid excessive layers of wrapper components, custom hooks, or complex state stores when simple DOM manipulation or lightweight reactive state suffices.

---

## 2. UI Structure & Lifecycle States

Every page, view, and interactive component must account for the standard UI lifecycle:

```text
[Initial / Landing View] ──► [Input / Action Trigger] ──► [Processing / Loading State]
                                                                   │
                                 ┌─────────────────────────────────┴─────────────────────────────────┐
                                 ▼                                                                   ▼
                      [Success / Result View]                                             [Graceful Error State]
                                 │                                                                   │
                                 └────────────────────────► [Recovery Path] ◄────────────────────────┘
```

### Mandatory UI State Handlers:
1. **Initial / Empty State**: Clear welcoming context, concise user instructions, and an optional one-click "Load Demo Scenario" action.
2. **Loading / Processing State**: Subtle spinners, progress indicators, or skeleton placeholders indicating active work without freezing the UI.
3. **Success State**: Clear, structured display of computation results, status confirmations, and export/next-step actions.
4. **Error State**: Non-destructive, human-readable alert badges explaining the failure with an immediate recovery action.
5. **Disabled State**: Visual indication for buttons and controls during active asynchronous processing to prevent duplicate submissions.

---

## 3. Interaction & Feedback Standards

Every interactive element must obey the **Predictable Interaction Contract**:
- **Clear User Intent**: Buttons, inputs, and controls must have unambiguous labels and visual affordances.
- **Immediate Feedback**: Hover states, active focus indicators, and visual response within $<100\text{ms}$ of user interaction.
- **Explicit Recovery Path**: If an operation fails, the user must never be trapped in a broken state. Input fields must retain values and provide a clear "Retry" or "Reset" mechanism.

---

## 4. Frontend Data Handling & Safety

- **Client-Side Validation**: Validate input formats (non-empty, string lengths, numerical bounds) before submitting to the backend or core logic.
- **Safe DOM Rendering**: Always sanitize text inputs and escape HTML entities before insertion into the DOM to prevent Cross-Site Scripting (XSS).
- **No Mock Data in Live Flows**: Never present fabricated hardcoded mock responses in production paths unless explicitly labeled as `DEMO FIXTURE`.
- **Asynchronous Safety**: Handle network timeouts and unexpected payloads gracefully; never assume an API call will succeed.

---

## 5. Performance & Asset Discipline

- **Minimal Dependency Overhead**: Use built-in browser APIs (e.g., `fetch()`, `Canvas API`, `Intl`, `URLSearchParams`) rather than pulling in external utility packages (e.g., Axios, Lodash, Moment.js).
- **Lightweight Assets**: Optimize static images, use modern vector icons (SVGs), and avoid heavy web fonts or bloated styling frameworks unless required.
- **No Unnecessary Polling**: Use event-driven updates or lightweight intervals only when live tracking is genuinely needed.

---

## 6. UI Quality & Anti-Patterns

### Strictly Prohibited Frontend Anti-Patterns:
- ❌ **Placeholder UI / Dead Controls**: Buttons, tabs, or links that do nothing when clicked.
- ❌ **Fake Animations**: Random spinning elements, gratuitous particle effects, or sluggish CSS transitions that delay user workflow.
- ❌ **Unexplained Icons**: Standalone iconography without tooltips, aria-labels, or visible text descriptors.
- ❌ **Excessive Gradients / Visual Noise**: Overly busy backgrounds that degrade text contrast and cognitive ergonomics.
- ❌ **Feature Disconnect**: Any visual affordance that does not correspond to a working, verified system capability.
