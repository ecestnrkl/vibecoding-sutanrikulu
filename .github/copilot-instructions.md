# VibeCoding Academic Portfolio - AI Agent Instructions

## Project Overview
This is a customized Academic Pages Jekyll site for Ece Sutanrikulu's portfolio. The project transforms the standard academic template into a minimal, creative, editorial webprofile focused on three core deliverables: a hero landing page, an accessible tri-modal CV (text/visual/audio), and one deep-dive interactive UX portfolio project page.

**Critical Constraint**: Do NOT introduce new frameworks or JavaScript libraries. Work only within Jekyll's Liquid templates, Markdown, CSS, and the existing npm dependencies (jQuery, FitVids, Plotly).

## Architecture & Structure

### Jekyll Collections System
Content is organized in five collections (defined in `_config.yml`):
- `_publications/`: Academic papers (front matter: `title`, `authors`, `venue`, `paperurl`, `citation`)
- `_talks/`: Conference presentations (front matter: `title`, `type`, `venue`, `date`, `location`)
- `_teaching/`: Courses taught
- `_portfolio/`: Project case studies (use this for the interactive UX portfolio page)
- `_posts/`: Blog entries

Each collection uses `permalink: /:collection/:path/` and outputs individual pages.

### Layout Hierarchy
1. `_layouts/default.html` - Base template with masthead, footer, scripts
2. `_layouts/single.html` - Individual content pages (publications, talks, portfolio items)
3. `_layouts/archive.html` - Collection listing pages
4. `_includes/` - Reusable components (`masthead.html`, `footer.html`, `author-profile.html`, etc.)

The layout uses `compress.html` to minify output. Page content flows: `{% include masthead.html %}` → `{{ content }}` → `{% include footer.html %}`.

### Theme System
- Primary: `_sass/` directory with theme variables in `_themes.scss`
- Current implementation: `site_theme` in `_config.yml` supports "default" and "air" themes
- **PRD Requirement**: Add custom theme switcher (light/dark/custom) via icon hover - implement in CSS only, no new JS

### Data & Navigation
- `_data/navigation.yml`: Controls header navigation order/visibility
- `_data/cv.json`: Structured CV data for JSON-based CV rendering (optional alternative to Markdown CV)
- `_data/ui-text.yml`: Localized UI strings

## Development Workflows

### Local Development
```bash
# Standard Ruby setup
bundle install
bundle exec jekyll serve -l -H localhost
```
View at `localhost:4000`. Changes to Markdown/HTML auto-rebuild; `_config.yml` changes require server restart.

### Docker Development (Preferred for Cross-Platform)
```bash
chmod -R 777 .
docker compose up
```
Uses `_config_docker.yml` overlay for Docker-specific settings. Watch mode enabled.

### VS Code DevContainer
Press F1 → "DevContainer: Reopen in Container". Auto-hosts at `localhost:4000` with live reload.

### Asset Pipeline
```bash
npm run build:js    # Minifies all JS to assets/js/main.min.js
npm run watch:js    # Auto-rebuild on JS changes
```
Concatenates: jQuery → FitVids → smooth-scroll → Plotly → greedy-navigation → `_main.js` into `main.min.js`.

## Project-Specific Patterns (from PRD.md)

### 1. Tri-Modal CV Implementation
The CV must be consumable three ways (Module C in PRD):
- **Text**: Standard Markdown in `_pages/cv.md`
- **Visual**: Timeline/infographic (implement using CSS Grid/Flexbox, no external libraries)
- **Audio**: Audio player + transcript (use native HTML5 `<audio>` element)
- Add mode switcher using CSS-only tabs or radio buttons + labels pattern
- Include PDF download link to file in `/files/` directory

### 2. Interactive Portfolio Project Page (Module D)
Create in `_portfolio/` collection with required front matter:
```yaml
---
layout: single
title: "Project Title"
authors: "Author Names"
institution: "Organization"
problem: "Problem statement"
method: "Approach description"
outcomes: "Measurable results"
excerpt: "Short description for listing pages"
---
```
Must include:
- Picture/video/animation (optimize images, place in `/images/`)
- PDF report download link
- At least one accessible interactive element (use `<details>`/`<summary>` for progressive disclosure, or CSS-only flip cards with `:focus-visible` support)

### 3. Hero Landing Page (Module B)
Customize `_pages/about.md` or create custom layout:
- Above-the-fold: name, positioning line, short intro, hero image
- Primary CTAs: About, CV, Project, Contact
- Credibility strip (publications count, GitHub stars, etc.)
- Implement in existing `splash.html` or `single.html` layout with custom CSS

### 4. Custom Theme System (Module A)
Design tokens to define in `_sass/_themes.scss`:
- Color variables (primary, secondary, background, text)
- Type scale (h1-h6, body, small)
- Spacing scale (using CSS custom properties)
- Component styles (buttons, cards, metadata rows)

Theme switcher must:
- Show on icon hover (CSS `:hover` + positioned dropdown)
- Offer 3 options: light, dark, custom
- Use `localStorage` + existing JS patterns in `_main.js` (minimal addition)
- Respect `prefers-color-scheme` media query

## Content Generation Tools

### Markdown Generator Scripts
Located in `markdown_generator/`:
- `publications.py` + `publications.tsv` → generates `_publications/*.md`
- `talks.py` + `talks.tsv` → generates `_talks/*.md`
- Jupyter notebooks (`.ipynb`) provide documented versions of Python scripts

When adding bulk content, edit TSV files and run Python scripts rather than manually creating Markdown files.

### Talkmap Feature
- `talkmap.py` generates interactive map of talk locations
- Outputs to `talkmap/` directory
- Set `talkmap_link: true` in `_config.yml` to enable link on talks page

## Accessibility Requirements (Section 9 of PRD)

All interactions must support:
- **Keyboard navigation**: Tab order, Enter/Space activation, visible `:focus-visible` states
- **No hover-only**: Every hover interaction needs keyboard/touch equivalent
- **Semantic HTML**: Logical heading hierarchy (single `<h1>`), ARIA labels where needed
- **Alt text**: All meaningful images, captions for project media
- **Transcripts**: Required for audio CV

Test keyboard-only navigation through all CTAs, navigation links, and interactive elements.

## Common Pitfalls

1. **Front matter syntax**: YAML is strict about indentation and colons. Use quotes for values containing colons.
2. **Liquid filters**: Use `| relative_url` for internal links, `| absolute_url` for external contexts
3. **Asset paths**: Reference images as `/images/filename.png` or `{{ site.baseurl }}/images/filename.png`
4. **Collection output**: Ensure `output: true` in `_config.yml` collections to generate pages
5. **Git submodules**: This project doesn't use them; all files are tracked directly
6. **JS changes**: Run `npm run build:js` after editing files in `assets/js/` to update minified bundle

## Key Files Reference

- `_config.yml`: Site-wide settings, collections, theme config
- `_data/navigation.yml`: Header menu structure
- `_layouts/single.html`: Template for individual content pages
- `_includes/author-profile.html`: Sidebar author bio
- `_sass/_themes.scss`: Theme variables and styling
- `assets/js/_main.js`: Custom JavaScript (keep additions minimal)
- `PRD.md`: Complete product requirements and acceptance criteria

## Deployment

GitHub Pages automatically builds from the `main` branch. No manual build/deploy needed. Validate locally before pushing:
1. Check build succeeds: `bundle exec jekyll build`
2. Verify pages render correctly on `localhost:4000`
3. Test responsive layout (mobile/tablet/desktop)
4. Run keyboard-only navigation test
5. Validate all download links work

## North Star Metric

**Project page reach rate**: % of unique visitors who reach the interactive UX portfolio project page. Design decisions should optimize for fast comprehension (30-90 seconds to understand skills/fit) leading visitors to the deep-dive project page.
