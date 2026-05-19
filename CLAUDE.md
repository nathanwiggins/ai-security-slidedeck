# CLAUDE.md

## Project Overview
Single-file HTML slide deck for an AI security presentation at the NCURA Annual Meeting 2026. All slide content, styles, and JavaScript live in `index.html`. Background images (`Title_Slide.png`, `Slide_Template.png`) are in the repo root.

## Key Facts
- **Slide size:** 1920×1080px, scaled to fit viewport via `position: fixed` + `translate(-50%, -50%) scale(s)` in JS
- **24 slides** across 5 sections; section nav uses `data-section` attributes
- **Bullet reveals:** `<ul data-reveal>` lists reveal one `<li>` at a time on Space/→ before advancing
- **Polls:** Client-side only (no backend); clicks accumulate in `pollData` in memory
- **Fonts:** Arial only — no external dependencies
- **Hosting:** GitHub Pages from `main` branch root

## Rules
- The content for this presentation is specified in `slides.md`. Update `index.html` based on the content specified there.
- **Update `README.md` whenever `index.html` is edited** to keep documentation in sync with slide content, navigation, or structural changes.
- If changes are made directly to `index.html`, also update `slides.md` so that it stays consistent with the presentation outline.
- Do not introduce external font or script dependencies without explicit instruction.
- Preserve the 16:9 (1920×1080) coordinate system for all layout values.
