# taste-skill

Strict frontend taste and anti-slop guardrail layer for AI coding workflows.

## Naming
- Repository folder name: `taste-skill`
- Skill frontmatter name (in `SKILL.md`): `design-taste-frontend`

Keep the `SKILL.md` name unchanged for compatibility.

## Install (full folder required)

Do not copy only `SKILL.md`. The skill depends on `references/*.md`.

```bash
git clone https://github.com/kesslerio/taste-skill.git
# copy or symlink the entire taste-skill/ directory into your skills path
```

Required contents:
- `SKILL.md`
- `references/design-rules.md`
- `references/motion.md`
- `references/anti-patterns.md`
- `references/bento-recipes.md`
- `references/checklist.md`

## Composition

Use this as the strict guardrail layer, then combine with `frontend-design-ultimate` for broader generation patterns.

For one-command UX, prefer a wrapper/composed skill that invokes both:
1. `design-taste-frontend` (this repo) for anti-slop constraints and quality gates.
2. `frontend-design-ultimate` for higher-level design/system generation.
