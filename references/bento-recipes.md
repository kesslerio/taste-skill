# Bento Recipes

## Critical
- For modern SaaS/dashboard feature sections, default to a Bento 2.0 composition instead of generic equal cards.
- Keep perpetual card animations lightweight, isolated, and memoized.
- Use layout-aware transitions (`layout`, `layoutId`) for card reordering/resizing behavior.

## Defaults
- Baseline aesthetic:
  - Background: `#f9fafb`
  - Surface: white cards with light border (`border-slate-200/50`)
  - Container radius: `rounded-[2.5rem]`
  - Shadow: soft diffusion, wide and subtle
- Typography stack: `Geist`, `Satoshi`, or `Cabinet Grotesk` with tight tracking on headings.
- Place titles/descriptions outside/below cards when using gallery-style presentation.
- Suggested 5 archetypes:
  1. Intelligent List: auto-sorting stack via shared layout ids.
  2. Command Input: typewriter + processing shimmer state.
  3. Live Status: breathing indicator + overshoot notification.
  4. Wide Data Stream: seamless horizontal infinite carousel.
  5. Contextual UI: staggered highlight + floating action toolbar.

## Optional
- Common row patterns:
  - `3-up` asymmetric top row + `70/30` second row.
  - Hybrid masonry + spotlight tiles for feature storytelling.
- Creative arsenal for non-generic interfaces:
  - Navigation: dock magnification, magnetic buttons, gooey menus, dynamic-island morphs, radial actions.
  - Layout: bento grids, masonry, chroma borders, split-scroll, curtain reveals.
  - Cards: parallax tilt, spotlight borders, glass panels, holographic foil, swipe stacks, morphing modals.
  - Scrolltelling: sticky stacks, horizontal scroll transforms, zoom parallax, SVG progress paths, liquid wipes.
  - Media: coverflow, drag-to-pan grids, accordion sliders, hover image trails, controlled glitch states.
  - Type: kinetic marquees, mask reveals, scramble effects, circular text paths, animated strokes.
  - Micro-effects: shimmer skeletons, direction-aware hover fills, click ripples, SVG line-draw, mesh gradients.
- Add restrained ambient loops to keep the surface alive without reducing readability.
