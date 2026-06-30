# AI Security — NCURA Annual Meeting 2026

An HTML-based slide deck for the NCURA Annual Meeting presentation on AI security for research administrators.  
Hosted on GitHub Pages at: **[your-github-pages-url]**

---

## Presentation Sections

| # | Section | Slides |
|---|---------|--------|
| — | Introduction | 1 – Title, 2 – Presenters, 3 – Overview |
| 01 | AI Model Training | 4 – Section divider, 5 – True/False interactive, 6 – What is an AI Model? (graphic), 7 – Neural Networks (graphic), 8 – Inspired by Biology (graphic), 9 – Data to Features (graphic), 10 – Transformers! (graphic), 11 – Training vs. Inference (graphic), 12 – Training process flow, 13 – Raw Data (GPT-3 training data table), 14 – Data Processing (graphic), 15 – Training Loop (graphic), 16 – 3 Stages of LLM Training (graphic), 17 – Models Deployed for Inference (graphic), 18 – Model inversion attack flow, 19 – Response Mining (graphic), 20 – Takeaways |
| 02 | Malicious Attacks | 21 – Section divider, 22 – Resume ranking interactive, 23 – Resume attack reveal, 24 – Prompt anatomy diagram, 25 – Prompt injection examples, 26 – Prompt Injection with Agentic AI (graphic), 27 – Takeaways |
| 03 | Risk Classification | 28 – Section divider, 29 – Shadow AI interactive, 30 – Classify data risk (interactive), 31 – Approved services per tier, 32 – NVIDIA DGX Spark spotlight, 33 – Takeaways |

| — | Conclusion | 34 – Q&A, 35 – Contact information |

**Total:** 35 slides ✓

---

## Navigation

| Input | Action |
|-------|--------|
| `→` / `↓` / `Space` | Next slide |
| `←` / `↑` | Previous slide |
| `Home` / `End` | Jump to first / last slide |
| Swipe left / right | Next / previous (touch devices) |

---


## Layout

Content is positioned inside a safe zone that clears the NCURA logo (top) and NYC skyline graphic (bottom):

| Property | Value |
|----------|-------|
| Safe zone top | 152 px |
| Safe zone bottom | 300 px |
| Slide canvas | 1920 × 1080 px |

Reducing the bottom from the original 395 px to 300 px reclaims ~95 px of usable vertical space while still clearing the tallest skyline peaks (~350 px from bottom).

---

## Customization

**To add or edit slide content**, open `index.html`. Each slide is a `<div class="slide ...">` block. Any element with `data-step` starts hidden and is revealed one at a time with Space/→ before the deck advances to the next slide. Use this for bullet list items (`<li data-step>`) and process-flow nodes.

**Presenter photos** are live on slide 2: `sheneman.jpg` (Luke Sheneman) and `wiggins.jpg` (Nathan Wiggins), rendered as `<img class="photo-circle" style="object-fit:cover;" />`. To swap in a different photo, replace the file in the repo root (or the `src` on the corresponding `.photo-circle` img in `index.html`).

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
