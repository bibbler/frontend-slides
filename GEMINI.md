# Frontend Slides (Gemini CLI Edition)

This project provides a specialized skill for Gemini CLI to create stunning, animation-rich HTML presentations. It features a "show, don't tell" workflow where you generate visual previews for the user to choose from.

## Getting Started

1. **Activate the Skill**:
   - The `SKILL.md` file in this directory is already configured for Gemini CLI.
   - You can refer to it as `frontend-slides` once indexed or by pointing directly to this directory.

2. **Core Workflow**:
   - **Phase 0**: Detect if the user wants a new presentation, a PPT conversion, or an enhancement.
   - **Phase 1**: Content discovery (purpose, length, content).
   - **Phase 2**: Style discovery (generate 3 previews based on vibe).
   - **Phase 3**: Generation (using `html-template.md`, `viewport-base.css`, and `animation-patterns.md`).
   - **Phase 4**: PPT Conversion (using `scripts/extract-pptx.py`).
   - **Phase 5**: Delivery (Open in browser, summarize features).
   - **Phase 6**: Share & Export (Vercel deployment or PDF export).

## Anti-Gravity Features

This version has been ported for **Google Anti-Gravity** compatibility, including specialized "weightless" design presets and floating animation patterns.

## Technical Standards

- **Zero Dependencies**: Output is a single HTML file with inline CSS/JS.
- **Viewport Fitting**: Every slide must fit in `100vh`. No scrolling.
- **Responsive**: Use `clamp()`, `min()`, `max()` for all sizing.
- **Anti-AI-Slop**: Avoid generic fonts (Inter/Roboto) and clichéd color schemes.

## Key Files

- `SKILL.md`: The core instruction set for Gemini.
- `STYLE_PRESETS.md`: Curated visual styles (now including Anti-Gravity).
- `viewport-base.css`: Mandatory responsive CSS.
- `html-template.md`: The master template for generation.
- `scripts/extract-pptx.py`: Tool for PowerPoint conversion.
