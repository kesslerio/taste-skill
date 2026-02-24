# Taste-Skill (High-Agency Frontend)

This project gives your AI (like in Antigravity, Cursor, Codex, Claude Code) good taste. It stops the AI from generating boring, generic, "slop" code and forces it to build modern, high-end interfaces.

This skill now uses a compact `SKILL.md` dispatcher plus `references/*.md` for detailed guidance. Install the full folder, not just one file.


## IMPORTANT: Feedback & Contributions
I’d love to hear your thoughts! If you have suggestions or find any bugs:

Open a Pull Request or Issue right here on GitHub.

Shoot me a DM on x.com/lexnlin

Or email me at: hello@learn2vibecode.dev


## How to Install

Use the full skill folder so the dispatcher can load its references.

Required files:
- `SKILL.md`
- `references/design-rules.md`
- `references/motion.md`
- `references/anti-patterns.md`
- `references/bento-recipes.md`
- `references/checklist.md`

Quick install:
```bash
git clone https://github.com/kesslerio/taste-skill.git
# copy or symlink the entire folder into your skills directory
```

If you only copy `SKILL.md`, you will lose most strict guidance and quality guardrails.

1. Clone or download the full repository folder.
2. Copy or symlink the entire `taste-skill/` folder into your skills directory.
3. Tell your AI: *"Please read and follow `SKILL.md` and its `references/*.md` files."*

That's it. The AI will load the dispatcher plus references and apply the full rule set.

## The 3 Control Dials

At the very top of `SKILL.md`, you will find three settings. They look like this:
* `DESIGN_VARIANCE: 8`
* `MOTION_INTENSITY: 6`
* `VISUAL_DENSITY: 4`

You can change these numbers from `1` to `10` depending on what you want to build. Here is what they actually do:

### 1. DESIGN_VARIANCE (1 to 10)
This controls how crazy or normal the layout looks.
* **1 to 3 (Normal):** Very safe, centered layouts. Standard grids where everything lines up perfectly.
* **4 to 7 (Creative):** Things overlap a bit. Text might be pushed to the side, images have different sizes.
* **8 to 10 (Wild):** Asymmetric layouts, huge empty spaces, masonry grids. Very artsy and modern.

### 2. MOTION_INTENSITY (1 to 10)
This controls how much stuff moves on the screen.
* **1 to 3 (Static):** Almost no movement. Just simple color changes when you hover over a button.
* **4 to 7 (Smooth):** Nice fade-ins when the page loads. Smooth scrolling.
* **8 to 10 (Cinematic):** Buttons that magnetic-pull to your mouse. Elements that pop in with spring physics. Advanced scrolling effects.

### 3. VISUAL_DENSITY (1 to 10)
This is all about "Room to Breathe". It controls how much stuff is packed onto one screen.

* **1 to 3 (The "Art Gallery" Mode):** 
  Everything has huge space. One big photo, one big title. You have to scroll to see the next thing. This feels expensive and high-end, like a luxury brand (Apple, Gucci).
* **4 to 7 (The "Daily App" Mode):** 
  Normal spacing. Like Instagram or a news site. Not too crowded, but you can see enough.
* **8 to 10 (The "Cockpit" Mode):** 
  Everything is tiny and packed together. No big cards, just thin lines and lists. You can see 100 numbers and stats at once without scrolling. This is for pros (Trading apps, Dashboards, Sci-Fi interfaces).

## Examples
*(Example projects and templates will be added in a future update! Stay tuned!)*
