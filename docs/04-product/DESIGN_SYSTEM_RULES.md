# Visual Design System & UX Behavior Standards

## Purpose
This document establishes the framework-agnostic visual design system, interaction ergonomics, state behaviors, and design decision framework for hackathon MVPs. It ensures that AI-generated user interfaces are professional, modern, clean, consistent, accessible, easy to use, and easy to demonstrate without forcing any single visual aesthetic, color palette, or framework.

---

## 1. Core Design System Principle

Every hackathon project must establish a coherent visual system **BEFORE** substantial UI implementation.
- The design system must define: Visual Direction, Color Tokens, Typography, Spacing, Layout, Components, Interaction States, Notification Patterns, and Accessibility.
- **24-Hour MVP Scoping**: The design system must remain lightweight and focused (typically 1–2 CSS files or style modules). It exists to prevent visual chaos and UI drift, not to become a time-consuming project of its own.

---

## 2. Context-Driven Visual Direction

Before choosing colors, typography, or visual treatments, determine:
$$\text{DOMAIN} \;\times\; \text{TARGET USERS} \;\times\; \text{PRODUCT PURPOSE} \;\times\; \text{PRIMARY ACTION} \;\times\; \text{DEMO ENVIRONMENT}$$

Select an appropriate visual direction tailored to the problem:
- **Enterprise / Institutional**: Clean light or slate surfaces, neutral borders, structured data grids, authoritative typography.
- **Modern SaaS / B2B**: Polished dark or crisp light mode, high-contrast action CTAs, subtle card elevation, refined micro-spacing.
- **Developer / Technical Utility**: High-density layouts, clear data hierarchy, monospace code blocks, minimal decorative padding.
- **Editorial / Content**: High-readability typography, wide margins, soft neutral backgrounds, restrained accents.
- **Data-Centric / Analytical**: Optimized tabular alignment, compact metrics, high-contrast visualization charts, clear filter toolbars.
- **Minimal / Consumer**: Ample whitespace, large focal action buttons, progressive disclosure, zero visual clutter.

---

## 3. The "Anti-Cyberpunk" Default & Domain Authenticity

> **CRITICAL RULE**: Do NOT default to "cyberpunk" or sci-fi visual tropes merely because a project involves cybersecurity, AI, cryptography, or backend infrastructure.

### Strictly Avoid:
- ❌ Neon cyan / neon purple / hot magenta color overload
- ❌ Glowing neon borders, scanlines, holographic effects, and sci-fi HUD crosshairs
- ❌ Futuristic grid overlays, animated particle canvases, and decorative "matrix code rain"
- ❌ Universal black backgrounds with low-contrast dark gray text
- ❌ Monospace fonts applied to entire body paragraphs and buttons
- ❌ Excessive, unreadable glassmorphism with heavy backdrop blurs

### Professional Technical UI Prioritizes:
$$\mathbf{CLARITY} \;\longrightarrow\; \mathbf{TRUST} \;\longrightarrow\; \mathbf{INFORMATION\ HIERARCHY} \;\longrightarrow\; \mathbf{READABILITY} \;\longrightarrow\; \mathbf{PROFESSIONALISM}$$

---

## 4. Semantic Color System & Design Tokens

Never assign random, hardcoded hex values to individual components. Define semantic design tokens per project:

```text
==================================================
SEMANTIC DESIGN TOKEN ARCHITECTURE
==================================================
--bg-app:                Primary application canvas background
--bg-surface:            Default container/card background
--bg-surface-secondary:  Nested card, table header, or subtle sidebar background
--text-primary:          Highest emphasis headlines, body text, and active labels
--text-secondary:        Supporting descriptions, secondary metadata
--text-muted:            Placeholder text, inactive captions, disabled labels
--border-subtle:         Dividers, card outlines (1px solid neutral)
--border-focus:          High-contrast focus ring for keyboard navigation
--color-primary:         Single primary brand / call-to-action color
--color-primary-hover:   Interactive hover/active state of primary color
--color-secondary:       Optional secondary accent for highlights/badges
--color-success:         Affirmative outcomes, verified status, passing checks
--color-warning:         Action required, cautionary notices, non-fatal alerts
--color-error:           Critical failures, validation blocks, fatal errors
--color-info:            Informational context, system announcements
--color-disabled:        Inactive buttons, non-interactive controls
==================================================
```

### Color Restraint & Meaning:
- **1 Primary Brand Color**: Reserved strictly for primary action buttons, active navigation, and key interactive focal points.
- **1 Optional Secondary Accent**: For badges or category tags.
- **Functional Semantic Colors**: Green is ONLY for success; Red is ONLY for errors/danger; Amber is ONLY for warnings; Blue/Cyan is for informational cues. Never use red or amber merely for visual decoration.

---

## 5. Contrast & Accessibility Standards

- **WCAG AA Compliance**: All text-to-background combinations must meet a minimum contrast ratio of $\ge 4.5:1$ ($\ge 3:1$ for large text $\ge 18\text{pt}$).
- **Non-Color-Only Communication**: Critical status must **NEVER** rely on color alone. Always combine:
  $$\text{ICON} \;+\; \text{EXPLICIT TEXT LABEL} \;+\; \text{SEMANTIC COLOR}$$
  *(e.g., Red "✖ Error: File missing", Green "✔ Verified: Scan complete")*.

---

## 6. Typography Scale & Readability

Define a clean, legible typographic hierarchy with maximum 2 font families (1 primary sans-serif for UI, 1 monospace reserved strictly for code/logs/hashes):

| Typographic Role | Recommended Size / Weight | Usage Context |
| :--- | :--- | :--- |
| **`DISPLAY / TITLE`** | `24px – 32px` \| Bold / SemiBold | Main application header, landing title |
| **`H1 / SECTION`** | `18px – 20px` \| SemiBold | Section titles, card group headers |
| **`H2 / SUBSECTION`** | `15px – 16px` \| Medium | Modal headers, sub-panel titles |
| **`BODY`** | `14px – 15px` \| Regular | Primary paragraph text, form input values |
| **`BODY_SMALL / CAPTION`** | `12px – 13px` \| Regular / Medium | Table metadata, helper text, timestamps |
| **`TECHNICAL / MONO`** | `12px – 13px` \| Monospace | JSON payloads, API keys, terminal logs, code snippets |

> **Rule**: Monospace typography must never be used for general UI navigation, buttons, or explanatory body text.

---

## 7. Spacing & Layout Architecture

### The 8px Cohesive Spacing Scale:
Use a standardized spacing scale across padding, margins, and component gaps:
$$\text{4px (2xs)} \;\longrightarrow\; \text{8px (xs)} \;\longrightarrow\; \text{12px (sm)} \;\longrightarrow\; \text{16px (md)} \;\longrightarrow\; \text{24px (lg)} \;\longrightarrow\; \text{32px (xl)} \;\longrightarrow\; \text{48px (2xl)}$$

### Layout Rules:
- **Predictable Flow**: Use CSS Flexbox and CSS Grid. Avoid arbitrary absolute positioning (`position: absolute; top: 137px;`).
- **Maximum Content Width**: Constrain content containers (e.g., `max-width: 1200px; margin: 0 auto;`) to prevent awkward ultra-wide stretching on large displays.
- **Generous Touch / Click Targets**: All interactive elements must maintain a minimum target size of $\ge 36\text{px} \times 36\text{px}$ ($\ge 44\text{px}$ for touch).

---

## 8. Interactive Component Standards

### Buttons:
- **Action-Specific Verbs**: Use explicit, descriptive labels (e.g., *"Analyze Architecture"*, *"Export Report"*, *"Deploy Test"*). Never use *"Click Here"* or generic *"Submit"*.
- **Clear Hierarchy**: 1 prominent Primary button per view; Secondary/Ghost buttons for auxiliary actions; Danger button style for destructive actions.
- **Interactive States**: Every button must implement distinct visual states for: `Default`, `Hover`, `Active/Pressed`, `Focus`, `Disabled`, and `Loading` (with inline spinner).
- **No Dead Buttons**: Every visible button must execute an actual, verified capability.

### Forms & Inputs:
- **Explicit Labels**: Every input, textarea, and dropdown must have a visible `<label>`.
- **Actionable Validation**: Validation errors must be displayed inline and state clearly:
  $$\mathbf{WHAT\ IS\ WRONG} \quad+\quad \mathbf{HOW\ TO\ FIX\ IT}$$
  *(e.g., "Invalid Port Number: Enter a numeric port between 1 and 65535.")*

---

## 9. Reusable Notification & Feedback Hierarchy

Choose the least disruptive feedback mechanism appropriate to the event:

```text
┌─────────────────┬───────────────────────────────────┬───────────────────────────────────────────┐
│ Feedback Type   │ Operational Context               │ Examples                                  │
├─────────────────┼───────────────────────────────────┼───────────────────────────────────────────┤
│ INLINE MESSAGE  │ Field-level guidance or error     │ Form validation, input length warnings    │
│ TOAST           │ Brief, non-blocking confirmation  │ "Report copied to clipboard", "Saved"     │
│ BANNER / ALERT  │ Persistent system/page status     │ "API rate limit reached", "Offline mode"  │
│ MODAL DIALOG    │ Focused, high-impact user decision│ Critical configuration, export parameters │
│ CONFIRMATION    │ Irreversible or destructive action│ "Delete database record", "Reset project" │
└─────────────────┴───────────────────────────────────┴───────────────────────────────────────────┘
```

> **Rule**: Never use modal popups for routine non-critical status updates that could be handled by a subtle toast or inline badge.

---

## 10. Comprehensive Lifecycle UI States

Every view or dynamic container must support all five operational lifecycle states while **preserving surrounding layout geometry** to eliminate jarring visual jumps:

1. **Empty State**: Displays clear icon, explanation of why no data exists, and an immediate call-to-action button (e.g., *"No scan records found. Run your first vulnerability scan to generate findings."* + `[Run Scan]`).
2. **Loading State**: Displays subtle spinner or skeleton card placeholders with meaningful progress text (*"Analyzing dependencies (Step 2/4)..."*).
3. **Success State**: Clean presentation of results with prominent export/action buttons.
4. **Error State**: Non-destructive alert badge explaining the failure and offering a one-click `[Retry]` or `[Reset]` action.
5. **Disabled State**: Visual dimming ($50\text{–}60\%$ opacity) with `cursor: not-allowed` during active background processing.

---

## 11. Data-Dense Tables & Dashboard Rules

### Dashboard Restraint:
- **Dashboards Are NOT Mandatory**: Build a dashboard only if the hackathon problem statement explicitly mandates continuous overview monitoring.
- **No Fake Metrics / Vanity Cards**: Strictly forbid adding 12 generic KPI cards with fabricated percentages, meaningless trend arrows, or decorative heatmaps. Every metric must have a live, verifiable data source.

### Data Tables & Technical Lists:
- Use clear column headers, left-aligned text, right-aligned numerical data, and monospaced alignment for identifiers and hashes.
- Highlight critical status badges (e.g., `CRITICAL` in red, `PASS` in green) with high-contrast text.

### Charts & Visualizations:
- Before adding any chart, answer: **"What specific user decision does this chart inform?"**
- If the chart provides only decorative value without actionable decision support, **DO NOT INCLUDE IT**.

---

## 12. Easy-to-Use & Easy-to-Demonstrate Rules

### The "Easy-to-Use" Test:
A first-time user must be able to understand:
1. *What is this tool?*
2. *What can I do right now?*
3. *What happened after I took action?*
4. *What should I do next?*

### The "Easy-to-Demonstrate" Test (Judges Rule):
- The primary demo loop must be immediately obvious on the initial landing view.
- Provide a visible **"Load Sample Data"** action next to primary inputs so the presenter can execute a flawless live demonstration in under 60 seconds without live typing errors.

---

## 13. Motion, Icons & Visual Polish

- **Purposeful Motion Only**: Micro-transitions ($\le 150\text{–}200\text{ms}$, `ease-out`) for hover, active tabs, and state changes. Never add decorative floating blobs, looping background spins, or sluggish animations.
- **Consistent Icon Family**: Use a single, clean icon library (e.g., Lucide, Heroicons, standard SVG set). Icons must always accompany explicit text labels when representing primary actions.

---

## 14. Design Decision Record Template

Before implementing substantial UI in any hackathon project, record the design choices in `docs/04-product/PRD_TEMPLATE.md` or `.ai/DECISIONS.md`:

```text
==================================================
PROJECT DESIGN SYSTEM SPECIFICATION
==================================================
VISUAL DIRECTION: <Enterprise / Modern SaaS / Technical Utility / Minimal / etc.>
RATIONALE: <Why this direction fits the target user and problem domain>
COLOR SYSTEM:
  - Primary Action Color: <e.g., Deep Indigo #4f46e5>
  - Canvas Background: <e.g., Slate Dark #0f172a / Crisp Light #ffffff>
  - Surface Cards: <e.g., #1e293b / #f8fafc>
  - Semantic Colors: Standard Success / Warning / Error / Info
TYPOGRAPHY: <Primary UI Font / Technical Monospace Font>
LAYOUT MODEL: <Responsive Flex/Grid, max-width: 1200px, 8px scale>
PRIMARY COMPONENTS: <Button, Input, Card, Table, Status Badge, Inline Alert>
NOTIFICATION APPROACH: <Inline validation + Toast confirmations>
TARGET PRESENTATION VIEWPORT: <1920x1080 Widescreen Laptop / Desktop>
ACCESSIBILITY BASELINE: <WCAG AA contrast, semantic HTML, visible focus>
==================================================
```
