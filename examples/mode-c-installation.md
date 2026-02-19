# Mode C — The Installation: Implementation Pattern

## When to Use
Brand landing pages, art-direction experiences, creative portfolios, event pages.

## Core Visual: Dark + Grain + Motion

```css
:root {
  --void: #080808;
  --light: #F0F0F0;
  --spark: #FF3B00; /* one surprise color */
  --grotesk: 'Space Grotesk', sans-serif;
  --mono: 'DM Mono', monospace;
}

body {
  background: var(--void);
  color: var(--light);
  font-family: var(--grotesk);
  overflow-x: hidden;
}

/* Grain overlay — the signature texture */
body::after {
  content: '';
  position: fixed; inset: 0;
  pointer-events: none;
  z-index: 9999;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.4'/%3E%3C/svg%3E");
  opacity: 0.035;
}
```

## Magnetic Cursor Field

```js
// Full cursor displacement system
class CursorField {
  constructor() {
    this.cursor = document.createElement('div');
    this.cursor.className = 'cursor-field';
    document.body.appendChild(this.cursor);
    
    this.x = 0; this.y = 0;
    this.targetX = 0; this.targetY = 0;
    
    document.addEventListener('mousemove', e => {
      this.targetX = e.clientX;
      this.targetY = e.clientY;
    });
    
    this.animate();
  }
  
  animate() {
    // Lag for smooth trailing
    this.x += (this.targetX - this.x) * 0.08;
    this.y += (this.targetY - this.y) * 0.08;
    
    this.cursor.style.transform = `translate(${this.x}px, ${this.y}px)`;
    requestAnimationFrame(() => this.animate());
  }
}

new CursorField();
```

```css
.cursor-field {
  position: fixed;
  width: 400px; height: 400px;
  top: -200px; left: -200px;
  pointer-events: none;
  z-index: 9998;
  background: radial-gradient(
    circle at center,
    rgba(255, 59, 0, 0.06) 0%,
    transparent 60%
  );
  mix-blend-mode: screen;
  border-radius: 50%;
}
```

## Fluid Typography (Viewport-Linked)

```css
/* Text that breathes with the viewport */
.installation-title {
  font-size: clamp(3rem, 14vw, 14rem);
  line-height: 0.85;
  letter-spacing: -0.05em;
  font-weight: 700;
}

/* Difference blend — inverts over any background */
.inverted-text {
  color: var(--light);
  mix-blend-mode: difference;
}
```

## Scroll-Velocity Skew

```js
let lastScrollY = window.scrollY;
let velocity = 0;

window.addEventListener('scroll', () => {
  velocity = window.scrollY - lastScrollY;
  lastScrollY = window.scrollY;
  
  document.querySelectorAll('.velocity-skew').forEach(el => {
    el.style.transform = `skewY(${velocity * -0.08}deg)`;
  });
});

// Decay to zero
setInterval(() => {
  velocity *= 0.85;
  document.querySelectorAll('.velocity-skew').forEach(el => {
    el.style.transform = `skewY(${velocity * -0.08}deg)`;
  });
}, 16);
```
