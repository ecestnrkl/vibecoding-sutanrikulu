# PRD: Ece Sutanrikulu VibeCoding Webprofile (Academic Pages)

Project Vibe (1 sentence pitch):
A minimal, creative, editorial webprofile that communicates skills and credibility fast, enables accessible tri modal CV consumption, and supports one deep dive Interactive UX Portfolio Project page using only Jekyll layouts, includes, Markdown, and CSS

Date: 2025-12-15
Author(s): Ece Sutanrikulu
Version: v0.1

Links:
Repo: https://github.com/ecestnrkl/vibecoding-sutanrikulu
Hackathon hub: https://vc-hackathon-hub.vercel.app/
Live site: TBD GitHub Pages URL

## 1) Core Context: Master Prompt

Problem (1 to 2 sentences)
My current online presence does not showcase my abilities in an engaging, differentiated way, so recruiters and professionals cannot quickly understand proof, strengths, and fit

Solution (1 to 2 sentences)
Customize the Academic Pages template into a branded editorial personal site with a strong hero landing, an accessible tri modal CV, and one interactive deep dive project page with evidence and downloadable report

Target Users
Primary: recruiters evaluating candidates quickly
Secondary: industry professionals exploring collaboration opportunities

Primary Use Cases
1. Get to know me in 30 to 90 seconds
2. Download my CV quickly
3. Review one project deeply: problem, method, outcomes, evidence

North Star Success Metric
Project page reach rate: percent of unique visitors who reach the Interactive UX Portfolio Project page

Non Goals
No user accounts, comments, or gated content
No backend services in V1
No new frameworks and no new JavaScript libraries

## 2) UX Foundations (Vibe, Research, Accessibility)

Personas
Recruiter
Needs fast comprehension, skills match, credibility signals, CV download
Success decides worth interviewing within 30 to 90 seconds

Industry professional
Needs clarity of craft and thinking, deeper case study, easy contact
Success understands approach and reaches out

Top Insights and Pain Points
Many portfolios look identical, differentiation should come from editorial structure plus proof, not tool lists
Visitors trust outcomes and artifacts more than adjectives

Emotional and Contextual Vibe Principles
Minimal
Creative
Editorial
Outcome driven

Accessibility and Inclusion Requirements
Semantic headings and logical reading order
Keyboard navigability with visible focus
High contrast and readable type scale
Motion safe behavior
Audio CV includes transcript

High Level Journey
Landing → About → CV → Projects → Project detail → Contact

## 3) Scope and Priorities

MVP Goals V1
Custom theme plus branding applied site wide
Theme icon hover reveals 3 options: light, dark, and my custom theme
Personalized hero landing with tagline, welcome message, profile picture or AI hero image, quick access links
Accessible tri modal CV: text, visual, audio, interactive experience, plus downloadable PDF
Interactive UX Portfolio Project page with required fields, at least one interactive element, and PDF report download
Navigation and contact entry point on key pages

Out of Scope for V1
Full CMS or admin editing system
Complete multilingual site
Full blog engine
Interactive paper page (optional P1)
Complex analytics setup (keep minimal)

Assumptions and Risks
Asset readiness risk: images, audio, and PDF report ready in time
Template constraints risk: Academic Pages and Jekyll build limit layout changes
Accessibility risk: interactions must not be hover only, needs keyboard and touch parity

## 4) Tech Stack and Architecture

Frontend
Jekyll using Academic Pages, Liquid templates, Markdown, CSS

Backend
None, static site

Database
None, content stored in repo files

Deployment
GitHub Pages

Security and Privacy
No user data collection in MVP
Static downloads served from repo assets

## 5) Feature Modules (Prompt by Prompt)

Module A: Custom Theme plus Branding
Priority: P0
User Story
As a visitor, I want the site to feel clearly like Ece, so I immediately trust it is curated
Acceptance Criteria
[ ] Design tokens defined for color, type scale, spacing, components
[ ] Theme icon hover shows light, dark, custom theme options
[ ] Consistent styling across all primary pages
[ ] Responsive layout works on mobile, tablet, desktop
[ ] Focus states visible, links and buttons consistent

Module B: Hero Landing Page
Priority: P0
User Story
As a recruiter or professional, I want to understand who Ece is and what she does in under 30 seconds
Acceptance Criteria
[ ] Above the fold includes name, positioning line, short intro, hero image
[ ] Primary CTAs visible: About, CV, Project, Contact
[ ] Credibility strip included
[ ] Quick access to key content

Module C: Accessible Tri Modal CV
Priority: P0
User Story
As a visitor, I want to consume Ece’s experience in the format that best fits my time and needs
Acceptance Criteria
[ ] Text CV web optimized
[ ] Visual CV as timeline or infographic
[ ] Audio CV with player plus transcript
[ ] Interactive experience, not just static sections
[ ] CV downloadable as PDF

Module D: Interactive UX Portfolio Project Page
Priority: P0
User Story
As a recruiter or professional, I want to review one project deeply and see concrete outcomes and evidence
Acceptance Criteria
[ ] Includes required fields: title, authors, institution or customer, problem statement, method, outcomes
[ ] Includes picture or video or animation
[ ] Includes PDF report download
[ ] Includes at least one accessible interactive element such as details summary, click through reveal, flip card with keyboard support

Module E: Navigation plus Contact
Priority: P0
User Story
As a visitor, I want to navigate and contact Ece with minimal friction
Acceptance Criteria
[ ] Persistent navigation: Landing, About, CV, Projects, Contact
[ ] Contact includes email link plus optional LinkedIn and GitHub
[ ] Contact CTA appears on landing and at end of project page

Module F: Interactive Paper Page (Optional)
Priority: P1
User Story
As a professional, I want to explore a publication with interactive visuals and download the PDF
Acceptance Criteria
[ ] Only if time permits, otherwise not built in V1

## 6) AI Design and Prompting Strategy

System Prompt
I am working on a Jekyll site (Academic Pages). Do not introduce new frameworks or JavaScript libraries. Modify only existing layouts, includes, Markdown, or CSS

Prompt Bank (examples)
Update landing hero layout and typography hierarchy using existing theme files only
Create CV tri modal mode switcher using CSS only patterns
Implement project page progressive disclosure using details summary and CSS
Refine navigation styles and focus states for keyboard users
Add project card styles using existing includes and CSS

Hallucination Mitigation and Safety
Commit early and often and use git as undo button
Test locally with bundle exec jekyll serve after each change
Keep changes small and reversible, one module per commit

Vibe Coding History
v0.1 PRD created and saved as PRD.md

## 7) IA, Flows and UI

Information Architecture
Landing
About
CV
Projects overview
Project detail
Contact

Key Flows
Recruiter scan: Landing → CV → Project detail → Contact
Deep dive: Landing → About → Project detail → Contact

Design Tokens and Components
Tokens: color, type scale, spacing scale, max width, radii, shadows
Components: CTA button, project card, metadata row, media figure with caption, timeline block, details summary accordion

Localization and Tone Guidelines
Primary language English
Tone editorial, minimal, confident
Prefer outcomes and specifics over adjectives

## 8) Iteration Plan and Workflow

Build Rhythm and Hackathon Tags
Milestone: PRD done
Milestone: Theme done
Milestone: Hero done
Milestone: CV done
Milestone: Project done

Risk and Spike Tickets
CSS only tri modal switching
Accessible interaction patterns without hover only dependency
Template layout overrides without breaking build

## 9) Quality: Testing, A11y, Performance

Testing
Manual smoke test on mobile and desktop
Link checks for navigation, CTAs, downloads, external profiles

Accessibility
Keyboard only navigation through all interactive elements
Heading hierarchy logical, single H1
Alt text for meaningful images, captions for project media
Transcript for audio CV

Performance Budgets
Optimize images and keep hero concise
Avoid heavy auto playing media

## 10) Metrics and Analytics

Minimum Events
Project page views
CV download clicks
Project report download clicks
Contact clicks

KPIs
North star: project page reach rate
Supporting: CV download rate, project PDF download rate, contact click through rate

## 11) Launch and Ops

Environments
Local Jekyll development
GitHub Pages production

Rollout Plan
Confirm GitHub Pages build succeeds
Validate required pages and downloads in production
Final QA pass: keyboard nav, mobile layout, interaction behavior