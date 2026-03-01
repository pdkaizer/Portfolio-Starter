# Portfolio Starter — Claude Code Context

## Project Overview
A hand-crafted HTML + CSS portfolio site built from scratch as a capstone
activity for the Figma-to-Code learning path. No frameworks, no build step
required — just semantic HTML, CSS custom properties, and vanilla JavaScript.

## Architecture

### CSS: Cascade Layers
Layer order is declared in `css/main.css`. **Do not change this order.**

```
@layer reset, tokens, base, components, utilities;
```

- `reset`      — Modern CSS reset, no specificity concerns
- `tokens`     — Design tokens only (custom properties). No selectors other than `:root` and `[data-theme]`
- `base`       — Raw HTML element styles (h1, p, a, img…). No class selectors
- `components` — BEM component classes
- `utilities`  — Single-purpose layout helpers. Always wins over components

### Design Tokens: Three-Tier System (css/layers/tokens.css)
```
Tier 1: Primitive   --color-blue-500: #3b82f6
Tier 2: Semantic    --color-action-primary: var(--color-blue-500)
Tier 3: Component   --btn-bg: var(--color-action-primary)   ← defined in component files
```

**Rule:** Component CSS must only reference semantic tokens or component-level tokens.
Never reference primitives directly from a component.

### Naming: BEM
```
.block {}
.block__element {}
.block--modifier {}
```

Component tokens are scoped to the block selector:
```css
.btn {
  --btn-height: 44px; /* Component token */
}
```

### Theming: data-theme attribute
```html
<html data-theme="light"> or <html data-theme="dark">
```
Theme switching happens by toggling this attribute on `<html>`.
Semantic tokens are redeclared under `[data-theme="dark"]` in tokens.css.

## Conventions

### When adding a new component:
1. Create `css/components/[name].css`
2. Add `@import url("components/[name].css") layer(components);` to `main.css`
3. Define component tokens at the top of the file scoped to the block class
4. Use only semantic tokens and component tokens — never primitives directly

### When adding a new section to index.html:
- Use a semantic element (`<section>`, `<article>`, `<aside>`)
- Add `aria-labelledby` pointing to the section's `<h2>` id
- Use `.container` for max-width + padding
- Use `.section` or `.section--lg` for vertical padding

### File structure
```
portfolio-starter/
├── index.html
├── images/           ← Add your project images here
├── projects/         ← Add individual case study pages here
└── css/
    ├── main.css      ← Entry point — edit layer order here only
    ├── layers/
    │   ├── reset.css
    │   ├── tokens.css  ← Edit design tokens here
    │   ├── base.css
    │   └── utilities.css
    └── components/
        ├── nav.css
        ├── hero.css
        ├── card.css
        ├── button.css
        └── footer.css
```

## What's intentionally NOT here
- No bundler / build step — open index.html directly in a browser
- No JavaScript framework — vanilla JS only
- No utility-first framework (Tailwind etc.)
- No CSS preprocessor (Sass etc.)

## Primary TODOs
Search for `TODO` in index.html for all content placeholders.
The biggest areas to customise:
1. `--font-display` and `--font-body` in tokens.css + the Google Fonts link in index.html
2. Hero heading and subheading copy in index.html
3. Project card content and images
4. About section copy
5. Contact email
6. Colour palette — edit Tier 1 primitives in tokens.css and remap Tier 2 semantic tokens
