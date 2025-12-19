# VibeCoding Academic Portfolio - AI Agent Instructions

## Profile Snapshot
- Name: Ece Sutanrikulu
- Role: Creative Technologist at the intersection of UX and engineering
- Focus: frontend from prototype to production, rapid learning of tools and frameworks, interactive 3D/XR, AI prototyping and evaluation, UX thinking and clear flows, collaboration with engineering
- Location: Munich, Germany
- Voice: concise, confident, evidence-based, no filler

## Project Overview
This repo is Ece's Academic Pages Jekyll site. It should feel minimal, creative, and editorial while communicating fit within 30 to 90 seconds. Content is in English.

## Critical Constraints
- Do not add new frameworks or JavaScript libraries.
- Work within Jekyll/Liquid/Markdown/SCSS and the existing JS stack (jQuery, FitVids, Plotly, theme toggle).
- Maintain accessibility and semantic HTML. Avoid hover-only interactions.

## Architecture and Structure

### Jekyll Collections System
Content is organized in collections defined in `_config.yml`:
- `_publications/`: Publications
- `_talks/`: Talks and presentations
- `_teaching/`: Courses taught
- `_portfolio/`: Case studies
- `_posts/`: Blog entries

Each collection uses `permalink: /:collection/:path/` and outputs individual pages.

### Layout Hierarchy
1. `_layouts/default.html` - Base template with masthead, footer, scripts
2. `_layouts/single.html` - Individual content pages (publications, talks, portfolio items)
3. `_layouts/archive.html` - Collection listing pages
4. `_includes/` - Reusable components (`masthead.html`, `footer.html`, `author-profile.html`)

Page content flow: `{% include masthead.html %}` -> `{{ content }}` -> `{% include footer.html %}`.

### Theme System
- Theme tokens live in `_sass/_themes.scss`; variants live in `_sass/theme/`.
- Theme toggle in `_includes/masthead.html` cycles light -> dark -> custom via `assets/js/_main.js`.
- `data-theme="dark"` or `data-theme="custom"` is applied on `<html>`; light uses the default.
- Update `_sass/theme/_custom.scss` for Ece's branded custom theme.

### Data and Navigation
- `_data/navigation.yml`: Header navigation
- `_data/cv.json`: Optional structured CV data
- `_data/ui-text.yml`: Localized UI strings

## Content Map
- Home: `_pages/about.md` with `layout: splash` and hero blocks (`hero-banner`, `hero-content`)
- CV: `_pages/cv.md`
- Portfolio list: `_pages/portfolio.html`
- Case studies: `_portfolio/` (front matter includes `problem`, `solution`, `impact`, `tech_stack`)

## Content and Voice Guidelines
- Keep first-person copy direct and pragmatic.
- Lead with outcomes and concrete work; avoid hype.
- Use short paragraphs and scannable headings.
- Keep the positioning consistent: Creative Technologist bridging UX and engineering.
- Highlight these focus areas when relevant:
  - Frontend experience from prototype to production
  - Fast learning of new tools and frameworks
  - Interactive 3D and XR experiences
  - AI prototyping and evaluation
  - UX thinking and clear flows
  - Collaboration with engineering

## Project-Specific Patterns (from PRD.md)

### 1. Tri Modal CV
- Text: `_pages/cv.md`
- Visual: Timeline or infographic using CSS Grid/Flexbox
- Audio: `<audio>` with transcript
- Include a PDF download link in `/files/`

### 2. Interactive Portfolio Project Page
Create in `_portfolio/` with front matter:
```yaml
---
layout: single
title: "Project Title"
authors: "Author Names"
institution: "Organization"
problem: "Problem statement"
solution: "Approach description"
impact: "Measurable results"
excerpt: "Short description for listing pages"
---
```
Must include:
- Optimized image/video in `/images/`
- PDF report download link
- At least one accessible interactive element (`<details>`/`<summary>` is preferred)

### 3. Hero Landing Page
Maintain a strong above-the-fold layout in `_pages/about.md`:
- Name and positioning line
- Short intro aligned with the profile snapshot above
- Primary CTAs: About, CV, Portfolio, Contact

## Accessibility Requirements
- Keyboard navigation and visible `:focus-visible` states
- No hover-only interactions
- Semantic HTML with a single `<h1>`
- Alt text for meaningful images
- Transcripts for audio

## Common Pitfalls
1. YAML front matter is strict with indentation and colons
2. Use `| relative_url` for internal links
3. Reference images as `/images/filename.png` or `{{ site.baseurl }}/images/filename.png`
4. Ensure `output: true` for collections in `_config.yml`
5. Run `npm run build:js` after editing files in `assets/js/`

## Key Files Reference
- `_config.yml`: Site settings and collections
- `_pages/about.md`: Home and hero content
- `_pages/cv.md`: CV content
- `_portfolio/`: Case studies
- `_sass/theme/_custom.scss`: Custom theme tokens
- `assets/js/_main.js`: Theme toggle logic
- `PRD.md`: Full requirements and acceptance criteria

## Deployment
GitHub Pages builds from `main`. Validate locally before pushing:
1. `bundle exec jekyll build`
2. Review at `localhost:4000`
3. Check mobile/tablet/desktop layouts
4. Run keyboard-only navigation test
5. Validate all download links

## North Star Metric
Project page reach rate: percent of unique visitors who reach the deep dive portfolio page.
