# Mike Ilan — Marketing Creative · Portfolio

A single-page, production-grade portfolio site presenting a curated body of work
Mike Ilan produced for **B&G Guitars**, a boutique high-end guitar brand. Built to
help him land a **full-time role** — a candidate presenting his work to hiring
managers, not a freelance services page.

The design echoes the B&G house style: warm near-black backgrounds, figured-wood
accents (tobacco/honey burst, brass, champagne), a geometric sans that nods to
B&G's Futura, and one restrained editorial serif for display moments.

- **Stack:** plain HTML / CSS / vanilla JS. No framework, no build step.
- **Fonts & images:** all self-hosted — the site works fully offline.
- **Accessibility:** semantic landmarks, skip link, visible focus, WCAG-minded
  contrast, descriptive `alt` text, `prefers-reduced-motion` support.
- **Performance:** two variable-font files, lazy-loaded images with explicit
  dimensions (no layout shift), tiny JS.

---

## Run locally

It's a static site — any static server works. From this folder:

```bash
# Option A — Python (already on most machines)
python -m http.server 8080
# then open http://localhost:8080

# Option B — Node
npx serve .
```

> Opening `index.html` directly with `file://` mostly works, but a local server is
> recommended so fonts and the structured-data script load exactly as in production.

---

## Deploy to Netlify (zero config)

Three equally simple options:

1. **Drag & drop** — go to <https://app.netlify.com/drop> and drop this whole
   folder. Done. `netlify.toml` sets the publish directory and caching headers.
2. **Git** — push this folder to a repo and "Import from Git" in Netlify. No build
   command; publish directory is `.`.
3. **CLI** — `npm i -g netlify-cli` then `netlify deploy --prod --dir .`

After deploy, set the real URL in the `og:image` meta tag (see TODO below) so link
previews render the Step Sister image.

---

## Where to swap things

### Thumbnails
All live in `assets/thumbs/` and are referenced locally (nothing hotlinks). To
replace one, drop a new file with the **same name** (or update the `src` + the
`width`/`height` attributes in `index.html`):

| File | Card | Aspect |
| --- | --- | --- |
| `stepsister.png` | Flagship guitar (transparent PNG) | 387×1200 |
| `ig-stepsister-ad.jpg` | Flagship "hero ad" reel inset | 360×640 |
| `helena.png` | Helena HyperShift (transparent PNG) | 387×1200 |
| `yt-scorpions.jpg` | Scorpions × Alberto Lombardi | 1280×720 |
| `yt-davidlevi.jpg` | David Levi acoustic lesson | 1280×720 |
| `ig-highlight.jpg` | Influencer highlight reel | 640×360 |
| `yt-review.jpg` | 586K-subscriber review | 1280×720 |

YouTube stills come from `https://img.youtube.com/vi/<ID>/maxresdefault.jpg`.
The B&G product images and both Instagram stills were pulled from each page's
`og:image` and saved locally.

### Textures & fonts
- `assets/textures/` — procedurally generated wood-grain (regenerate with
  `scratchpad/gen_textures.py` if you ever want a different figure).
- `assets/fonts/` — self-hosted **Jost** (Futura-alike sans, variable) and
  **DM Serif Display** (high-contrast editorial serif for titles), as `.woff2`.

### Copy
All copy lives directly in `index.html`, grouped by section with comments.

---

## ✅ TODO before going live

Search `index.html` for `TODO` — each is inline where it's used.

- [x] **LinkedIn** — wired to `https://www.linkedin.com/in/mikeilan` (Contact + footer).
- [x] **Résumé** — `assets/mike-ilan-resume.pdf` is in place and linked (Contact + footer).
- [ ] **Name spelling** — confirm "Mike Ilan" is correct everywhere.
- [ ] **Contact email** — currently `mikeilan207@gmail.com`. Confirm this is the
      address you want public (used in the mailto link, footer, and structured data).
- [ ] **Instagram (optional)** — no personal handle was provided, so the placeholder
      button was removed to avoid a dead link. Add one back where the `TODO (optional)`
      comment sits in the Contact section once you have the URL.
- [ ] **Portrait (optional)** — an About-section portrait slot is commented in
      `index.html`; add `assets/portrait.jpg` and uncomment if you'd like a photo.
- [ ] **`og:image` URL** — once you have the final domain, set the absolute URL in
      the `og:image` meta tag for correct social link previews.

---

## Structure

```
mike-ilan-portfolio/
├── index.html          # all markup + copy
├── styles.css          # design system + components
├── main.js             # nav, mobile menu, scroll reveals, scroll-spy
├── netlify.toml         # zero-config deploy + caching/security headers
├── README.md
└── assets/
    ├── favicon.svg
    ├── mike-ilan-resume.pdf   # linked from Contact + footer
    ├── fonts/          # self-hosted Jost + Fraunces (woff2)
    ├── textures/       # wood-grain + film-grain motifs (JPEG)
    └── thumbs/         # work thumbnails (all local)
```

---

*Selected work produced for B&G Guitars. Product images and video stills remain ©
B&G Guitars and the respective creators, shown here for portfolio purposes.*
