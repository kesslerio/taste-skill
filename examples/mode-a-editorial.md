# Mode A — Editorial: Implementation Pattern

## When to Use
Content sites, portfolios, blogs, online magazines, brand stories.

## HTML Structure Blueprint

```html
<!-- Editorial Layout: Asymmetric, text-over-image, aggressive whitespace -->
<article class="editorial-layout">
  <!-- Oversized offset headline -->
  <header class="editorial-header">
    <span class="label">Issue № 01 — 2026</span>
    <h1 class="headline reveal-line">
      THE <em>SIGNAL</em><br>
      & THE NOISE
    </h1>
  </header>

  <!-- Image with text overlapping it -->
  <div class="editorial-feature">
    <figure class="feature-image">
      <img src="..." alt="Feature" />
    </figure>
    <div class="feature-caption overlap-text">
      <p class="label">Featured Story</p>
      <h2>What design costs when it stops meaning anything.</h2>
    </div>
  </div>

  <!-- Body with intentional indentation -->
  <div class="editorial-body">
    <p class="body indented">
      The browser was never supposed to be a billboard...
    </p>
  </div>
</article>
```

## CSS Tokens

```css
:root {
  --paper: #F5F0E8;
  --ink: #0D0B08;
  --clash: #BFFF00; /* acid green */
  --font-serif: 'Cormorant Garamond', Georgia, serif;
  --font-sans: 'Space Grotesk', sans-serif;
}

body {
  background: var(--paper);
  color: var(--ink);
  font-family: var(--font-serif);
}

.editorial-header {
  padding: 8vw 5vw 4vw 15vw; /* intentional left offset */
}

.headline {
  font-size: clamp(4rem, 11vw, 9rem);
  line-height: 0.88;
  letter-spacing: -0.04em;
  font-style: normal;
}

.headline em {
  font-style: italic;
  color: var(--clash); /* the one clash color */
}

.editorial-feature {
  position: relative;
  margin: 0 -2rem; /* bleed past container */
}

.feature-image img {
  width: 100%;
  height: 70vh;
  object-fit: cover;
  filter: grayscale(20%);
}

.overlap-text {
  position: absolute;
  bottom: -2rem; /* overlaps the image below */
  left: 5vw;
  background: var(--paper);
  padding: 1.5rem 2rem;
  max-width: 40ch;
}

.editorial-body .indented {
  padding-left: 25%; /* unexpected indent */
  max-width: 60ch;
}

.label {
  font-family: var(--font-sans);
  font-size: 0.6rem;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  opacity: 0.5;
}
```

## Text Reveal Animation

```js
// Stagger reveal on scroll using IntersectionObserver
const lines = document.querySelectorAll('.reveal-line');
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry, i) => {
    if (entry.isIntersecting) {
      setTimeout(() => {
        entry.target.classList.add('revealed');
      }, i * 80);
    }
  });
}, { threshold: 0.1 });

lines.forEach(el => observer.observe(el));
```

```css
.reveal-line {
  clip-path: inset(0 0 100% 0);
  transition: clip-path 0.8s cubic-bezier(0.16, 1, 0.3, 1);
}
.reveal-line.revealed {
  clip-path: inset(0 0 0% 0);
}
```
