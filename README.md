# areddy30.github.io

Personal site for **Avinash Reddy** — Staff Site Reliability Engineer.

Live at **https://areddy30.github.io**

Plain HTML, CSS, and JavaScript. No build step, no dependencies, no `node_modules`.
Push to `main` and GitHub Pages serves it.

## Structure

```
index.html          Entire page — all content lives here
css/style.css       Design tokens, layout, components, responsive, print
js/main.js          Scroll reveal, metric counters, nav state, mobile menu
assets/
  favicon.svg
  resume.pdf        ← replace with your own PDF
  og-image.png      ← 1200×630 social preview (optional)
robots.txt
sitemap.xml
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

- **Hero headline** — `<h1 class="hero__title">`. The word in `<em>` renders in the accent color.
- **Metrics** — `<span class="metric__fig" data-count="30" data-suffix="+">`. The
  `data-count` value is what the counter animates to; the visible text is the
  fallback for when JavaScript is off. Change both.
- **Case studies** — each `<li class="case">`. Copy one to add a seventh; the
  number in `.case__num` is manual.
- **Colors** — the `:root` block at the top of `css/style.css`. Changing
  `--accent` recolors the whole site.

## Accessibility and behavior notes

- Fully readable with JavaScript disabled — JS only adds motion and nav state.
- All animation is disabled under `prefers-reduced-motion`.
- Skip link, visible focus rings, semantic landmarks, one `h1`, ordered headings.
- `@media print` styles mean the page prints as a clean light-background resume.

## Assets

- `assets/resume.pdf` — a generated two-page resume matching the site content.
  Replace it with your own PDF at the same path if you'd rather use yours.
- `assets/og-image.png` — 1200×630 preview image for LinkedIn and Twitter shares.
  Regenerate it by screenshotting the top of the page at that size.

## Verified

- No horizontal overflow at 500 / 768 / 1440 px.
- All text/background pairs meet WCAG AA (lowest is 3.8:1 on the decorative
  case-study numbers; all body text is 6.3:1 or better).
- Renders correctly with JavaScript disabled.
- All internal anchors resolve; one `h1`; heading order is sequential.
