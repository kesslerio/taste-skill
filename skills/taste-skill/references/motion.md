# Motion

## Critical
- Never drive magnetic hover or continuous animation loops with React `useState`.
- For Framer Motion, use `useMotionValue` and `useTransform` for cursor-reactive movement outside render cycle.
- Infinite/perpetual animations must be isolated in small client components and memoized.
- Parent/child `staggerChildren` orchestration must remain in one client component tree.
- Do not mix GSAP/ThreeJS and Framer Motion in the same component tree.
- If using imperative animation APIs (`useEffect`, GSAP, ThreeJS), always include strict teardown cleanup.
- Avoid direct `window.addEventListener('scroll')` choreography for high-intensity motion systems.

## Defaults
- Motion behavior by `MOTION_INTENSITY`:
  - `1-3`: hover/active only, no autoplay.
  - `4-7`: smooth transitions, transform/opacity load-ins, light stagger.
  - `8-10`: advanced choreography (parallax/shared element transitions) with strict performance budgeting.
- Use spring transitions for tactile feel: `type: "spring", stiffness: 100, damping: 20`.
- Prefer Framer `layout` and `layoutId` for reflow, reorder, and shared transitions.
- Do not instantly mount heavy lists/grids; use staggered reveals (`staggerChildren` or indexed CSS delays).
- Use skeleton shimmer and waterfall reveals over abrupt list/grid mounts.

## Optional
- "Liquid glass" refinement: combine blur with thin inner border and subtle inner highlight shadow.
- Add micro-physics (`-translate-y-[1px]`, `scale-[0.98]`) on active presses for tactile confirmation.
- Add looped ambient motion (pulse/float/typewriter/carousel) where it improves scanability.
- GSAP/ThreeJS are valid for isolated full-page scrolltelling or canvas backgrounds only.
