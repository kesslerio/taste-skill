# Mode B — Precision Instrument: Implementation Pattern

## When to Use
Dashboards, developer tools, data products, financial UIs, productivity apps.

## Visual Language: Blueprint Rules

```css
:root {
  --dust: #F4F1EC;
  --graphite: #2A2A2A;
  --rust: #D4603A;
  --sage: #7A8C6E;
  --mono: 'JetBrains Mono', 'IBM Plex Mono', monospace;
  --rule: 1px solid var(--graphite);
}

body {
  background: var(--dust);
  color: var(--graphite);
  font-family: var(--mono);
}

/* Blueprint grid lines */
.instrument-grid {
  display: grid;
  grid-template-columns: 1fr 3fr 1fr;
  border-left: var(--rule);
}

.instrument-cell {
  border-right: var(--rule);
  border-bottom: var(--rule);
  padding: 1.5rem;
  position: relative;
}

/* Coordinate labels — decorative but informative */
.instrument-cell::before {
  content: attr(data-coord);
  position: absolute;
  top: 0.4rem;
  right: 0.5rem;
  font-size: 0.5rem;
  opacity: 0.3;
  letter-spacing: 0.1em;
}
```

## Slot Machine Number Animation

```js
// Animate a number change with slot-machine shuffle
function shuffleNumber(el, target, duration = 600) {
  const start = parseInt(el.textContent) || 0;
  const steps = 12;
  const interval = duration / steps;
  let step = 0;

  const timer = setInterval(() => {
    step++;
    if (step < steps) {
      // Show random intermediate value
      el.textContent = Math.round(
        start + (target - start) * (step / steps) + 
        (Math.random() - 0.5) * 20
      ).toLocaleString();
    } else {
      el.textContent = target.toLocaleString();
      clearInterval(timer);
    }
  }, interval);
}
```

## HTML Blueprint

```html
<section class="instrument-panel" data-coord="A1-D4">
  <header class="panel-header">
    <span class="coord-label">SYS.MONITOR</span>
    <span class="timestamp">22:40:45 UTC+1</span>
  </header>

  <div class="metric-row">
    <label class="mono-label">THROUGHPUT</label>
    <span class="metric-value" data-target="84293">84,293</span>
    <span class="metric-unit">req/s</span>
    <div class="spark-line" aria-hidden="true">
      <!-- SVG sparkline, not a chart.js plugin -->
      <svg viewBox="0 0 100 30" preserveAspectRatio="none">
        <polyline points="0,28 20,15 40,22 60,8 80,18 100,5" 
                  fill="none" stroke="currentColor" stroke-width="1.5"/>
      </svg>
    </div>
  </div>
</section>
```

## Toggle Snap Behavior

```css
/* Snap, never slide */
.toggle-switch {
  position: relative;
  width: 3rem; height: 1.5rem;
  border: var(--rule);
  cursor: pointer;
  transition: none; /* intentional: no animation on toggle */
}
.toggle-switch::after {
  content: '';
  position: absolute;
  left: 2px; top: 2px;
  width: calc(50% - 4px); height: calc(100% - 4px);
  background: var(--graphite);
  transition: transform 0ms step-end; /* instant snap */
}
.toggle-switch.active::after { transform: translateX(100%); }
```
