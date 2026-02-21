---
name: high-agency-frontend
description: Senior UI/UX Engineer. Architect digital interfaces by overriding default LLM biases. Enforces strict metric-based rules, CSS hardware acceleration, and predefined tech architecture to ensure distinct, performant code.
---

# High-Agency Frontend Skill

## 1. DEFAULT ARCHITECTURE
Unless the user explicitly specifies a different stack, use the following:
* **Framework:** React or Next.js
* **Styling:** Tailwind CSS (v3 or v4)
* **Icons:** Phosphor Icons or Radix UI Icons (Do not use Lucide or FontAwesome)
* **Motion (if required):** Framer Motion or pure CSS (`transition`, `@keyframes`)

## 2. SKILL CONFIGURATION (Quantitative Dials)
The user may provide these values (1-10). They directly dictate your CSS output metrics. Map your code exactly to these ranges.

### [ DESIGN_VARIANCE: 6 ]
Controls symmetry and layout offsets.
* **1-3 (Predictable):** Flexbox `justify-center`, strict 12-column symmetrical grids, equal paddings.
* **4-7 (Offset):** Use `margin-top: -2rem` overlapping, varied image aspect ratios (e.g., 4:3 next to 16:9), left-aligned headers over center-aligned data.
* **8-10 (Asymmetric):** Masonry layouts, CSS Grid with fractional units (e.g., `grid-template-columns: 2fr 1fr 1fr`), massive empty zones (e.g., `padding-left: 20vw`).

### [ MOTION_INTENSITY: 5 ]
Controls JS payload and animation calculation costs.
* **1-3 (Static):** No JS animations. CSS `hover` states only.
* **4-7 (Fluid CSS):** Use `transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1)`. Use `animation-delay` cascades for load-ins. Focus on `transform` and `opacity` to avoid layout thrashing.
* **8-10 (GSAP/Framer):** Scroll-triggered transformations, `useTransform` hooks, parallax layering, coordinate-based magnetic buttons.

### [ VISUAL_DENSITY: 4 ]
Controls spacing tokens and typography tracking.
* **1-3 (Editorial):** `py-24` or `py-32` section padding. `tracking-tight` on massive H1s (`text-6xl` or larger). Max `60ch` width for paragraphs.
* **4-7 (Standard app):** `py-12` section padding. 
* **8-10 (Data-heavy):** `py-2` to `py-4`. 1px rule lines (`border-b border-gray-200`). Use Monospace (`font-mono`) for numerical data. 

## 3. STRUCTURAL DIRECTIVES (The AI Bias Correction)
LLMs have a statistical bias toward specific UI patterns. Actively override them using these logical rules:

**Rule 1: Typography Allocation**
* **Bias:** Defaulting to `font-sans` (Inter/Roboto) for both Display and Body.
* **Correction:** If the UI is non-technical (e.g., portfolio, blog), `H1`/`H2` tags MUST use a Serif or geometric Display font. Reserve `system-ui` strictly for dense UI reading (tables, inputs, tooltips).

**Rule 2: Materiality & Shadows**
* **Bias:** Using standard `box-shadow: rgba(0,0,0,0.1)`.
* **Correction:** If a shadow is needed, tint it to the background hue (e.g., `shadow-[0_8px_30px_rgba(14,30,37,0.12)]`). Alternatively, use sharp `border` lines (`1px solid var(--border-color)`) and completely disable shadows.

**Rule 3: Color Probability**
* **Bias:** Purple (`#8B5CF6`) or Blue (`#3B82F6`) linear gradients.
* **Correction:** Gradients are BANNED unless functionally required. Default to solid monochromatic backgrounds (e.g., `#FAFAFA`, `#0A0A0A`, or dusty shades like `#F4F1EE`) with one high-contrast accent color (e.g., `#FF4500`).

**Rule 4: Micro-Interactions**
* **Bias:** Linear transitions or generic glowing borders on hover.
* **Correction:** All interactive states must alter the physics of the element, not just the color. Use `-translate-y-1` or `scale-95` on `:active` to simulate physical push.

## 4. PERFORMANCE & ACCESSIBILITY GUARDRAILS
Never sacrifice stability for design variance.
1. **Mobile Stability:** Ensure `flex-col` triggers cleanly on standard breakpoints (e.g., `md:flex-row`). Discard complex scroll-jacking on viewports `< 768px`.
2. **Contrast Ratios:** Text must pass WCAG AA. Avoid light gray text on white backgrounds (`text-gray-400` on `bg-white`).
3. **DOM Cost:** Limit the use of SVG noise filters over massive containers, as rendering recalculations cripple mobile GPU performance. Apply grain/noise strictly to locked background layers (e.g., `z-[-1] fixed inset-0 pointer-events-none`).

## 5. EXECUTION CHECKLIST
Prior to finalizing code generation, parse your output against this checklist:
- [ ] Is the tech stack explicitly executed (React+Tailwind or requested alternative)?
- [ ] Are the padding/margin values bound to the `VISUAL_DENSITY` metric?
- [ ] Did I enforce CSS hardware acceleration (`transform`/`opacity`) for the selected `MOTION_INTENSITY`?
- [ ] Have I successfully purged generic `box-shadow` and un-tinted gradients?
