# Material 3 Playground

An unofficial, standalone developer playground for **Material Design 3 Components** — featuring the **Loading Indicator**, **Linear Progress Indicator**, **Circular Progress Indicator**, **Common Buttons**, and **Floating Action Button (FAB)** — built entirely with vanilla **HTML**, **CSS**, and **JavaScript** without frameworks, bundlers, or external dependencies.

> **Disclaimer:** This is an unofficial community developer tool inspired by Material Design 3 guidelines. It is not affiliated with or endorsed by Google or the Material Design team.
>
> Official Material 3 References:
> - [Material Design 3 Loading Indicator](https://m3.material.io/components/loading-indicator/overview)
> - [Material Design 3 Progress Indicators](https://m3.material.io/components/progress-indicators/overview)
> - [Material Design 3 Buttons](https://m3.material.io/components/all-buttons/overview)
> - [Material Design 3 Floating Action Button](https://m3.material.io/components/floating-action-button/overview)

---

## Overview

This playground allows developers to:
1. **Explore and Customize**: Adjust styles, variants, color roles, density, typography, stroke thickness, container elevation, and motion parameters in real-time.
2. **Preview Live**: Inspect smooth 60 FPS animations and realistic interactive state layers (hover, focus, active press, and radial click ripples).
3. **Inspect Independent Code**: View separate, fully working **HTML**, **CSS**, and **JS** implementations, or a combined **Full Document**.
4. **Copy & Paste**: Export 100% self-contained code that runs in any web project without external libraries.

---

## Included Components

### 1. Loading Indicator
The Material 3 Expressive Loading Indicator represents continuous activity for short wait times (<5 seconds), replacing traditional circular spinners with dynamic, organic shape-morphing transitions.

- **Expressive Shape Morphing**: Continuous fluid transitions cycling through 7 canonical Material 3 polygon shapes (*Soft Burst*, *Cookie 9-Sided*, *Pentagon*, *Pill*, *Sunny*, *Cookie 4-Sided*, *Oval*).
- **Single Shape Mode**: Select and freeze or rotate any individual canonical shape (including *Circle*, *Squircle*, *Flower*, *Heart*, and *Triangle*).
- **Container Variants**: *Uncontained* (standard standalone loader) and *Contained* (tonal surface tile with elevation).
- **Style Variants**: *Filled* (solid) and *Outlined* (custom stroke width).
- **Engines**: Pure CSS/SVG SMIL animation or Vanilla JS requestAnimationFrame controller.

### 2. Linear Progress Indicator
Material 3 Linear Progress indicators display loading status along a horizontal track with pill-rounded caps, supporting both standard straight tracks and the new Expressive wavy variant.

- **Progress Modes**:
  - **Indeterminate**: Dual-bar overlapping animation using authentic M3 cubic-bezier curves (`m3-primary-indeterminate-translate`, `m3-primary-indeterminate-scale`, `m3-secondary-indeterminate-translate`, `m3-secondary-indeterminate-scale`).
  - **Determinate**: Precision progress percentage (0–100%) with 4dp stop indicator dot.
- **Visual Variants**:
  - **Standard Linear**: Clean pill track with dual moving bars or progress fill.
  - **Wavy Expressive**: Sinusoidal wave path (`d="M 0 12 Q ..."` with configurable amplitude and wavelength) scrolling seamlessly or clipping with `stroke-dashoffset`.
- **Four-Color Cycle**: Optional Material 3 expressive multi-color indeterminate cycling (Primary, Teal, Tertiary, and Error).
- **Dimensions**: Configurable track thickness (2px–16px) and width (160px–560px).
- **Engines**: Pure CSS/SVG (declarative zero-JS) or Vanilla JS controller class.

### 3. Circular Progress Indicator
Material 3 Circular Progress indicators visualize loading status through circular motion, supporting standard arc spinners and the new Material 3 Expressive wavy circular ring.

- **Progress Modes**:
  - **Indeterminate**: Smooth rotating circular spinner with expanding/collapsing arc keyframes (`m3-circular-rotate` and `m3-circular-dash`).
  - **Determinate**: Precision progress percentage (0–100%) mapped onto circle `stroke-dashoffset`.
- **Visual Variants**:
  - **Standard Circular**: Classic circular arc with rounded caps and track background circle.
  - **Wavy Expressive**: Continuous sinusoidal polar wave path ($r(\theta) = R_0 + A \cdot \sin(N\theta + \phi)$) creating an undulating ripple ring with customizable amplitude (2–10px) and cycle frequency (3–12 waves).
- **Four-Color Cycle**: Optional multi-color cycling across Material 3 primary, teal, tertiary, and error tokens.
- **Dimensions & Timing**: Configurable diameter (24px–120px), stroke thickness (2px–12px), and cycle duration (0.5s–4.0s).
- **Engines**: Pure CSS/SVG (declarative zero-JS) or Vanilla JS controller class (`createM3CircularProgress`).

### 4. Common Buttons
Material 3 buttons communicate actions that users can take, using clear visual hierarchy to indicate importance.

- **5 Material 3 Hierarchy Variants**:
  - **Filled**: High-emphasis container for the screen's primary action.
  - **Elevated**: High-emphasis container with subtle elevation shadow on flat surfaces.
  - **Tonal**: Medium-emphasis secondary container for important alternative actions.
  - **Outlined**: Medium-emphasis with a 1px boundary stroke for actions of equal weight.
  - **Text**: Low-emphasis action with no surface container or border.
- **Icon Placement**: *None*, *Leading icon* (before label), or *Trailing icon* (after label) with automatic alignment and spacing.
- **Sizes & Density**: *Small* (32dp height), *Medium* (40dp standard height), and *Large* (48dp height).
- **Corner Radii**: *Full Pill* (9999px canonical M3), *Rounded* (12dp), and *Subtle* (4dp).
- **Full Width**: One-click toggle to stretch button to container boundaries.
- **States & Ripples**:
  - CSS state layers using `::before` (Hover 8% opacity, Focus 12% opacity, Active 12% opacity).
  - Optional Vanilla JS interactive radial ripple expanding dynamically from pointer click coordinates.
  - Full keyboard accessibility and disabled state handling.

### 5. Floating Action Button (FAB)
A Floating Action Button (FAB) performs the primary, or most common, action on a screen. It appears in front of all other content.

- **4 Standard Sizes**:
  - **Standard**: 56×56dp with 16dp rounded corners and 24dp icon.
  - **Small**: 40×40dp with 12dp rounded corners for secondary actions or tight spaces.
  - **Large**: 96×96dp with 28dp rounded corners and 36dp icon for high-visual priority.
  - **Extended**: 56dp height with 16dp corners, customizable text label, and leading icon.
- **Color Roles**:
  - **Surface**: Subtle tonal surface container (`#ece6f0`) with primary icon color.
  - **Primary**: High-emphasis container with primary container background (`#eaddff`).
  - **Secondary**: Medium-emphasis container with secondary tonal background (`#e8def8`).
  - **Tertiary**: Expressive emphasis with tertiary container accent (`#ffd8e4`).
- **Elevation Levels**:
  - **Standard**: Level 3 resting elevation (6dp) lifting to Level 4 on hover (8dp).
  - **Lowered**: Level 1 resting elevation (1dp) lifting to Level 2 on hover (3dp) for dense interfaces.
- **Interactions**:
  - State layers and box-shadow elevation lift transitions.
  - Optional Vanilla JS radial expansion click ripple ink effect.

---

## Playground Features

- **Live Dynamic Controls**: Range sliders, segmented pill switches, color swatches, and hex inputs update preview immediately without page reload.
- **Dedicated Code Tabs**: Inspect separate **HTML**, **CSS**, **JS**, and **Full Document** implementations reflecting the current configuration in real-time.
- **100% Independent Generated Code**: Exported components run out-of-the-box in any standard HTML5 document without external dependencies, frameworks, or build steps.
- **One-Click Actions**:
  - **Copy Code**: Copies selected tab or complete implementation with a Material 3 feedback snackbar.
  - **Download .html**: Generates a self-contained, standalone demo file ready to open in any browser.
- **Accessibility & Motion Compliance**:
  - Proper ARIA attributes (`role="progressbar"`, `role="status"`, `aria-label`, `aria-valuenow`).
  - Strict support for `@media (prefers-reduced-motion: reduce)`.
- **Light & Dark Theme**: Full Material 3 tonal surface token architecture with instant toggle and `prefers-color-scheme` synchronization.

---

## File Structure

```
material3-playground/
│
├── index.html       # Playground UI, layout, controls, and code tabs
├── style.css        # Material 3 design tokens, responsive grid, dark/light themes
├── script.js        # Reactive state, morph engine, preview, and code generator
└── README.md        # Documentation and usage guide
```

---

## Getting Started

No build step, npm install, or bundler is required. Simply:

1. Double-click `index.html` to open it directly in any modern browser (Chrome, Edge, Firefox, Safari).
2. Or serve the directory using any static web server:
   ```bash
   # Python 3
   python3 -m http.server 8080

   # Node.js (npx)
   npx serve .
   ```
3. Open `http://localhost:8080` in your browser.

---

## Using Generated Components in Your Project

Every code snippet produced by the playground is **100% independent** and has **no dependencies** on this playground.

### Example 1: Material 3 Button (Pure CSS)

```html
<!-- Material 3 Filled Button -->
<button type="button" class="m3-button m3-button--filled">
  <span class="m3-button__icon" aria-hidden="true">
    <svg viewBox="0 0 24 24" width="18" height="18" fill="currentColor">
      <path d="M12 2l2.4 7.2L21.6 12l-7.2 2.4L12 21.6l-2.4-7.2L2.4 12l7.2-2.4z"/>
    </svg>
  </span>
  <span class="m3-button__label">Explore Material 3</span>
</button>

<style>
:root {
  --m3-btn-color: #6750A4;
  --m3-btn-height: 40px;
  --m3-btn-padding-h: 24px;
  --m3-btn-radius: 9999px;
}

.m3-button {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  height: var(--m3-btn-height);
  padding: 0 var(--m3-btn-padding-h);
  border: none;
  border-radius: var(--m3-btn-radius);
  background-color: var(--m3-btn-color);
  color: #ffffff;
  font-family: inherit;
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 0.1px;
  cursor: pointer;
  user-select: none;
  overflow: hidden;
  transition: box-shadow 0.2s cubic-bezier(0.2, 0, 0, 1);
}

.m3-button::before {
  content: "";
  position: absolute;
  inset: 0;
  background-color: currentColor;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.15s cubic-bezier(0.2, 0, 0, 1);
}

.m3-button:hover::before { opacity: 0.08; }
.m3-button:hover { box-shadow: 0 1px 3px 1px rgba(0, 0, 0, 0.15), 0 1px 2px 0 rgba(0, 0, 0, 0.30); }
.m3-button:focus-visible::before { opacity: 0.12; }
.m3-button:active::before { opacity: 0.12; }

@media (prefers-reduced-motion: reduce) {
  .m3-button, .m3-button::before { transition: none !important; }
}
</style>
```

### Example 2: Extended Floating Action Button (FAB)

```html
<!-- Material 3 Extended FAB -->
<button type="button" class="m3-fab m3-fab--extended m3-fab--primary" aria-label="Compose">
  <span class="m3-fab__icon" aria-hidden="true">
    <svg viewBox="0 0 24 24" width="24" height="24" fill="currentColor">
      <path d="M19 13h-6v6h-2v-6H5v-2h6V5h2v6h6v2z"/>
    </svg>
  </span>
  <span class="m3-fab__label">Compose</span>
</button>

<style>
:root {
  --m3-fab-bg: #eaddff;
  --m3-fab-color: #21005d;
  --m3-fab-shadow: 0 6px 10px 0 rgba(0, 0, 0, 0.14), 0 1px 18px 0 rgba(0, 0, 0, 0.12);
  --m3-fab-shadow-hover: 0 8px 10px 1px rgba(0, 0, 0, 0.14), 0 3px 14px 2px rgba(0, 0, 0, 0.12);
}

.m3-fab {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 56px;
  padding: 0 20px;
  gap: 12px;
  border-radius: 16px;
  background-color: var(--m3-fab-bg);
  color: var(--m3-fab-color);
  box-shadow: var(--m3-fab-shadow);
  border: none;
  cursor: pointer;
  overflow: hidden;
  font-family: inherit;
  font-size: 14px;
  font-weight: 500;
  transition: box-shadow 0.2s cubic-bezier(0.2, 0, 0, 1);
}

.m3-fab::before {
  content: "";
  position: absolute;
  inset: 0;
  background-color: currentColor;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.15s cubic-bezier(0.2, 0, 0, 1);
}

.m3-fab:hover { box-shadow: var(--m3-fab-shadow-hover); }
.m3-fab:hover::before { opacity: 0.08; }
.m3-fab:active::before { opacity: 0.12; }
</style>
```

### Example 3: Loading Indicator (Pure CSS/SVG)

```html
<!-- Material 3 Loading Indicator -->
<div class="m3-loading-indicator" role="status" aria-live="polite" aria-label="Loading">
  <svg class="m3-loading-indicator__svg" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
    <path class="m3-loading-indicator__shape" d="M 18.7 27.2 ... Z">
      <animate
        attributeName="d"
        dur="1.5s"
        repeatCount="indefinite"
        values="M 18.7 27.2 ...; M 50.0 1.4 ...; M 18.7 27.2 ..."
        calcMode="spline"
        keyTimes="0; 0.5; 1"
        keySplines="0.2 0 0 1; 0.2 0 0 1"
      />
    </path>
  </svg>
</div>

<style>
.m3-loading-indicator {
  --m3-indicator-size: 48px;
  --m3-indicator-color: #6750A4;
  --m3-indicator-speed: 1.5s;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: var(--m3-indicator-size);
  height: var(--m3-indicator-size);
}

.m3-loading-indicator__svg {
  width: 100%;
  height: 100%;
  transform-origin: center;
  animation: m3-spin var(--m3-indicator-speed) linear infinite;
}

.m3-loading-indicator__shape { fill: var(--m3-indicator-color); }

@keyframes m3-spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@media (prefers-reduced-motion: reduce) {
  .m3-loading-indicator__svg { animation: none !important; }
  .m3-loading-indicator__shape animate { display: none !important; }
}
</style>
```

---

## Architecture & Extensibility

The JavaScript codebase (`script.js`) is conceptually decoupled into modular subsystems:

- **State (`state`)**: Central reactive object managing component properties, active component selection, theme, and code output mode.
- **Component Registry (`components`)**: Pluggable registry containing all Material 3 components:
  ```javascript
  const components = {
    loadingIndicator: {
      name: 'Loading Indicator',
      initPreview(container) { ... },
      renderPreview(container, state, elapsed) { ... },
      generateHTML(state) { ... },
      generateCSS(state) { ... },
      generateJS(state) { ... },
      generateFullDocument(state) { ... }
    },
    linearProgress: { ... },
    circularProgress: { ... },
    button: { ... },
    fab: { ... }
  };
  ```
- **Preview Renderer (`initPreview`, `previewAnimationLoop`)**: High-performance 60 FPS animation loop with spring-scale breathing.
- **Code Generator (`updateCodeViewer`)**: Pure functions producing reactive, production-ready code.
- **Syntax Highlighter (`highlighter`)**: Pure regex tokenizer formatting tags, attributes, properties, strings, and comments without external libraries.
- **Theme Manager (`setupTheme`)**: Light and dark mode manager with `prefers-color-scheme` synchronization.

---

## Future Roadmap & Planned Components

The Material 3 Playground is actively expanding to cover the complete Material 3 component catalog. The following components are planned for upcoming releases:

| Component | Hierarchy & Variants | Key Features | Status |
| :--- | :--- | :--- | :---: |
| **Cards** | Elevated, Filled, Outlined | Media container, headline, subhead, body text, action bar, card selection state | Planned |
| **Chips** | Assist, Filter, Input, Suggestion | Leading icon/avatar, trailing clear action, filter checkmark badge, rounded 8dp radius | Planned |
| **Text Fields** | Filled, Outlined | Animated floating label, leading/trailing icons, supporting text helper, character counter, error validation | Planned |
| **Dialogs** | Alert, Confirmation, Full-Screen | Modal scrim container, icon header, title, scrollable content area, action button row | Planned |
| **Switch & Checkbox** | Selection Controls | Animated switch track thumb with icon slot, tri-state indeterminate checkbox, radio selection | Planned |
| **Navigation Bar** | Bottom Bar & Navigation Rail | 3–5 destination tabs, active pill indicator, badge overlay, responsive switch to vertical rail | Planned |
| **Sliders** | Continuous, Discrete, Range | Interactive thumb track, active track highlight, value bubble indicator, discrete step tick marks | Planned |
| **Badges & Tooltips** | Notification Badges, Tooltips | Small dot badge, large numerical badge (e.g. `99+`), plain tooltips, rich contextual tooltips | Planned |
| **Segmented Buttons** | Single-select & Multi-select | Pill segment row with checkmark indicator and outline borders | Planned |
| **Menus & Top App Bar** | Dropdown Menu, App Bar | Anchored dropdown menu with dividers, small/center/medium/large top app bars | Planned |

---

## Browser Support

- Google Chrome / Chromium 80+
- Mozilla Firefox 75+
- Apple Safari (macOS & iOS) 13.1+
- Microsoft Edge 80+

---

## License

MIT License. Free to use in personal, open-source, and commercial projects.
