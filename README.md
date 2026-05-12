# Frontend Slides (Gemini CLI Edition)

A Gemini CLI skill for creating stunning, animation-rich HTML presentations — from scratch or by converting PowerPoint files.

## What This Does

**Frontend Slides** helps non-designers create beautiful web presentations without knowing CSS or JavaScript. It uses a "show, don't tell" approach: instead of asking you to describe your aesthetic preferences in words, it generates visual previews and lets you pick what you like.

### Key Features

- **Zero Dependencies** — Single HTML files with inline CSS/JS. No npm, no build tools, no frameworks.
- **Visual Style Discovery** — Can't articulate design preferences? No problem. Pick from generated visual previews.
- **PPT Conversion** — Convert existing PowerPoint files to web, preserving all images and content.
- **Anti-AI-Slop** — Curated distinctive styles that avoid generic AI aesthetics.
- **Anti-Gravity Optimized** — Specialized presets and animations for weightless, futuristic presentations.
- **Production Quality** — Accessible, responsive, well-commented code you can customize.

## Installation for Gemini CLI

### Setup in Workspace

Clone this repository into your workspace:

```bash
git clone https://github.com/zarazhangrui/frontend-slides.git .
```

Gemini CLI will automatically detect the `GEMINI.md` and `SKILL.md` files.

### Global Installation (as a Skill)

To use this skill across all your projects, copy the files to your Gemini skills directory:

```bash
mkdir -p ~/.gemini/skills/frontend-slides
cp SKILL.md STYLE_PRESETS.md viewport-base.css html-template.md animation-patterns.md ~/.gemini/skills/frontend-slides/
cp -r scripts ~/.gemini/skills/frontend-slides/
```

Then you can activate it by name: `activate_skill(name="frontend-slides")`.

## Usage

### Create a New Presentation

```
> "I want to create a pitch deck for my AI startup"
```

The skill will:

1. Ask about your content (purpose, length, notes)
2. Ask about the feeling you want (Impressed? Excited? Anti-Gravity?)
3. Generate 3 visual style previews for you to compare
4. Create the full presentation in your chosen style
5. Open it in your browser

### Convert a PowerPoint

```
> "Convert my presentation.pptx to a web slideshow"
```

The skill will:

1. Extract all text, images, and notes from your PPT
2. Show you the extracted content for confirmation
3. Let you pick a visual style (including Anti-Gravity)
4. Generate an HTML presentation with all your original assets

## Included Styles

### Specialized
- **Anti-Gravity** — Weightless, floating, ethereal, futuristic (Google Anti-Gravity edition)

### Dark Themes
- **Bold Signal** — Confident, high-impact, vibrant card on dark
- **Electric Studio** — Clean, professional, split-panel
- **Creative Voltage** — Energetic, retro-modern, electric blue + neon
- **Dark Botanical** — Elegant, sophisticated, warm accents

### Light Themes
- **Notebook Tabs** — Editorial, organized, paper with colorful tabs
- **Pastel Geometry** — Friendly, approachable, vertical pills
- **Split Pastel** — Playful, modern, two-color vertical split
- **Vintage Editorial** — Witty, personality-driven, geometric shapes

## Architecture

This skill uses **progressive disclosure** — the main `SKILL.md` is a concise map, with supporting files loaded on-demand:

| File                      | Purpose                        | Loaded When               |
| ------------------------- | ------------------------------ | ------------------------- |
| `SKILL.md`                | Core workflow and rules        | Always (skill invocation) |
| `STYLE_PRESETS.md`        | 13 curated visual presets      | Phase 2 (style selection) |
| `viewport-base.css`       | Mandatory responsive CSS       | Phase 3 (generation)      |
| `html-template.md`        | HTML structure and JS features | Phase 3 (generation)      |
| `animation-patterns.md`   | CSS/JS animation reference     | Phase 3 (generation)      |
| `scripts/extract-pptx.py` | PPT content extraction         | Phase 4 (conversion)      |

## Sharing Your Presentations

### Deploy to a Live URL
One command deploys your slides to a permanent, shareable URL:
```bash
bash scripts/deploy.sh ./my-deck/
```

### Export to PDF
Convert your slides to a PDF for email or Slack:
```bash
bash scripts/export-pdf.sh ./my-deck/index.html
```

## Requirements

- [Gemini CLI](https://github.com/google/gemini-cli)
- For PPT conversion: Python with `python-pptx` library
- For URL deployment: Node.js + Vercel account
- For PDF export: Node.js (Playwright)

## License
MIT
