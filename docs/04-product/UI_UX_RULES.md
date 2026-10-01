# Product UI/UX Design Standards

## Purpose
This document establishes product design, visual ergonomics, information hierarchy, and user experience standards for hackathon MVPs. It ensures the resulting application is immediately intuitive, professional, accessible, and optimized for high-impact live demonstration.

---

## 1. The Core UX Triad

Every interface built from this template must adhere to three foundational axioms:

$$\mathbf{EASY\ TO\ UNDERSTAND} \quad\longleftrightarrow\quad \mathbf{EASY\ TO\ OPERATE} \quad\longleftrightarrow\quad \mathbf{EASY\ TO\ DEMONSTRATE}$$

1. **Easy to Understand**: A first-time viewer or hackathon judge must grasp what the product does within 5 seconds of looking at the screen.
2. **Easy to Operate**: Core user actions require minimal cognitive load, zero ambiguous steps, and clear visual affordances.
3. **Easy to Demonstrate**: The primary value loop can be showcased live in under 90 seconds without navigating confusing sub-menus.

---

## 2. Information Hierarchy & Screen Anatomy

Every view or screen must strictly organize visual elements into four priority tiers:

```text
┌─────────────────────────────────────────────────────────────┐
│ 1. PRIMARY CONTEXT & TITLE (What is this screen for?)        │
├─────────────────────────────────────────────────────────────┤
│ 2. PRIMARY ACTION AREA (The single main thing to do next)    │
│    [Input Field / Upload Zone / Core Interaction Trigger]   │
├─────────────────────────────────────────────────────────────┤
│ 3. RELEVANT DATA & RESULTS (Output, visualizations, stats)   │
├─────────────────────────────────────────────────────────────┤
│ 4. SECONDARY ACTIONS (Export, Settings, Reset, Help)        │
└─────────────────────────────────────────────────────────────┘
```

> **Rule**: Avoid visual clutter. If a piece of information or secondary button does not serve the core MVP journey, remove it.

---

## 3. Streamlined User Flow Architecture

$$\text{ENTRY / CONTEXT} \longrightarrow \text{PRIMARY INPUT} \longrightarrow \text{INSTANT PROCESSING} \longrightarrow \text{ACTIONABLE OUTCOME}$$

- **Short & Focused**: The primary happy path should require no more than 2–3 clicks/inputs from start to finish.
- **Predictable Transitions**: Keep screen changes smooth; avoid sudden layout shifts or unexpected modal overlays.
- **Graceful Error Recovery**: If input is invalid, highlight the specific field with clear remediation advice; never reset valid fields.

---

## 4. Visual Design System & Consistency

Maintain a clean, cohesive visual language across all components:

- **Typography Hierarchy**: Use standard, highly legible system font stacks (e.g., Inter, system-ui, Roboto) with maximum 3 font sizes: `Title (24-32px)`, `Section (18-20px)`, `Body/Inputs (14-16px)`.
- **Harmonious Color Palette**:
  - *Background*: Clean dark mode (`#0f172a`, `#1e293b`) or crisp light mode (`#ffffff`, `#f8fafc`).
  - *Surface Cards*: Distinct contrast with subtle borders (`1px solid rgba(255,255,255,0.1)`).
  - *Primary Accent*: 1 distinct brand color (e.g., Indigo/Cyan/Violet) reserved for primary call-to-action buttons and active states.
  - *Semantic Colors*: Green for success, Red for errors, Amber for warnings.
- **Consistent Spacing Tokens**: Enforce 8px grid spacing (`8px`, `16px`, `24px`, `32px`).
- **No Ad-Hoc Styling**: Do not style individual buttons or inputs with random one-off CSS rules. Use consistent component classes or variables.

---

## 5. Pragmatic Responsiveness & Target Devices

- **Judge Viewport First**: Optimize primarily for standard desktop presentation viewports (1920x1080 and 1366x768 widescreen laptop screens).
- **Graceful Tablet Adaptation**: Ensure containers use responsive CSS Flexbox / CSS Grid so that narrower laptop or tablet windows do not cause horizontal scrolling or clipping.
- **Scope Discipline**: Do not spend valuable hackathon hours fine-tuning complex mobile smartwatch or edge-case viewports unless mobile is the explicit problem requirement.

---

## 6. Accessibility Essentials

- **High Contrast**: Ensure text meets WCAG AA contrast ratio ($\ge 4.5:1$ for normal text).
- **Visible Focus Affordance**: Retain clear focus rings for keyboard navigation.
- **Semantic HTML**: Use native `<button>`, `<input>`, `<main>`, `<header>`, and `<form>` elements.
- **Descriptive Labels**: Every input field must have an explicit visible `<label>`.

---

## 7. Demo-Optimized UX (The "Judges Rule")

- **Prominent Primary Call-to-Action**: The main button that triggers the core differentiator must be the most visually prominent element on the screen.
- **One-Click Demo Helper**: Provide a visible "Load Sample Data" link/button next to input areas so the presenter can populate valid data instantly during live pitches without manual typing.
