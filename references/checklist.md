# Pre-Flight Checklist

## Critical (Must Pass)
- [ ] Dependency availability verified before imports; missing packages surfaced with install commands.
- [ ] Server/client boundary is correct (`'use client'` only where required).
- [ ] Full-height sections use `min-h-[100dvh]` (not `h-screen`).
- [ ] Mobile fallback is guaranteed for high-variance desktop layouts.
- [ ] Motion animates only `transform`/`opacity`.
- [ ] Infinite/perpetual motion is isolated and memoized.
- [ ] `useEffect`/imperative animations include cleanup.
- [ ] Loading, empty, and error states are present.

## Defaults (Should Pass)
- [ ] Palette is coherent, single-accent, and avoids AI-purple bias.
- [ ] Typography and spacing rhythm are deliberate and non-generic.
- [ ] Card usage is intentional; separators/negative space used when better.
- [ ] Icon library and stroke-width consistency are enforced.

## Optional (Quality Boosters)
- [ ] Staggered entrance sequencing improves scanability.
- [ ] Tactile active states are implemented on primary actions.
- [ ] Hero/layout pattern avoids default centered-template look.
