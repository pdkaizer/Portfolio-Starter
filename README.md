# Portfolio Starter
### Capstone Activity — [From Figma to Code](https://designercodelearning.com)

A starter kit for building your portfolio from scratch using semantic HTML and modern CSS. No frameworks, no build tools, no package.json. Open the file, start editing.

---

## What's inside

```
portfolio-starter/
├── index.html              ← Your main page — start here
├── images/                 ← Add your project images here
├── projects/               ← Add case study pages here (optional)
├── CLAUDE.md               ← Context file for Claude Code
└── css/
    ├── main.css            ← CSS entry point, imports everything
    ├── layers/
    │   ├── reset.css       ← Modern CSS reset (don't edit)
    │   ├── tokens.css      ← Your design tokens ← EDIT THIS
    │   ├── base.css        ← Element defaults
    │   └── utilities.css   ← Layout helpers (.container, .grid, .stack…)
    └── components/
        ├── nav.css         ← Navigation bar
        ├── hero.css        ← Hero section
        ├── card.css        ← Project cards
        ├── button.css      ← Button variants
        └── footer.css      ← Footer
```

## Getting started

**1. Open the project**

No installation needed. Just open `index.html` in your browser. For the best development experience, use [VS Code](https://code.visualstudio.com) with the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension — it refreshes the browser every time you save a file.

**2. Start with your tokens**

Open `css/layers/tokens.css`. This is your Figma Variables translated into CSS. The first things to change are your colours and fonts:

```css
/* In :root — Tier 1 primitives */
--color-blue-500: #3b82f6;  /* ← Replace with your brand colour */

/* In :root — Tier 2 semantic */
--color-action-primary: var(--color-blue-500);  /* ← Maps brand colour to usage */
```

And your fonts:
```css
--font-display: Georgia, serif;      /* ← Your heading font */
--font-body:    system-ui, sans-serif; /* ← Your body font */
```

Don't forget to update the Google Fonts link in `index.html` too.

**3. Search for TODO**

Every content placeholder in `index.html` is marked with `TODO:`. Use your editor's find feature to locate and replace them all:

- Your name
- Your role / location
- Hero heading and subheading
- Project content (title, description, image, link)
- About section copy
- Contact email

**4. Add your images**

Drop your project images into the `images/` folder, then update the `src` attributes on each `<img>` in index.html.

Images work best at a 16:9 ratio (e.g. 1200×675px). Keep file sizes under 500KB — use [Squoosh](https://squoosh.app) to compress them.

**5. Customise the CSS**

Each component file has a `Component tokens` block at the top — this is where you make most visual changes without touching the component's structural code:

```css
/* In card.css */
.card {
  --card-radius:    var(--radius-lg);   /* ← Change this */
  --card-padding:   var(--space-6);     /* ← Change this */
  --card-img-ratio: 56.25%;             /* ← 16:9. Try 75% for 4:3 */
}
```

---

## Concepts to practise

As you build, look for opportunities to apply each phase of the learning path:

| Concept | Where to try it |
|---|---|
| Semantic HTML | Every element in index.html has a comment explaining the choice |
| CSS Custom Properties | tokens.css — edit and extend the token system |
| Flexbox & Grid | utilities.css — `.grid`, `.cluster` classes |
| Container Queries | card.css — the card switches layout at 480px container width |
| BEM naming | Every component — Block, Element, Modifier |
| Cascade Layers | main.css — the `@layer` declaration order |
| Light / Dark theming | tokens.css — `[data-theme="dark"]` block |
| Pseudo-classes | button.css — `:hover`, `:focus-visible`, `:disabled` |
| Fluid typography | tokens.css — `--text-*` tokens use `clamp()` |
| Accessibility | index.html — `aria-*` attributes, `role`, `:focus-visible` |

---

## Deploying your portfolio

When you're ready to share it:

- **[Netlify Drop](https://app.netlify.com/drop)** — Drag your folder onto the page. Instant live URL, no account needed.
- **[GitHub Pages](https://pages.github.com)** — Push to a repo named `yourname.github.io`. Free, version-controlled.
- **[Vercel](https://vercel.com)** — Connect your GitHub repo. Automatic deploys on every push.

---

## Going further

Once the basics are in place:

- **Add a case study page** — Duplicate `index.html` into `projects/your-project.html`. The nav, tokens, and components all work the same.
- **Add a tag component** — Create `css/components/tag.css` and add the import to `main.css`. Practice the full BEM + component token pattern.
- **Try `@property`** — Register a custom property with a type and animate it. The button hover is a good place to try this.
- **Add a scroll-driven animation** — Use `animation-timeline: scroll()` to animate the hero content as the page scrolls.
- **Connect to Figma** — Export your Figma Variables as JSON, run them through [Style Dictionary](https://amzn.github.io/style-dictionary), and replace your `tokens.css` with the generated output.

---

Built for the [*From Figma to Fluent Code* learning path](https://designercodelearning.com).
