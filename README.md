<div align="center">

# 🎨 Site Design

**Universal template and design system for product landing pages**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)
[![No Build](https://img.shields.io/badge/No_Build-Pure_HTML%2FCSS%2FJS-E34F26?style=for-the-badge)](template/index.html)

Pure HTML/CSS/JS template with dark mode, responsive layout, and zero dependencies.
Built from the [Merge Video](https://github.com/maximosovsky/merge-video) production site.

**No frameworks · No npm · No build step**

</div>

---

## 💡 Concept

A reusable starting point for building landing pages. Instead of reaching for React or Tailwind, start with clean semantic HTML and CSS variables. The template includes everything needed for a polished product page: dark mode, SEO tags, responsive layout, social icons, and Google Fonts.

Extracted from a real production site and codified into a design system with documented tokens, rules, and principles.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Dark mode** | CSS variables + `data-theme` attribute, respects `prefers-color-scheme` |
| **Responsive** | Single breakpoint `768px`, mobile-first layout |
| **SEO ready** | Open Graph, Twitter Card, canonical URL, semantic HTML5 |
| **Design tokens** | Colors, fonts, spacing — all via CSS `var()` |
| **No dependencies** | Zero npm packages, opens directly in browser |
| **Google Fonts** | Lato (body) + Sora (headings) |
| **Social icons** | Gray → brand color on hover with `scale(1.2)` |
| **LLM-friendly** | `llms.txt` and `llms-full.txt` for AI assistants |

---

## 🚀 Quick Start

1. Copy `template/` to your new project
2. Replace "Project Name" in `index.html` and `site.webmanifest`
3. Add your favicon PNGs to `favicon/`
4. Add your hero image as `hero.png`
5. Edit content, push

```bash
cd template && npx -y serve -l 3456
# Open http://localhost:3456
```

---

## 📁 What's Inside

| File | Purpose |
|------|---------|
| `template/index.html` | HTML5 template — header, hero, features, footer |
| `template/style.css` | CSS with variables, responsive layout, design tokens |
| `template/favicon/` | Manifest + placeholder structure for favicon set |
| `site-design.md` | Complete design principles and rules |
| `llms.txt` | Short LLM-readable project summary |
| `llms-full.txt` | Full LLM instructions — system prompt or `.context.md` |

---

## 🎨 Design Standard

| Token | Value |
|-------|-------|
| Primary text | `#33334f` |
| Accent | `#6078ff` |
| Muted | `#999` |
| Font — Body | Lato 400/700 |
| Font — Headings | Sora 700 |
| Breakpoint | `768px` |

See [site-design.md](site-design.md) for the full design system documentation.

---

## 🏗️ Tech Stack

- Pure HTML/CSS/JS — no frameworks, no npm, no build step
- Google Fonts: Lato (body) + Sora (headings)
- Dark mode via CSS variables + `data-theme` attribute
- Single breakpoint: `768px`

---

## 📄 License

MIT © [Maxim Osovsky](https://github.com/maximosovsky)
