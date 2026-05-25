# AI Security — NCURA Annual Meeting 2026

An HTML-based slide deck for the NCURA Annual Meeting presentation on AI security for research administrators.  
Hosted on GitHub Pages at: **[your-github-pages-url]**

---

## Presentation Sections

| # | Section | Slides |
|---|---------|--------|
| — | Introduction | 1 – Title, 2 – Presenters, 3 – Overview |
| 01 | AI Model Training | 4 – Section divider, 5 – True/False interactive, 6 – Training process flow, 7 – Model inversion attack flow, 8 – Takeaways |
| 02 | Malicious Attacks | 9 – Section divider, 10 – Resume ranking interactive, 11 – Resume attack reveal, 12 – Prompt anatomy diagram, 13 – Prompt injection examples, 14 – Takeaways |
| 03 | Risk Classification | *(coming soon)* |

**Total:** 14 slides (in progress)

---

## Navigation

| Input | Action |
|-------|--------|
| `→` / `↓` / `Space` | Next slide |
| `←` / `↑` | Previous slide |
| `Home` / `End` | Jump to first / last slide |
| Swipe left / right | Next / previous (touch devices) |

---


## Customization

**To add or edit slide content**, open `index.html`. Each slide is a `<div class="slide ...">` block. Any element with `data-step` starts hidden and is revealed one at a time with Space/→ before the deck advances to the next slide. Use this for bullet list items (`<li data-step>`) and process-flow nodes.

**To swap in real presenter photos**, find the `.photo-circle` div for each presenter in `index.html` and replace it with `<img src="your-photo.jpg" class="photo-circle" style="object-fit:cover;" />`.

**Fonts:** Arial throughout. No external font dependencies.

**Images:** Both background PNGs (`Title Slide.png`, `Slide Template.png`) are referenced from the repository root.

---

## GitHub Pages Setup

1. Go to **Settings → Pages** in this repository.
2. Set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
3. Save — the site will publish at `https://<username>.github.io/<repo-name>/`.

---

## License

Presentation content © 2026 [Presenter Name] / NCURA. All rights reserved.
