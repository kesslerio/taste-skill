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
- [ ] Primary user journeys can be completed within 3 navigation steps.
- [ ] Cancellation is honest and one-click where feasible.

## Defaults (Should Pass)
- [ ] Palette is restrained (generally <=3 primary colors) and avoids neon/AI-purple bias.
- [ ] Typography and spacing rhythm are deliberate and non-generic.
- [ ] Card usage is intentional; separators/negative space used when better.
- [ ] Icon library and stroke-width consistency are enforced.
- [ ] Interaction feedback feels near-instant (~100ms target where feasible).
- [ ] URL slugs are short/human-readable; raw UIDs are avoided in primary routes.
- [ ] State continuity is persistent/resumable where it materially helps users.
- [ ] Hit targets are comfortably large for mouse/touch interactions.
- [ ] Tooltips are minimal; labels/inline context do most of the work.
- [ ] Microcopy is active voice and concise (<=7 words where practical).
- [ ] Layout supports clear left-to-right scanning.
- [ ] Optical alignment choices are validated (not purely geometric centering).
- [ ] Async surfaces use skeleton loading states.
- [ ] App-like products include `Cmd/Ctrl + K` where appropriate.
- [ ] Clipboard workflows (copy/paste) are supported in expected places.
- [ ] Loss-risk moments include reassurance and clear recovery language.

## Optional (Quality Boosters)
- [ ] Staggered entrance sequencing improves scanability.
- [ ] Tactile active states are implemented on primary actions.
- [ ] Hero/layout pattern avoids default centered-template look.
- [ ] Scrollbars are visually hidden in polished surfaces without harming accessibility.
- [ ] Brand surfaces expose copyable SVG logo/brand assets where relevant.
