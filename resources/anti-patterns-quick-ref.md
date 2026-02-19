# Anti-Patterns Quick Reference Card

> Print this. Tape it next to your screen. Check every component against it.

## ❌ FORBIDDEN — Visual

```
background: linear-gradient(135deg, #667eea, #764ba2)   ← BANNED gradient
box-shadow: 0 0 20px rgba(99, 102, 241, 0.5)            ← neon glow
backdrop-filter: blur(12px)                              ← glassmorphism reflex
box-shadow: 0 4px 24px rgba(0,0,0,0.15)                 ← generic drop shadow
text-align: center  (on every heading)                   ← static centering
```

## ❌ FORBIDDEN — Components

- `border-radius: 999px` on badge/tag elements → use `border-radius: 2px` or `0`
- White `#FFFFFF` background + `#E5E7EB` border + drop shadow card
- 3-equal-column grid (bento pattern)
- Any icon from Heroicons/Feather used generically (rocket, shield, star, check-circle)
- Linear gradient button (`from-indigo-500 to-purple-600`)

## ✅ ALLOWED — Replacements

| Instead of... | Use... |
|---|---|
| Pill badge | `[ LABEL ]` with 1px border, `border-radius: 2px` |
| Card component | Spacing + rule lines as visual separator |
| Drop shadow | `box-shadow: 4px 4px 0px var(--ink)` (hard, retro) |
| Icon | SVG abstract mark, typographic symbol, or `<span>01</span>` numeral |
| Center alignment | Left-aligned with intentional offset margin or indent |
| Gradient header | Solid color + grain overlay + extreme type size |

## ✅ ALLOWED — Color Starting Points

### Editorial (Mode A)
```css
--bg: #F5F0E8;  --fg: #0D0B08;  --accent: #BFFF00;
```

### Precision (Mode B)
```css
--bg: #F4F1EC;  --fg: #2A2A2A;  --accent: #D4603A;
```

### Installation (Mode C)
```css
--bg: #080808;  --fg: #F0F0F0;  --accent: #FF3B00;
```
