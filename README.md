# Material 3 Playground

An unofficial, standalone developer playground for **Material Design 3 Components** — featuring the **Loading Indicator** and **Linear Progress Indicator** — built entirely with vanilla **HTML**, **CSS**, and **JavaScript** without frameworks, bundlers, or external dependencies.

> **Disclaimer:** This is an unofficial community developer tool inspired by Material Design 3 guidelines. It is not affiliated with or endorsed by Google or the Material Design team.
>
> Official Material 3 References:
> - [Material Design 3 Loading Indicator](https://m3.material.io/components/loading-indicator/overview)
> - [Material Design 3 Progress Indicators](https://m3.material.io/components/progress-indicators/overview)

---

## Overview

This playground allows developers to:
1. **Explore and Customize**: Adjust modes, size/thickness, colors, speed, stroke, container styling, and motion parameters in real-time.
2. **Preview Live**: Inspect smooth 60 FPS animations inspired by Android AOSP `androidx.graphics.shapes` and Jetpack Compose Material 3 Expressive.
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
  - **Indeterminate**: Dual-bar overlapping animation using authentic M3 cubic-bezier curves (`cubic-bezier(0.65, 0.815, 0.735, 0.395)` and `cubic-bezier(0.165, 0.84, 0.44, 1)`).
  - **Determinate**: Precision progress percentage (0–100%) with 4dp stop indicator dot.
- **Visual Variants**:
  - **Standard Linear**: Clean pill track with dual moving bars or progress fill.
  - **Wavy Expressive**: Sinusoidal wave path (`d="M 0 12 Q ..."` with 32px wave repeat) scrolling seamlessly or clipping with `stroke-dashoffset`.
- **Four-Color Cycle**: Optional Material 3 expressive multi-color indeterminate cycling (Primary, Teal, Tertiary, and Error).
- **Dimensions**: Configurable track thickness (2px–16px) and width (160px–560px).
- **Engines**: Pure CSS/SVG (declarative zero-JS) or Vanilla JS controller class.

---

## Playground Features

- **Live Dynamic Controls**: Range sliders, segmented pill switches, color swatches, and hex inputs update preview immediately without page reload.
- **Dedicated Code Tabs**: Inspect separate **HTML**, **CSS**, **JS**, and **Full Document** implementations reflecting the current configuration in real-time.
- **100% Independent Generated Code**: Exported components run out-of-the-box in any standard HTML5 document without external dependencies, frameworks, or build steps.
- **One-Click Actions**:
  - **Copy Code**: Copies selected tab or complete implementation with a Material 3 feedback snackbar.
  - **Download .html**: Generates a self-contained, standalone demo file ready to open in any browser.
- **Accessibility & Motion Compliance**:
  - Proper ARIA attributes (`role="progressbar"`, `role="status"`, `aria-valuenow`, `aria-valuemin`, `aria-valuemax`).
  - Strict support for `@media (prefers-reduced-motion: reduce)`.
- **Light & Dark Theme**: Full Material 3 tonal surface token architecture with instant toggle and `prefers-color-scheme` support.

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

### Example: Pure CSS/SVG Component (Zero JS)

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

.m3-loading-indicator__shape {
  fill: var(--m3-indicator-color);
}

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

### Example: Linear Progress Indicator (Indeterminate Pure CSS)

```html
<!-- Material 3 Linear Progress (Indeterminate) -->
<div class="m3-linear-progress m3-linear-progress--indeterminate" role="progressbar" aria-label="Loading in progress">
  <div class="m3-linear-progress__track">
    <div class="m3-linear-progress__bar m3-linear-progress__bar--primary"></div>
    <div class="m3-linear-progress__bar m3-linear-progress__bar--secondary"></div>
  </div>
</div>

<style>
:root {
  --m3-linear-color: #6750A4;
  --m3-linear-track: #E6E0E9;
  --m3-linear-height: 4px;
  --m3-linear-width: 320px;
  --m3-linear-speed: 2.0s;
}

.m3-linear-progress {
  display: block;
  width: var(--m3-linear-width);
  max-width: 100%;
  height: var(--m3-linear-height);
  position: relative;
}

.m3-linear-progress__track {
  width: 100%;
  height: 100%;
  background-color: var(--m3-linear-track);
  border-radius: 9999px;
  overflow: hidden;
  position: relative;
}

.m3-linear-progress__bar {
  position: absolute;
  top: 0;
  bottom: 0;
  background-color: var(--m3-linear-color);
  border-radius: 9999px;
}

.m3-linear-progress__bar--primary {
  animation: m3-linear-primary var(--m3-linear-speed) cubic-bezier(0.65, 0.815, 0.735, 0.395) infinite;
}

.m3-linear-progress__bar--secondary {
  animation: m3-linear-secondary var(--m3-linear-speed) cubic-bezier(0.165, 0.84, 0.44, 1) infinite;
  animation-delay: calc(var(--m3-linear-speed) * 0.4);
}

@keyframes m3-linear-primary {
  0% { left: -35%; right: 100%; }
  60% { left: 100%; right: -90%; }
  100% { left: 100%; right: -90%; }
}

@keyframes m3-linear-secondary {
  0% { left: -200%; right: 100%; }
  60% { left: 107%; right: -8%; }
  100% { left: 107%; right: -8%; }
}

@media (prefers-reduced-motion: reduce) {
  .m3-linear-progress__bar { animation: none !important; }
}
</style>
```

---

## Architecture & Extensibility

The JavaScript codebase (`script.js`) is conceptually decoupled into modular subsystems:

- **State (`state`)**: Central reactive object managing component properties, theme, and UI state.
- **Component Registry (`components`)**: Pluggable registry containing fully implemented Material 3 components:
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
    linearProgress: {
      name: 'Linear Progress',
      initPreview(container) { ... },
      renderPreview(container, state, elapsed) { ... },
      generateHTML(state) { ... },
      generateCSS(state) { ... },
      generateJS(state) { ... },
      generateFullDocument(state) { ... }
    }
  };
  ```
- **Preview Renderer (`initPreview`, `previewAnimationLoop`)**: High-performance 60 FPS animation loop with spring-scale breathing.
- **Code Generator (`updateCodeViewer`)**: Pure functions producing reactive, production-ready code.
- **Syntax Highlighter (`highlighter`)**: Pure regex tokenizer formatting tags, attributes, properties, strings, and comments without external libraries.
- **Theme Manager (`setupTheme`)**: Light and dark mode manager with `prefers-color-scheme` synchronization.

---

## Browser Support

- Google Chrome / Chromium 80+
- Mozilla Firefox 75+
- Apple Safari (macOS & iOS) 13.1+
- Microsoft Edge 80+

---

## License

MIT License. Free to use in personal, open-source, and commercial projects.
