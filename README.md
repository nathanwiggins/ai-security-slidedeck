# AI Security — NCURA Annual Meeting 2026

An HTML-based slide deck for the NCURA Annual Meeting presentation on AI security for research administrators.  
Hosted on GitHub Pages at: **[your-github-pages-url]**

---

## Presentation Sections

| # | Section | Slides |
|---|---------|--------|
| 01 | Introduction | AI basics, use cases in research administration, audience poll |
| 02 | Model Training | How LLMs learn, training data risks, guidance for administrators |
| 03 | Prompt Injection | Attack types, real-world scenarios, audience poll |
| 04 | Risk Classification | NIST/OWASP frameworks, data sensitivity table, mitigation strategies, audience poll |
| 05 | Q&A | Key takeaways, thank-you slide |

**Total:** 24 slides

---

## Navigation

| Input | Action |
|-------|--------|
| `→` / `↓` / `Space` | Next slide (or reveal next bullet point) |
| `←` / `↑` | Previous slide |
| `Home` / `End` | Jump to first / last slide |
| Click agenda items | Jump to that section |
| Section dots (right edge) | Jump to section start |
| Swipe left / right | Next / previous (touch devices) |

Bullet points on content slides reveal one at a time with `Space` or `→` before the slide advances.

---

## Interactive Polls

Three audience poll slides are included (slides 6, 15, and 21). Each poll tallies clicks in real time on the presenter's display. For live audience participation from participant devices, link each poll slide to an external service:

- [Mentimeter](https://www.mentimeter.com) — recommended for live word clouds and ranked polls
- [Poll Everywhere](https://www.polleverywhere.com) — integrates well with presenter displays
- [Slido](https://www.slido.com) — good for Q&A queues alongside polls

Add a QR code image to the poll slides by placing a PNG in the repo and referencing it in `index.html`.

---

## Customization

**To add or edit slide content**, open `index.html`. Each slide is a `<div class="slide ...">` block. Bullet lists with `data-reveal` on the `<ul>` element will reveal one item at a time during the presentation.

**To update presenter information**, search for `[Presenter Name]`, `[Email Address]`, `[Institution]`, and `[Your GitHub Pages URL]` in `index.html` and replace with real values.

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
