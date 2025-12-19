---
layout: archive
title: "CV"
permalink: /cv/
author_profile: false
redirect_from:
  - /resume
---

{% include base_path %}

<div class="cv-cyber-container">

  <div class="cv-cyber-header">
    <h1 class="cv-cyber-header__title">Curriculum Vitae</h1>
    <p class="cv-cyber-header__subtitle">// Building the bridge between design vision and technical reality</p>
  </div>

  <section class="cv-cyber-section">
    <h2 class="cv-cyber-section__title">Education</h2>
    
    <div class="cv-cyber-timeline">
      <div class="cv-cyber-item">
        <h3 class="cv-cyber-item__title">M.Sc. User Experience Design</h3>
        <div class="cv-cyber-item__company">University Name</div>
        <div class="cv-cyber-item__meta">2024 (expected)</div>
        <div class="cv-cyber-item__description">
          <p>Focus: Human-Centered Design, ISO 9241-210, Strategic UX Methodology</p>
        </div>
      </div>

      <div class="cv-cyber-item">
        <h3 class="cv-cyber-item__title">B.Sc. Informatics and Design</h3>
        <div class="cv-cyber-item__company">University Name</div>
        <div class="cv-cyber-item__meta">2022</div>
        <div class="cv-cyber-item__description">
          <p>Foundation: Java, Algorithms, Logic, Visual Design<br>
          Thesis: Requirements-driven evaluation of Design-to-Code tools</p>
        </div>
      </div>
    </div>
  </section>

  <section class="cv-cyber-section">
    <h2 class="cv-cyber-section__title">Professional Experience</h2>
    
    <div class="cv-cyber-timeline">
      <div class="cv-cyber-item">
        <h3 class="cv-cyber-item__title">Working Student / Intern — NLP & AI Applications</h3>
        <div class="cv-cyber-item__company">BMW Group | Munich, Germany</div>
        <div class="cv-cyber-item__meta">Jan 2023 - Present</div>
        <div class="cv-cyber-item__description">
          <p>Developing scalable frontend interfaces for enterprise AI applications. Bridging complex backend AI services with intuitive UX for non-technical stakeholders.</p>
          <ul>
            <li>Built Angular applications integrating TypeScript, Java backends, Docker, and REST APIs</li>
            <li>Shipped features in large-scale agile environment (Scrum)</li>
            <li>Balanced innovation with enterprise constraints and technical debt management</li>
          </ul>
          <div class="cv-cyber-skills">
            <span class="cv-cyber-skill-badge">Angular</span>
            <span class="cv-cyber-skill-badge">TypeScript</span>
            <span class="cv-cyber-skill-badge">Java</span>
            <span class="cv-cyber-skill-badge">Docker</span>
            <span class="cv-cyber-skill-badge">REST APIs</span>
            <span class="cv-cyber-skill-badge">Git</span>
          </div>
        </div>
      </div>

      <div class="cv-cyber-item">
        <h3 class="cv-cyber-item__title">Product Management Working Student</h3>
        <div class="cv-cyber-item__company">Check24 | Munich, Germany</div>
        <div class="cv-cyber-item__meta">Jun 2022 - Dec 2022</div>
        <div class="cv-cyber-item__description">
          <p>Optimized user experience on high-traffic comparison platforms. Translated business requirements into technical implementation.</p>
          <ul>
            <li>Implemented chatbot features and mobile/web flow optimizations</li>
            <li>Conducted QA testing and agile product discovery</li>
            <li>Learned consumer product pace: speed and conversion as primary metrics</li>
          </ul>
          <div class="cv-cyber-skills">
            <span class="cv-cyber-skill-badge">React</span>
            <span class="cv-cyber-skill-badge">Agile</span>
            <span class="cv-cyber-skill-badge">A/B Testing</span>
            <span class="cv-cyber-skill-badge">Analytics</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="cv-cyber-section">
    <h2 class="cv-cyber-section__title">Technical Skills</h2>
    
    <div class="cv-cyber-skills-grid">
      <div class="cv-cyber-skill-category">
        <h4 class="cv-cyber-skill-category__title">Frontend Frameworks</h4>
        <div class="cv-cyber-skills">
          <span class="cv-cyber-skill-badge">React</span>
          <span class="cv-cyber-skill-badge">Angular</span>
        </div>
      </div>

      <div class="cv-cyber-skill-category">
        <h4 class="cv-cyber-skill-category__title">Languages</h4>
        <div class="cv-cyber-skills">
          <span class="cv-cyber-skill-badge">TypeScript</span>
          <span class="cv-cyber-skill-badge">JavaScript</span>
          <span class="cv-cyber-skill-badge">Java</span>
          <span class="cv-cyber-skill-badge">Python</span>
          <span class="cv-cyber-skill-badge">HTML5</span>
          <span class="cv-cyber-skill-badge">SCSS</span>
        </div>
      </div>

      <div class="cv-cyber-skill-category">
        <h4 class="cv-cyber-skill-category__title">Design & UX</h4>
        <div class="cv-cyber-skills">
          <span class="cv-cyber-skill-badge">Figma</span>
          <span class="cv-cyber-skill-badge">Adobe XD</span>
          <span class="cv-cyber-skill-badge">UXPin</span>
          <span class="cv-cyber-skill-badge">ISO 9241-210</span>
          <span class="cv-cyber-skill-badge">Prototyping</span>
        </div>
      </div>

      <div class="cv-cyber-skill-category">
        <h4 class="cv-cyber-skill-category__title">Tools & Methods</h4>
        <div class="cv-cyber-skills">
          <span class="cv-cyber-skill-badge">Git</span>
          <span class="cv-cyber-skill-badge">Docker</span>
          <span class="cv-cyber-skill-badge">REST APIs</span>
          <span class="cv-cyber-skill-badge">Agile/Scrum</span>
        </div>
      </div>

      <div class="cv-cyber-skill-category">
        <h4 class="cv-cyber-skill-category__title">Emerging Technologies</h4>
        <div class="cv-cyber-skills">
          <span class="cv-cyber-skill-badge">LLM/AI</span>
          <span class="cv-cyber-skill-badge">WebXR</span>
          <span class="cv-cyber-skill-badge">Unity</span>
          <span class="cv-cyber-skill-badge">Unreal</span>
        </div>
      </div>
    </div>
  </section>

  <section class="cv-cyber-section">
    <h2 class="cv-cyber-section__title">Publications</h2>
    
    <div class="cv-cyber-timeline">
      {% for post in site.publications reversed %}
        <div class="cv-cyber-item">
          <h3 class="cv-cyber-item__title">{{ post.title }}</h3>
          {% if post.venue %}
            <div class="cv-cyber-item__company">{{ post.venue }}</div>
          {% endif %}
          {% if post.date %}
            <div class="cv-cyber-item__meta">{{ post.date | date: "%B %Y" }}</div>
          {% endif %}
          {% if post.excerpt %}
            <div class="cv-cyber-item__description">
              <p>{{ post.excerpt | markdownify | strip_html }}</p>
            </div>
          {% endif %}
        </div>
      {% endfor %}
    </div>
  </section>

  <div class="cv-cyber-download">
    <a href="/files/cv-ece-sutanrikulu.pdf" class="cv-cyber-download__btn">
      <span>Download PDF Version</span>
      <i class="fa-solid fa-download"></i>
    </a>
  </div>

</div>

<div class="cv-cyber-footer">
  <em>Last updated: December 2025</em>
</div>
