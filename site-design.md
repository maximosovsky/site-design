# Site Design — Design System & Development Guidelines

> Universal template and principles for building product landing pages.
> Pure HTML/CSS/JS. Backend-agnostic. Mobile-first.

## Branding Standard

| Token              | Value                         |
|---------------------|-------------------------------|
| Font — Body         | Lato 400/700                  |
| Font — Headings     | Sora 700                      |
| Font — Buttons      | System stack (-apple-system…)  |
| Primary text        | `#33334f`                     |
| Secondary text      | `#767ead`                     |
| Muted text          | `#999`                        |
| Accent              | `#6078ff`                     |
| Badge               | green icon `#2a9d5c` on `#eef0ff` |
| Error               | `#c00` on `#fff0f0`           |
| Success             | `#080` on `#f0fff4`           |

## Architecture Principles

### 1. No frameworks
- Pure HTML/CSS/JS — no React, no Tailwind, no npm
- Single `style.css` + single `index.html`
- Zero external dependencies except Google Fonts

### 2. Backend-agnostic
- Template works with any backend (FastAPI, Express, nginx, static hosting)
- No build step required — open `index.html` directly

### 3. CSS Variables for theming
- All colors via `var(--token)` in `:root` and `[data-theme="dark"]`
- Dark mode via `data-theme` attribute on `<html>`
- Respects `prefers-color-scheme` by default

## Layout Principles

### Header
- **Desktop**: Logo (left) + nav links (right) + theme toggle
- **Mobile**: Logo + theme toggle (nav links hidden, CTAs move to hero)
- Nav links are **plain text** — gray `#999`, black on hover, `font-weight: 400`, no borders
- Logo text scales with `clamp(16px, 5vw, 24px)` — never wraps (`white-space: nowrap`)
- No burger menu — all actions directly visible or in hero

### Hero
- **Desktop**: Text left + image right, two-column flex
- **Mobile**: Text only, image hidden, CTA buttons visible
- Badge (pill shape, `border-radius: 20px`) — hidden on mobile
- Subtitle: max 2 sentences

### Features
- **Desktop**: 3 cards in a row, icon on top, centered text
- **Mobile**: Vertical stack, horizontal layout (icon left + text right), titles hidden, `gap: 14px`

### Footer
- **Desktop**: Text + social icons in row
- **Mobile**: Stacked, centered
- All text gray `#999`, links turn `#6078ff` on hover

## Visual Design Principles

### External link arrows
- Use **SVG arrows** (not Unicode ↗) for cross-platform consistency
- Thin lines, inherits `currentColor` from parent
- Example: `<svg width="14" height="14" viewBox="0 0 24 24" ...>`

### Social icons
- Gray `#999` by default → **brand color on hover** with `scale(1.2)`
- Telegram: `#0088cc`, YouTube: `#FF0000`, Instagram: `#E4405F`
- X: `#000`, GitHub: `#333`, LinkedIn: `#0A66C2`, DEV.to: `#000`

### Avatars (if auth present)
- **Rainbow Google border on hover** — 4-color `box-shadow` (#34A853, #EA4335, #4285F4, #FBBC05)
- `flex-shrink: 0` — **never compresses**
- Dropdown: lavender bg `#eef0ff`, purple-tinted shadow
- Sign Out: red `#ff6b6b` → `#ff4444` on hover
- Tooltip: black bg `#222`, hidden when dropdown is open

### Buttons & CTAs
- Outline style: `box-shadow: inset 0 0 0 1px`
- Primary: black bg on light, accent bg on dark
- All hover effects: `transition: 0.2s`
- Gradient merge button: `linear-gradient(135deg, #7c3aed, #6366f1, #818cf8)` with glow animation

### Toggle switches
- Custom: gray `#ccc` → purple `#6366f1` on checked
- White circle with shadow, smooth `translateX(18px)`

### Inputs
- Border: `2px solid #e2e4ef` → `#6078ff` on focus
- `border-radius: 8px`

## Responsive Principles

### Breakpoint
- Single breakpoint: `768px` for all mobile rules

### Sizing
- Logo: 51px desktop / 64px mobile
- Avatar: 37px desktop / 56px mobile
- `flex-shrink: 0` on elements that must not compress (avatars, logos)
- `clamp()` for smooth scaling instead of breakpoint jumps

### Tooltip positioning on mobile
- `right: -3px; left: auto; transform: none` — right-aligned to screen edge
- `top` value large enough to not cover the trigger element

## Animation Principles

| Element           | Duration | Easing          | Effect                     |
|-------------------|----------|-----------------|----------------------------|
| Buttons, links    | 0.2s     | ease            | Color, shadow, scale       |
| Modal             | 0.25s    | ease            | slideY(30px) + fade        |
| Merge button glow | 1.5s     | ease-in-out     | Infinite box-shadow pulse  |
| Social icons      | 0.25s    | ease            | scale(1.2) + color         |
| File scan pulse   | 1.5s     | infinite        | opacity 1→0.4              |
| Theme transition  | 0.3s     | —               | background + color         |

## SEO Checklist

Every page must have:
- `<title>` — descriptive, unique
- `<meta name="description">` — 1-2 sentences
- `<meta property="og:*">` — title, description, image, url
- `<meta name="twitter:*">` — card, title, description, image
- `<link rel="canonical">` — self-referencing
- Single `<h1>` per page
- Semantic HTML5 (`<header>`, `<section>`, `<footer>`)

## Favicon Checklist

- `favicon-16.png` (16×16)
- `favicon-32.png` (32×32)
- `apple-touch-icon.png` (180×180)
- `site.webmanifest` with icon references

## File Structure

```
project/
├── index.html          # Single page
├── style.css           # All styles
├── favicon/
│   ├── favicon-16.png
│   ├── favicon-32.png
│   ├── apple-touch-icon.png
│   └── site.webmanifest
├── hero.png            # Hero section image
└── llms.txt            # LLM-readable project summary
```
