# Design Rules

## Critical
- Verify package availability in `package.json` before imports; output install command when missing.
- React/Next.js default architecture:
  - Server Components first.
  - Global providers/state only in client components.
  - Motion/liquid-glass interactivity must be isolated in leaf `'use client'` components.
- State scope discipline:
  - Prefer local `useState`/`useReducer` for isolated UI state.
  - Use global state only to avoid deep prop drilling.
- Tailwind version discipline:
  - Match syntax to installed major version.
  - In v4, do not use legacy `tailwindcss` PostCSS plugin; use supported v4 integration.
- Full-height stability: use `min-h-[100dvh]`, not `h-screen`.
- Structural layout reliability: use grid for multi-column composition; avoid flex calc hacks.
- Performance safety:
  - Animate only `transform` and `opacity`.
  - Apply grain/noise overlays only on fixed, pointer-event-none layers.
  - Use z-index intentionally for real layering contexts, not arbitrary stacking.

## Defaults
- Typography baseline:
  - Display: `text-4xl md:text-6xl tracking-tighter leading-none`
  - Body: `text-base text-gray-600 leading-relaxed max-w-[65ch]`
- Premium sans stack preference: `Geist`, `Outfit`, `Cabinet Grotesk`, `Satoshi`.
- Dashboard/software UI constraint: serif is disallowed.
- Color calibration:
  - One accent color maximum.
  - Keep saturation controlled (<80% target).
  - Hold one coherent temperature across neutrals.
- Layout diversification:
  - For `DESIGN_VARIANCE > 4`, avoid centered hero defaults.
  - Prefer split-screen, asymmetric whitespace, and offset compositions.
- Responsive containers: prefer `max-w-[1400px] mx-auto` or `max-w-7xl mx-auto`.
- Icon policy: use only `@phosphor-icons/react` or `@radix-ui/react-icons`, and keep stroke width consistent globally.
- Forms:
  - Labels above inputs.
  - Optional helper text present in markup when needed.
  - Errors below inputs.
  - Use consistent vertical rhythm (`gap-2` blocks).

## Optional
- Use subtle tinted shadows that match background hue when elevation is meaningful.
- For high-density interfaces, prefer separators (`border-t`, `divide-y`) and whitespace grouping over card overuse.
- For `VISUAL_DENSITY > 7`, run cockpit mode:
  - Reduce padding and visual noise.
  - Favor line-divided surfaces over boxed cards.
  - Use monospace for numeric-heavy data.
- Keep major cards/containers on generous padding (`p-8` or `p-10`) when density permits.
