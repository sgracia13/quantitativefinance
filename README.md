# The Quantitative Finance Book — Skeleton

A single-file HTML book template. Dark theme, sidebar navigation, mobile responsive.

## Quick Start

1. Open `quant-finance-book.html` in a browser
2. Edit the `bookStructure` object in the `<script>` section to add your content

## Structure

Everything lives in one HTML file. The book is defined as a JavaScript object:

```javascript
const bookStructure = {
    title: "The Quantitative Finance Book",
    subtitle: "From Foundations to Practice",
    pages: [
        {
            id: "intro",           // URL hash (e.g., #intro)
            title: "Introduction", // Display name
            chapter: null,         // Chapter number (null for intro)
            content: `<h1>...</h1><p>...</p>`  // HTML content
        },
        {
            id: "1",
            title: "Chapter Title",
            chapter: "1",
            part: "Part I: Section Title",  // Starts a new sidebar section
            content: `...`
        },
        {
            id: "1.1",
            title: "Subsection",
            chapter: "1.1",        // Dot notation = subsection styling
            content: `...`
        },
        // ...
    ]
};
```

## Adding Content

### New Chapter

```javascript
{
    id: "4",
    title: "Options Pricing",
    chapter: "4",
    part: "Part II: Derivatives",  // Optional: starts new section
    content: `
        <div class="chapter-header">Chapter 4</div>
        <h1>Options Pricing</h1>
        <p>Your content here...</p>
    `
}
```

### New Subsection

```javascript
{
    id: "4.1",
    title: "Black-Scholes Model",
    chapter: "4.1",
    content: `
        <div class="chapter-header">Chapter 4.1</div>
        <h1>Black-Scholes Model</h1>
        <p>Your content here...</p>
    `
}
```

## Content Components

### Code Block

```html
<pre><code>import numpy as np

def black_scholes(S, K, T, r, sigma):
    # Implementation here
    pass</code></pre>
```

### Math Block

```html
<div class="math-block">
    C = S₀N(d₁) - Ke^(-rT)N(d₂)
</div>
```

### Callout Box

```html
<div class="callout">
    <div class="callout-title">Note</div>
    <p>Important information here.</p>
</div>
```

Variants: Add class `warning` or `tip` for different colors.

```html
<div class="callout warning">
    <div class="callout-title">Warning</div>
    <p>Be careful about...</p>
</div>

<div class="callout tip">
    <div class="callout-title">Tip</div>
    <p>Pro tip...</p>
</div>
```

### Inline Code

```html
<p>Use the <code>numpy</code> library for numerical operations.</p>
```

## Navigation

Built-in features:

- **Sidebar** — Click any chapter/subsection
- **Prev/Next buttons** — Bottom of each page
- **Keyboard** — ← → arrow keys
- **URL hashes** — Bookmarkable (e.g., `book.html#4.1`)
- **Browser history** — Back/forward buttons work
- **Mobile** — Hamburger menu with overlay

## Customization

### Change Colors

Edit CSS variables at the top of `<style>`:

```css
:root {
    --bg-primary: #0f1419;
    --accent: #58a6ff;
    /* ... */
}
```

### Change Fonts

Replace the Google Fonts import and update font-family references.

### Add Real Math Rendering

Add MathJax or KaTeX:

```html
<script src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
```

Then render equations in your content.

## File Structure

```
quant-finance-book.html    # Everything in one file
README.md                  # This file
```

## License

Do whatever you want with it.
