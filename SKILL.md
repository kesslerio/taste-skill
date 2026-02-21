---
name: high-agency-frontend
description: Creative Technologist & Senior Frontend Engineer skill. Architect digital artifacts using measurable constraints, React-first architecture, specific Tailwind + Raw CSS separation, and strict interaction modes to eradicate "AI Slop".
---

# High-Agency Frontend Skill

## 1. DEFAULT ARCHITECTURE & TOOLING

**Framework & State:**
- React or Next.js (Server Components by default; `"use client"` strictly at the leaf level for interactive UI).
- Use local `useState`/`useReducer` for UI state. Global state is only for preventing deep prop-drilling across the component tree.
- Generate full interaction states proactively: **Loading** (Skeletons, not spinners), **Empty** (designed placeholders), and **Error** (inline feedback).

**Styling Separation:** 
- **Styling Rule:** Use Tailwind CSS for 90% of styling (layout, colors, spacing). Use raw CSS (or CSS Modules) ONLY for complex `@keyframes`, `clamp()` typography, and pseudo-element grain filters where Tailwind strings become unreadable.

**Animation & DOM:**
- **No Vanilla JS DOM manipulation** (e.g., `document.querySelector`, `el.addEventListener`). 
- For complex physics or DOM events, strictly use React patterns: `useRef` and `useEffect`. **Mandatory:** `useEffect` hooks implementing listeners MUST return a cleanup function to prevent memory leaks.
- Prefer `framer-motion` for complex physics and choreography.

---

## 2. THE ANTI-PATTERNS (STRICTLY FORBIDDEN)

Before writing any code, internalize these forced constraints:

| ❌ Forbidden / Generic | ✅ High-Agency Alternative |
|---|---|
| Purple-to-blue linear gradients | Muted editorial tones, solid OLED blacks, or single-accent monochrome |
| Glassmorphism / `backdrop-blur` everywhere | Solid opacity layers, or highly specific "Liquid Glass" (1px inner border + inset shadow) |
| Standard `box-shadow: rgba(0,0,0,0.1)` | Tinted ambient shadows matching the background hue, or no shadow (use 1px borders) |
| Centered bento grids for everything | Asymmetric layouts or massive intentional whitespace (fallback to mobile column) |
| "Everything is a Card" | Rely on spacing and alignment to group data instead of boxed cards |

---

## 3. DESIGN ENGINEERING DIRECTIVES

### Typography Intent
- **Contextual Selection:** Modern B2B tools excel with clean Sans-Serifs (`Inter`, `Geist`). Do not force Serif fonts unless the context explicitly demands an editorial, luxury, or portfolio aesthetic.
- **Display Typography:** Add tracking adjustments to large text (e.g., `tracking-tighter leading-none` on massive headers).

### Data & Form Patterns
- **Forms:** Label MUST sit above input. Helper text is optional but should exist in markup. Error text MUST sit below the input. Group elements with a standard `gap-2`.

### Responsive Stability
- **Mobile Override:** Any asymmetric or complex grid layout on desktop (`md:`) MUST collapse gracefully to a clean, single-column layout (`w-full`, `px-4`, `py-8`) on viewports `< 768px`. Do not allow horizontal overflow.

---

## 4. ADVANCED TECHNIQUES (When explicitly requested)

These are reserved for high-end creative requests. Do NOT apply these to standard dashboards or simple landing pages unless explicitly asked.

### Performance-Safe Grain
- **Rule:** Dithering and grain destroy mobile GPUs if applied to scrolling containers.
- **Execution:** Apply grain filters exclusively to fixed, pointer-event-none pseudo-elements (`fixed inset-0 z-50 pointer-events-none`) and NEVER to scrolling containers to prevent continuous GPU repaints.
  ```css
  /* RAW CSS allowed here for readability */
  .grain-overlay {
    position: fixed; inset: 0; z-index: 50; pointer-events: none;
    background-image: url("data:image/svg+xml,..."); /* base64 noise SVG */
    opacity: 0.04;
  }
  ```

### Staggered Reveal
- Use CSS cascades or Framer Motion `staggerChildren` to reveal elements sequentially. Avoid mounting 20 list items instantly.
  ```css
  .reveal-item { animation-delay: calc(var(--index) * 100ms); }
  ```

### Magnetic Micro-physics
- For high-end portfolios only. Buttons physically pull toward the cursor.
- **Execution:** Use Framer Motion `useTransform` mapped to mouse coordinates, NOT vanilla JS.

---

## 5. EXECUTION SCENARIOS (Concrete Snippets)

### Scenario A: Complex Header (Tailwind + Raw CSS approach)
- **Concept:** A massive headline scaling fluidly without huge Tailwind bracket strings.
```jsx
// HTML (Tailwind for layout)
<h1 className="fluid-headline text-zinc-900 tracking-tighter">
  Vanguard
</h1>
// CSS (Raw CSS for fluid math)
.fluid-headline { font-size: clamp(3rem, 8vw, 8rem); line-height: 0.9; }
```

### Scenario B: High-End Form Input
- **Concept:** Predictable structure, explicit states, no guessing.
```jsx
<div className="flex flex-col gap-2 w-full max-w-md">
  <label className="text-sm font-medium text-zinc-800">Email</label>
  <input className="px-4 py-2 border border-zinc-200 focus:ring-2 focus:ring-zinc-900 rounded-none transition-all" />
  <span className="text-xs text-red-500">Error message placeholder</span>
</div>
```

---

## 6. PRE-FLIGHT CHECKLIST

Before generating your final React output, verify internally:
- [ ] Is my styling separated correctly (Tailwind for 90%, CSS for complex clamps/keyframes)?
- [ ] Did I avoid Vanilla JS `el.addEventListener` in favor of React `useEffect` / `useRef`?
- [ ] If using `useEffect` for events or animations, is there a strict cleanup function?
- [ ] Is grain/noise applied ONLY to a `fixed inset-0 pointer-events-none` container?
- [ ] Are structural states (Loading skeletons, Empty, Errors) included?
- [ ] Does the mobile view collapse safely?
