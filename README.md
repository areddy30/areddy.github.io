# areddy30.github.io

Personal site for **Avinash Reddy** — Staff Site Reliability Engineer.

Live at **https://areddy30.github.io**

Plain HTML, CSS, and JavaScript. No build step, no dependencies, no `node_modules`.
Push to `main` and GitHub Pages serves it.

## Structure

```
index.html          Home page: hero, metrics, work cards, experience, skills, contact
work/*.html         One page per project (the "Read the project" cards link here)
css/style.css       Design tokens, layout, components, responsive, print
js/main.js          Scroll reveal, metric counters, nav state, mobile menu
assets/
  favicon.svg
  resume.pdf        replace with your own PDF if you prefer
  og-image.png      1200×630 social preview
robots.txt
sitemap.xml         lists the home page and all six project pages
```

## Deploying

The repo name must be **exactly** `areddy30.github.io` (username + `.github.io`)
for the site to serve at the root domain. Any other name makes it a *project*
site at `areddy30.github.io/<repo-name>/`.

```bash
git add .
git commit -m "Build portfolio site"
git push origin main
```

Then in the repo: **Settings → Pages → Source: Deploy from a branch → `main` / `root`**.
First deploy takes about a minute.

## Editing content

Everything is in `index.html` as plain semantic HTML — find the text and change it.

- **Hero headline** — `<h1 class="hero__title">`. The phrase in `<em>` renders in the accent color.
- **Metrics** — `<span class="metric__fig" data-count="30" data-suffix="+">`. The
  `data-count` value is what the counter animates to; the visible text is the
  fallback for when JavaScript is off. Change both. `data-prefix` (e.g. `~$`) and
  `data-decimals` (e.g. `1`) are optional, for figures like `~$1.5M`.
- **Work cards** — the `<ul class="cards">` in `index.html`. Each `<li>` is one card
  (label, title, two-line description) linking to a page in `work/`.
- **Project pages** — `work/<name>.html`. This is where longer details go: the three
  highlight tiles at the top (`.hl`), then Problem / Approach / Impact, then tech tags.
  To add a seventh project, copy one page, edit it, and add a card to `index.html`.
- **Colors** — the `:root` block at the top of `css/style.css`. Changing `--accent`
  recolors the whole site (currently teal `#5EEAD4`).

## Accessibility and behavior notes

- Fully readable with JavaScript disabled — JS only adds motion and nav state.
- All animation is disabled under `prefers-reduced-motion`.
- Skip link, visible focus rings, semantic landmarks, one `h1`, ordered headings.
- `@media print` styles mean the page prints as a clean light-background resume.

## Assets

- `assets/resume.pdf` — a generated two-page resume matching the site content.
  Replace it with your own PDF at the same path if you'd rather use yours.
- `assets/og-image.png` — 1200×630 preview image for LinkedIn and Twitter shares.
  Regenerate it by screenshotting the top of the home page at that size.

## Verified

- No horizontal overflow at 500 / 768 / 1440 px.
- All text/background pairs meet WCAG AA (lowest is 5.6:1, secondary text on a
  hovered card; body text is 9:1 or better).
- Renders correctly with JavaScript disabled.
- All internal links and anchors resolve across all 7 pages; one `h1` per page.
- No horizontal overflow at 360 / 390 / 430 px (tested in true-width viewports).
