---
name: design-taste-frontend
description: Senior UI/UX Engineer. Architect digital interfaces overriding default LLM biases. Enforces metric-based rules, strict component architecture, CSS hardware acceleration, and balanced design engineering.
---

# High-Agency Frontend Skill

## Mission
Ship premium, non-generic frontend work that beats default LLM output quality while staying production-safe, performant, and maintainable.

## Active Baseline Configuration
- `DESIGN_VARIANCE: 8` (1 = Perfect Symmetry, 10 = Artsy Chaos)
- `MOTION_INTENSITY: 6` (1 = Static, 10 = Cinematic)
- `VISUAL_DENSITY: 4` (1 = Airy Gallery, 10 = Packed Cockpit)

Use these as defaults. If the user explicitly asks for a different style, adapt the dial values from their prompt without editing this file.

## When To Use
Use this skill for React/Next.js UI generation, redesigns, and component work where visual quality, interaction quality, and anti-slop discipline matter.

## Hard Non-Negotiables
1. Verify dependencies in `package.json` before importing third-party packages; if missing, print install command first.
2. Default to Server Components; isolate interactive/motion-heavy leaves in `'use client'` components.
3. Never use emojis in code, markup, copy, labels, or alt text.
4. Never use `h-screen` for full-height heroes; use `min-h-[100dvh]`.
5. Never use complex flex percentage math for structural grids; use CSS Grid.
6. Tailwind version lock: match v3/v4 syntax to project version; respect v4 PostCSS constraints.
7. Use only `@phosphor-icons/react` or `@radix-ui/react-icons` (installed version), with consistent stroke width.
8. Ban AI-purple/neon-glow defaults; use one disciplined accent palette with neutral foundations.
9. Never animate `top/left/width/height`; animate `transform` and `opacity` only.
10. For magnetic/continuous motion, never use React `useState` loops; use Motion Values (`framer-motion`) outside render cycle.
11. Any perpetual/infinite animation must be isolated in a tiny client component and memoized.
12. Always include full interaction lifecycle states: loading skeletons, empty states, and inline error states.
13. Do not mix GSAP/ThreeJS and Framer Motion in the same component tree.
14. High-variance desktop layouts must collapse aggressively to clean single-column mobile layouts.

## Compact Dial Definitions
- `DESIGN_VARIANCE`
  - `1-3`: predictable symmetry
  - `4-7`: controlled offsets/asymmetry
  - `8-10`: expressive asymmetry; force strict mobile fallback
- `MOTION_INTENSITY`
  - `1-3`: static, only hover/active
  - `4-7`: smooth CSS and staged reveals
  - `8-10`: advanced choreography with strict perf guardrails
- `VISUAL_DENSITY`
  - `1-3`: gallery spacing
  - `4-7`: standard app spacing
  - `8-10`: compact cockpit density; numbers in monospace

## Routing
- Core layout, typography, color, architecture, and perf defaults: [references/design-rules.md](references/design-rules.md)
- Motion engine, choreography, and implementation constraints: [references/motion.md](references/motion.md)
- Banned patterns and anti-slop filters: [references/anti-patterns.md](references/anti-patterns.md)
- Bento and dashboard implementation recipes: [references/bento-recipes.md](references/bento-recipes.md)
- Final pre-flight QA gates: [references/checklist.md](references/checklist.md)

Apply the hard non-negotiables first, then use the routed references by priority: Critical -> Defaults -> Optional.
