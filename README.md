# Anti-Slop Frontend Skill

A skill for AI coding agents to build better frontend interfaces. The goal is to avoid standard, generic "AI slop" designs and create websites that look unique, professional, and well-crafted.

---

## How It Works

This repository contains **1 Overall Skill** and **4 Sub-Skills**. The overall skill sets the baseline, while the sub-skills give the agent specific design styles to follow based on the user's request.

### The Overall Skill
The core `SKILL.md` teaches the agent basic rules:
- **No generic UI:** Stop using default gradients, basic glassmorphism, and centered text everywhere.
- **Better feel:** Add texture and depth to the designs.
- **Good typography:** Use strong font pairs and clear text sizes instead of browser defaults.

---

## The 4 Sub-Skills

The agent will choose one of these four sub-skills based on what you ask it to build:

### 1. Editorial & Brutalism
**Best for:** Portfolios, blogs, magazines, and text-heavy sites.
**Look & Feel:** Like a printed fashion magazine or raw HTML.
**Key elements:** Asymmetrical grids, huge text, high black-and-white contrast, and visible borders.

### 2. Precision & Utilitarian
**Best for:** Dashboards, tools, SaaS apps, and calculators.
**Look & Feel:** Like a physical tool, a classic Braun calculator, or Teenage Engineering gear.
**Key elements:** Small legible monospace fonts, subtle neumorphism for buttons, monochromatic colors with one bright accent (like neon orange).

### 3. Cinematic & Installation
**Best for:** Product launches, landing pages, and interactive showcases.
**Look & Feel:** Like a digital art piece or a high-end movie experience.
**Key elements:** Smooth scrolling, 3D or parallax fade effects, full-screen images, and hidden navigation until you need it.

### 4. Motion & Micro-Interactions
**Best for:** Interactive web apps, complex menus, and dynamic buttons.
**Look & Feel:** Like a video game engine with real physics.
**Key elements:** Spring physics instead of basic animations, magnetic buttons that follow the mouse, and visual feedback when clicking.

---

## Output Examples

Here is what you can expect the AI agent to generate for each sub-skill:

### Example 1: Editorial Portfolio (Sub-Skill 1)
- **What it generates:** A webpage with huge, left-aligned text and no rounded corners. Images might have a slight grain effect. It feels like reading a modern newspaper.
- **Code hints:** `font-family: 'Helvetica Neue', Arial, sans-serif;`, `border: 1px solid black;`, `text-transform: uppercase;`.

### Example 2: Synth Dashboard (Sub-Skill 2)
- **What it generates:** A settings menu that looks like an analog synthesizer. Buttons look pressed in when clicked, like physical hardware switches.
- **Code hints:** Real inset shadows, dark themes with bright orange highlights, grid backgrounds, and monospace fonts.

### Example 3: Cinematic Product Launch (Sub-Skill 3)
- **What it generates:** A completely black screen at the start. As you scroll, a large product image slowly fades in from the dark.
- **Code hints:** `background: #000;`, very slow transitions, fading with opacity and blur (`filter: blur(20px)` to `blur(0)`).

### Example 4: Physics Button (Sub-Skill 4)
- **What it generates:** An "Add to Cart" button that bends slightly toward your mouse as you hover. When clicked, it bounces back realistically.

---

## Quick Installation (Terminal)

You can easily install this skill directly into your project or your AI's global skills folder using your terminal.

*(Note: Replace `YOUR_GITHUB_USERNAME` with your actual username once you publish the repository.)*

### 1. Project-Level Installation (Recommended)
Run this command in the root folder of your current project. This gives the AI agent access to the skill for just this project.

```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/antislopfrontend.git .agent/skills/antislopfrontend
```

**Example AI Prompt:**
> "Look at the Anti-Slop Skill in my `.agent/skills` folder and build a landing page for a coffee brand using Sub-Skill 1."

### 2. Global Installation
If your AI agent supports a global skills directory, run these commands to install it permanently across all your projects.

**Mac / Linux:**
```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/antislopfrontend.git ~/.agent/skills/antislopfrontend
```

**Windows (PowerShell):**
```powershell
git clone https://github.com/YOUR_GITHUB_USERNAME/antislopfrontend.git "$HOME\.agent\skills\antislopfrontend"
```

---

## How It Works Internally

When the agent starts a task, it follows a simple process:
1. **Initial Review:** The agent reads `SKILL.md` to understand the general quality standards.
2. **Style Selection:** Based on your request, it picks one of the **4 Sub-Skills** (e.g., if you want a dashboard, it picks *Precision & Utilitarian*).
3. **Execution:** It uses the code hints and examples in the `examples/` folder to build your interface without using generic templates.

---

## License

MIT - use freely, remix aggressively.
