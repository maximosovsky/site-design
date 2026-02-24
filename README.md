# Site Design

Universal template and design system for building product landing pages.

## What's inside

| File | Purpose |
|------|---------|
| `template/index.html` | Ready-to-use HTML5 template with dark mode, SEO, favicons |
| `template/style.css` | CSS with variables, responsive layout, all design tokens |
| `template/favicon/` | Manifest + placeholder structure for favicon set |
| `site-design.md` | Complete design principles and rules |
| `llms.txt` | Short LLM-readable project summary |
| `llms-full.txt` | Full LLM instructions — use as system prompt or `.context.md` |

## Quick Start

1. Copy `template/` to your new project
2. Replace "Project Name" in `index.html` and `site.webmanifest`
3. Add your favicon PNGs to `favicon/`
4. Add your hero image as `hero.png`
5. Edit content, push

## Stack

- Pure HTML/CSS/JS — no frameworks, no npm, no build step
- Google Fonts: Lato (body) + Sora (headings)
- Dark mode via CSS variables + `data-theme` attribute
- Single breakpoint: `768px`

## Design Standard

- Palette: `#33334f` / `#6078ff` / `#999`
- Nav links: plain text (not buttons), gray → black on hover
- External links: SVG arrow icons (not Unicode)
- No burger menus — all actions visible
- `flex-shrink: 0` on logos and avatars
- `clamp()` for responsive typography

## License

MIT
