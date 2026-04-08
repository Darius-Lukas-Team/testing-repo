# Component Library

Complete HTML patterns for every visual component. **All CSS for these components is defined in `brand/brand.css`** — the single source of truth for styles. The CSS shown below each component is for reference only; do not duplicate it in output files. Instead, inline `brand.css` into the `<style>` block as described in `SKILL.md`.

All components assume they sit inside a `.page-wrapper` with `max-width: 1200px; margin: 0 auto; padding: 0 40px;`.

**Important:** No text in any component should be smaller than 14px. YouTube compression destroys small text. When in doubt, go larger.

---

## Table of Contents

1. [Hero Section](#1-hero-section)
2. [Section Container](#2-section-container)
3. [Flow Diagram / Node Row](#3-flow-diagram--node-row)
4. [Parallel Branches / Card Grid](#4-parallel-branches--card-grid)
5. [Comparison Grid](#5-comparison-grid)
6. [Stat Cards](#6-stat-cards)
7. [Timeline](#7-timeline)
8. [Before/After](#8-beforeafter)
9. [Step Sequence](#9-step-sequence)
10. [Icon Grid](#10-icon-grid)
11. [Callout Box](#11-callout-box)
12. [Quote Block](#12-quote-block)
13. [Pricing Table](#13-pricing-table)
14. [Mind Map](#14-mind-map)
15. [Code Block](#15-code-block)
16. [Section Divider](#16-section-divider)
17. [Summary Bar](#17-summary-bar)
18. [Pie Chart (SVG)](#18-pie-chart-svg)
19. [Donut / Ring Chart (SVG)](#19-donut--ring-chart-svg)
20. [Horizontal Bar Chart (CSS)](#20-horizontal-bar-chart-css)
21. [Gantt Chart](#21-gantt-chart)
22. [Radial / Circular Diagram (SVG)](#22-radial--circular-diagram-svg)
23. [Progress Bars](#23-progress-bars)
24. [Flowchart](#24-flowchart)
25. [Network Diagram (D3.js)](#25-network-diagram-d3js)
26. [Block Diagram](#26-block-diagram)
27. [Sitemap (D3.js)](#27-sitemap-d3js)
28. [Organizational Chart (D3.js)](#28-organizational-chart-d3js)
29. [Venn Diagram](#29-venn-diagram)
30. [Cycle Diagram](#30-cycle-diagram)
31. [Hierarchy Pyramid](#31-hierarchy-pyramid)
32. [Quadrant Diagram](#32-quadrant-diagram)
33. [Line Chart (SVG)](#33-line-chart-svg)
34. [Area Chart (SVG)](#34-area-chart-svg)
35. [Column Chart (SVG)](#35-column-chart-svg)
36. [Agenda/Outline Slide](#36-agendaoutline-slide)
37. [Section Header Slide](#37-section-header-slide)
38. [Title + Content Split Slide](#38-title--content-split-slide)
39. [Summary/Recap Slide](#39-summaryrecap-slide)
40. [Testimonial Wall](#40-testimonial-wall)
41. [Offer Stack Slide](#41-offer-stack-slide)
42. [Guarantee Badge Slide](#42-guarantee-badge-slide)
43. [Emotional Contrast Slide](#43-emotional-contrast-slide)

---

## 1. Hero Section

The opening section of every page. Contains the logo, title, and subtitle. Designed to fill the first viewport. The title should be the largest text on the entire page — it's the first thing viewers see.

```html
<section class="hero">
  <img src="[LOGO_URL]" alt="Logo" class="hero-logo">
  <h1 class="hero-title">[Title]</h1>
  <p class="hero-subtitle">[Subtitle — 1-2 sentences]</p>
</section>
```

```css
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 40px;
}
.hero-logo {
  height: 60px;
  margin-bottom: 32px;
}
.hero-title {
  font-size: 72px;
  font-weight: 600;
  color: #fff;
  line-height: 1.15;
  margin-bottom: 20px;
  max-width: 1000px;
}
.hero-subtitle {
  font-size: 26px;
  color: rgba(255,255,255,0.65);
  line-height: 1.5;
  max-width: 750px;
}
```

---

## 2. Section Container

Wraps every content section. Provides consistent vertical spacing and an optional label + title.

```html
<section class="section">
  <div class="section-label">[Phase / Category Label]</div>
  <h2 class="section-title">[Section Heading]</h2>
  <p class="section-desc">[Optional 1-2 sentence description]</p>
  <!-- Components go here -->
</section>
```

```css
.section {
  background: rgba(255, 255, 255, 0.06);
  border-radius: 16px;
  padding: 40px 44px;
  border: 1px solid rgba(79, 48, 254, 0.12);
  margin-bottom: 40px;
}
.section-label {
  font-size: 14px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  color: #4F30FE;
  margin-bottom: 14px;
}
.section-title {
  font-size: 38px;
  font-weight: 600;
  color: #fff;
  margin-bottom: 10px;
  line-height: 1.25;
}
.section-desc {
  font-size: 20px;
  color: rgba(255,255,255,0.6);
  line-height: 1.6;
  margin-bottom: 28px;
  max-width: 850px;
}
```

---

## 3. Flow Diagram / Node Row

A horizontal sequence of connected nodes showing a process or data flow. Each node has an icon, type label, name, and optional detail text. Arrows connect them.

```html
<div class="node-row">
  <div class="node [color-class]">
    <div class="node-icon">[emoji or letter]</div>
    <div class="node-content">
      <div class="node-type">[Type Label]</div>
      <div class="node-name">[Node Name]</div>
      <div class="node-detail">[Optional detail]</div>
    </div>
  </div>
  <div class="arrow">&#8594;</div>
  <div class="node [color-class]">
    <!-- ... -->
  </div>
</div>
```

```css
.node-row {
  display: flex;
  align-items: center;
  gap: 16px;
  flex-wrap: wrap;
}
.node {
  display: inline-flex;
  align-items: center;
  gap: 14px;
  background: rgba(20, 18, 60, 0.9);
  border: 1px solid rgba(79, 48, 254, 0.15);
  border-radius: 12px;
  padding: 16px 22px;
  transition: border-color 0.2s;
}
.node:hover { border-color: rgba(79, 48, 254, 0.4); }
.node-icon {
  width: 42px;
  height: 42px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  flex-shrink: 0;
}
.node-content { display: flex; flex-direction: column; gap: 3px; }
.node-type {
  font-size: 14px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  color: #4F30FE;
}
.node-name { font-size: 18px; color: #e8e8e8; font-weight: 600; }
.node-detail { font-size: 15px; color: rgba(255,255,255,0.45); }
.arrow { color: rgba(79, 48, 254, 0.4); font-size: 26px; flex-shrink: 0; }

/* Color variants for node icons */
.node-gold .node-icon { background: rgba(79, 48, 254, 0.15); color: #4F30FE; }
.node-green .node-icon { background: rgba(218, 179, 255, 0.2); color: #4CAF50; }
.node-teal .node-icon { background: rgba(255, 38, 139, 0.2); color: #4F30FE; }
.node-amber .node-icon { background: rgba(160, 136, 255, 0.2); color: #DAB3FF; }
.node-purple .node-icon { background: rgba(83, 198, 38, 0.2); color: #22c55e; }
```

---

## 4. Parallel Branches / Card Grid

A grid of cards, each representing a branch, category, or item. Supports 2–4 columns. Each card can have an icon, title, count badge, a list of sub-items, and a summary footer.

```html
<div class="card-grid cols-3">
  <div class="card">
    <div class="card-accent" style="background: linear-gradient(90deg, #4F30FE, #DAB3FF);"></div>
    <div class="card-header">
      <div class="card-icon" style="background:rgba(79,48,254,0.15); color:#4F30FE;">[emoji]</div>
      <div class="card-title">[Title]</div>
      <div class="card-badge">[Badge Text]</div>
    </div>
    <div class="card-items">
      <div class="card-item">
        <div class="card-dot" style="background:#4F30FE;"></div>
        <div class="card-item-name">[Item name]</div>
        <div class="card-item-count">[count]</div>
      </div>
      <!-- more items... -->
    </div>
    <div class="card-footer">
      <div><div class="card-footer-label">[Label]</div><div class="card-footer-value" style="color:#4F30FE;">[Value]</div></div>
    </div>
  </div>
  <!-- more cards... -->
</div>
```

```css
.card-grid {
  display: grid;
  gap: 20px;
}
.card-grid.cols-2 { grid-template-columns: repeat(2, 1fr); }
.card-grid.cols-3 { grid-template-columns: repeat(3, 1fr); }
.card-grid.cols-4 { grid-template-columns: repeat(4, 1fr); }
.card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 14px;
  padding: 26px 24px;
  position: relative;
  overflow: hidden;
}
.card-accent {
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
}
.card-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 18px;
}
.card-icon {
  width: 40px; height: 40px;
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 18px; flex-shrink: 0;
}
.card-title { font-size: 20px; font-weight: 600; color: #fff; }
.card-badge {
  font-size: 14px; font-weight: 600;
  padding: 4px 12px; border-radius: 8px;
  margin-left: auto;
  background: rgba(79, 48, 254, 0.12);
  color: #4F30FE;
}
.card-items { display: flex; flex-direction: column; gap: 8px; }
.card-item {
  display: flex; align-items: center; gap: 10px;
  padding: 9px 14px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
  font-size: 16px;
}
.card-dot {
  width: 10px; height: 10px;
  border-radius: 50%; flex-shrink: 0;
}
.card-item-name { flex: 1; color: rgba(255,255,255,0.7); }
.card-item-count { font-size: 14px; color: rgba(255,255,255,0.4); font-weight: 600; }
.card-footer {
  margin-top: 16px; padding-top: 16px;
  border-top: 1px solid rgba(79, 48, 254, 0.1);
  display: flex; justify-content: space-between;
}
.card-footer-label { font-size: 14px; color: rgba(255,255,255,0.4); }
.card-footer-value { font-size: 28px; font-weight: 600; }
```

---

## 5. Comparison Grid

Side-by-side cards for comparing options. One card can be highlighted as "recommended" with a special border. Each card has a badge, title, description, and a list of pros/cons.

```html
<div class="compare-grid">
  <div class="compare-card">
    <div class="compare-badge badge-caution">[Badge]</div>
    <div class="compare-title">[Option Name]</div>
    <div class="compare-desc">[Description]</div>
    <div class="compare-points">
      <div class="point-pro">&#10003; [Pro point]</div>
      <div class="point-con">&#10007; [Con point]</div>
    </div>
  </div>
  <div class="compare-card recommended">
    <div class="compare-badge badge-recommended">Recommended</div>
    <!-- ... -->
  </div>
</div>
```

```css
.compare-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}
.compare-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 14px;
  padding: 28px;
}
.compare-card.recommended {
  border-color: #4F30FE;
  box-shadow: 0 0 24px rgba(79, 48, 254, 0.12);
}
.compare-badge {
  font-size: 14px; font-weight: 600; text-transform: uppercase;
  letter-spacing: 1px; padding: 5px 14px; border-radius: 6px;
  display: inline-block; margin-bottom: 14px;
}
.badge-caution { background: rgba(79, 48, 254, 0.12); color: #4F30FE; }
.badge-warning { background: rgba(255, 70, 46, 0.15); color: #ff462e; }
.badge-recommended { background: rgba(218, 179, 255, 0.2); color: #4CAF50; }
.compare-title { font-size: 22px; font-weight: 600; color: #e8e8e8; margin-bottom: 10px; }
.compare-desc { font-size: 17px; color: rgba(255,255,255,0.5); line-height: 1.5; margin-bottom: 18px; }
.compare-points { display: flex; flex-direction: column; gap: 8px; }
.point-pro { color: #4CAF50; font-size: 17px; line-height: 1.6; }
.point-con { color: #ff462e; font-size: 17px; line-height: 1.6; }
```

---

## 6. Stat Cards

A row of large-number cards for highlighting key metrics. Horizontally centered, bold numbers with labels.

```html
<div class="stat-row">
  <div class="stat-card">
    <div class="stat-num">[Number]</div>
    <div class="stat-label">[Label]</div>
  </div>
  <!-- more stat cards... -->
</div>
```

```css
.stat-row {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}
.stat-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 14px;
  padding: 24px 32px;
  text-align: center;
  min-width: 160px;
}
.stat-num {
  font-size: 56px;
  font-weight: 600;
  color: #4F30FE;
  line-height: 1.1;
}
.stat-label {
  font-size: 16px;
  color: rgba(255,255,255,0.5);
  margin-top: 8px;
}
```

---

## 7. Timeline

A vertical timeline with dots and connecting lines. Each entry has a time/date marker and content.

```html
<div class="timeline">
  <div class="timeline-entry">
    <div class="timeline-marker">
      <div class="timeline-dot"></div>
      <div class="timeline-line"></div>
    </div>
    <div class="timeline-content">
      <div class="timeline-date">[Date or timing label]</div>
      <div class="timeline-title">[Event title]</div>
      <div class="timeline-desc">[Description]</div>
    </div>
  </div>
  <!-- more entries... (last entry: omit .timeline-line) -->
</div>
```

```css
.timeline { display: flex; flex-direction: column; gap: 0; padding-left: 20px; }
.timeline-entry { display: flex; gap: 28px; min-height: 110px; }
.timeline-marker {
  display: flex; flex-direction: column; align-items: center;
  flex-shrink: 0; width: 24px;
}
.timeline-dot {
  width: 18px; height: 18px; border-radius: 50%;
  background: #4F30FE; flex-shrink: 0;
  box-shadow: 0 0 14px rgba(79, 48, 254, 0.3);
}
.timeline-line {
  width: 2px; flex: 1;
  background: rgba(79, 48, 254, 0.2);
}
.timeline-content { padding-bottom: 36px; }
.timeline-date {
  font-size: 15px; font-weight: 600; color: #4F30FE;
  text-transform: uppercase; letter-spacing: 1px;
  margin-bottom: 8px;
}
.timeline-title { font-size: 22px; font-weight: 600; color: #fff; margin-bottom: 8px; }
.timeline-desc { font-size: 18px; color: rgba(255,255,255,0.55); line-height: 1.6; }
```

---

## 8. Before/After

Two-column layout showing a "before" state and an "after" state, connected by an arrow or transformation indicator.

```html
<div class="before-after">
  <div class="ba-card ba-before">
    <div class="ba-label">Before</div>
    <div class="ba-title">[Before State]</div>
    <div class="ba-desc">[Description of the problem or old way]</div>
  </div>
  <div class="ba-arrow">&#10140;</div>
  <div class="ba-card ba-after">
    <div class="ba-label">After</div>
    <div class="ba-title">[After State]</div>
    <div class="ba-desc">[Description of the solution or new way]</div>
  </div>
</div>
```

```css
.before-after {
  display: flex; align-items: stretch; gap: 24px;
}
.ba-card {
  flex: 1; padding: 32px; border-radius: 14px;
}
.ba-before {
  background: rgba(255, 70, 46, 0.08);
  border: 1px solid rgba(255, 70, 46, 0.2);
}
.ba-after {
  background: rgba(218, 179, 255, 0.08);
  border: 1px solid rgba(218, 179, 255, 0.25);
}
.ba-label {
  font-size: 14px; font-weight: 600; text-transform: uppercase;
  letter-spacing: 1.5px; margin-bottom: 12px;
}
.ba-before .ba-label { color: #ff462e; }
.ba-after .ba-label { color: #4CAF50; }
.ba-title { font-size: 24px; font-weight: 600; color: #fff; margin-bottom: 10px; }
.ba-desc { font-size: 18px; color: rgba(255,255,255,0.6); line-height: 1.6; }
.ba-arrow {
  display: flex; align-items: center; justify-content: center;
  font-size: 42px; color: #4F30FE; flex-shrink: 0; width: 56px;
}
```

---

## 9. Step Sequence

Numbered steps with visual step indicators. Each step has a number badge, title, and description.

```html
<div class="steps">
  <div class="step">
    <div class="step-num">1</div>
    <div class="step-content">
      <div class="step-title">[Step Title]</div>
      <div class="step-desc">[What to do in this step]</div>
    </div>
  </div>
  <!-- more steps... -->
</div>
```

```css
.steps { display: flex; flex-direction: column; gap: 18px; }
.step {
  display: flex; align-items: flex-start; gap: 22px;
  padding: 22px 28px;
  background: rgba(255, 255, 255, 0.03);
  border-radius: 12px;
  border: 1px solid rgba(79, 48, 254, 0.08);
}
.step-num {
  width: 48px; height: 48px; border-radius: 50%;
  background: linear-gradient(135deg, #DAB3FF, #262DFF);
  color: #fff; font-size: 22px; font-weight: 600;
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
}
.step-content { flex: 1; }
.step-title { font-size: 21px; font-weight: 600; color: #fff; margin-bottom: 6px; }
.step-desc { font-size: 18px; color: rgba(255,255,255,0.55); line-height: 1.6; }
```

---

## 10. Icon Grid

A grid of items each with an icon/emoji, title, and short description. Good for feature lists or category overviews.

```html
<div class="icon-grid">
  <div class="icon-item">
    <div class="icon-box" style="background:rgba(79,48,254,0.12); color:#4F30FE;">[emoji]</div>
    <div class="icon-title">[Title]</div>
    <div class="icon-desc">[Short description]</div>
  </div>
  <!-- more items... -->
</div>
```

```css
.icon-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 18px;
}
.icon-item {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.08);
  border-radius: 12px;
  padding: 26px 22px;
  text-align: center;
}
.icon-box {
  width: 56px; height: 56px; border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 26px; margin: 0 auto 16px;
}
.icon-title { font-size: 19px; font-weight: 600; color: #fff; margin-bottom: 8px; }
.icon-desc { font-size: 16px; color: rgba(255,255,255,0.5); line-height: 1.5; }
```

---

## 11. Callout Box

A highlighted box for key insights, warnings, or important takeaways.

```html
<div class="callout">
  <div class="callout-title">[Callout Title]</div>
  <div class="callout-text">[Callout content — can include <strong>bold</strong> and <br> line breaks]</div>
</div>
```

```css
.callout {
  background: linear-gradient(135deg, rgba(79,48,254,0.08), rgba(218,179,255,0.08));
  border: 1px solid rgba(79, 48, 254, 0.2);
  border-radius: 14px;
  padding: 28px 32px;
}
.callout-title {
  font-size: 20px; font-weight: 600;
  color: #4F30FE; margin-bottom: 12px;
}
.callout-text {
  font-size: 18px; color: rgba(255,255,255,0.7);
  line-height: 1.7;
}
.callout-text strong { color: #fff; }
```

---

## 12. Quote Block

For testimonials, citations, or highlighted quotes.

```html
<div class="quote-block">
  <div class="quote-mark">&#8220;</div>
  <div class="quote-text">[Quote text]</div>
  <div class="quote-author">&#8212; [Author Name], [Title/Context]</div>
</div>
```

```css
.quote-block {
  background: rgba(255, 255, 255, 0.03);
  border-left: 4px solid #4F30FE;
  border-radius: 0 14px 14px 0;
  padding: 32px 36px;
}
.quote-mark {
  font-size: 56px; color: rgba(79, 48, 254, 0.3);
  line-height: 1; margin-bottom: -10px;
}
.quote-text {
  font-size: 22px; color: rgba(255,255,255,0.85);
  line-height: 1.6; font-style: italic;
  margin-bottom: 14px;
}
.quote-author {
  font-size: 17px; color: rgba(79, 48, 254, 0.7);
  font-weight: 600;
}
```

---

## 13. Pricing Table

Side-by-side tier cards with feature lists. One tier can be highlighted.

```html
<div class="pricing-grid">
  <div class="pricing-card">
    <div class="pricing-tier">[Tier Name]</div>
    <div class="pricing-price">[Price]</div>
    <div class="pricing-period">[per month / one-time / etc.]</div>
    <div class="pricing-features">
      <div class="pricing-feature">&#10003; [Feature]</div>
      <div class="pricing-feature">&#10003; [Feature]</div>
      <div class="pricing-feature muted">&#10007; [Not included]</div>
    </div>
  </div>
  <div class="pricing-card pricing-featured">
    <!-- highlighted tier -->
  </div>
</div>
```

```css
.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 20px;
}
.pricing-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 14px;
  padding: 36px 32px;
  text-align: center;
}
.pricing-card.pricing-featured {
  border-color: #4F30FE;
  box-shadow: 0 0 30px rgba(79, 48, 254, 0.1);
  transform: scale(1.03);
}
.pricing-tier {
  font-size: 17px; font-weight: 600; color: #4F30FE;
  text-transform: uppercase; letter-spacing: 1.5px;
  margin-bottom: 14px;
}
.pricing-price { font-size: 60px; font-weight: 600; color: #fff; }
.pricing-period { font-size: 17px; color: rgba(255,255,255,0.4); margin-bottom: 28px; }
.pricing-features { text-align: left; display: flex; flex-direction: column; gap: 12px; }
.pricing-feature { font-size: 18px; color: rgba(255,255,255,0.7); }
.pricing-feature.muted { color: rgba(255,255,255,0.25); }
```

---

## 14. Mind Map

A central concept with radiating connected branches. Built with CSS flexbox and connector lines.

```html
<div class="mind-map">
  <div class="mm-branches mm-left">
    <div class="mm-branch">
      <div class="mm-node">[Branch 1]</div>
      <div class="mm-connector"></div>
    </div>
    <div class="mm-branch">
      <div class="mm-node">[Branch 2]</div>
      <div class="mm-connector"></div>
    </div>
  </div>
  <div class="mm-center">[Central Concept]</div>
  <div class="mm-branches mm-right">
    <div class="mm-branch">
      <div class="mm-connector"></div>
      <div class="mm-node">[Branch 3]</div>
    </div>
    <div class="mm-branch">
      <div class="mm-connector"></div>
      <div class="mm-node">[Branch 4]</div>
    </div>
  </div>
</div>
```

```css
.mind-map {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0;
  padding: 48px 0;
}
.mm-center {
  background: linear-gradient(135deg, #DAB3FF, #262DFF);
  color: #fff;
  font-size: 22px; font-weight: 600;
  padding: 28px 36px;
  border-radius: 50%;
  text-align: center;
  min-width: 180px; min-height: 180px;
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
  box-shadow: 0 0 40px rgba(79, 48, 254, 0.2);
  z-index: 1;
}
.mm-branches {
  display: flex; flex-direction: column; gap: 20px;
}
.mm-branch { display: flex; align-items: center; gap: 0; }
.mm-connector {
  width: 70px; height: 2px;
  background: rgba(79, 48, 254, 0.3);
}
.mm-node {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.15);
  border-radius: 10px;
  padding: 14px 24px;
  font-size: 18px; font-weight: 600; color: #e8e8e8;
  white-space: nowrap;
}
```

---

## 15. Code Block

Styled code snippet with a language label.

```html
<div class="code-block">
  <div class="code-label">[Language / Context]</div>
  <pre class="code-content"><code>[code here]</code></pre>
</div>
```

```css
.code-block {
  background: rgba(8, 8, 20, 0.9);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 12px;
  overflow: hidden;
}
.code-label {
  background: rgba(79, 48, 254, 0.08);
  padding: 10px 20px;
  font-size: 14px; font-weight: 600; color: #4F30FE;
  text-transform: uppercase; letter-spacing: 1px;
  border-bottom: 1px solid rgba(79, 48, 254, 0.1);
}
.code-content {
  padding: 24px;
  font-family: 'SF Mono', 'Fira Code', monospace;
  font-size: 17px;
  color: rgba(255,255,255,0.8);
  line-height: 1.6;
  overflow-x: auto;
  margin: 0;
}
```

---

## 16. Section Divider

A subtle visual separator between major topic shifts. Use sparingly.

```html
<div class="divider">
  <div class="divider-line"></div>
  <div class="divider-dot"></div>
  <div class="divider-line"></div>
</div>
```

```css
.divider {
  display: flex;
  align-items: center;
  gap: 16px;
  margin: 56px 0;
}
.divider-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(79,48,254,0.2), transparent);
}
.divider-dot {
  width: 8px; height: 8px;
  border-radius: 50%;
  background: #4F30FE;
}
```

---

## 17. Summary Bar

A horizontal row of key metrics or takeaways, typically used near the end of a page.

```html
<div class="summary-bar">
  <div class="summary-item">
    <div class="summary-value">[Value]</div>
    <div class="summary-label">[Label]</div>
  </div>
  <!-- more items... -->
</div>
```

```css
.summary-bar {
  display: flex;
  flex-wrap: wrap;
  gap: 18px;
  justify-content: center;
}
.summary-item {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 12px;
  padding: 22px 32px;
  text-align: center;
  min-width: 160px;
}
.summary-value {
  font-size: 40px; font-weight: 600;
  color: #4F30FE;
}
.summary-label {
  font-size: 15px;
  color: rgba(255,255,255,0.45);
  margin-top: 6px;
}
```

---

## 18. Pie Chart (SVG)

An inline SVG pie chart for showing proportional data. Each slice is a `<circle>` with `stroke-dasharray` and `stroke-dashoffset` for the arc. Include a legend below.

Best for: market share, budget allocation, distribution of categories (2–6 slices).

```html
<div class="chart-container">
  <svg class="pie-chart" viewBox="0 0 200 200">
    <!-- Background circle (optional subtle ring) -->
    <circle cx="100" cy="100" r="80" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="40"/>
    <!-- Slice 1: 40% -->
    <circle cx="100" cy="100" r="80" fill="none"
      stroke="#4F30FE" stroke-width="40"
      stroke-dasharray="201 503" stroke-dashoffset="0"
      transform="rotate(-90 100 100)"/>
    <!-- Slice 2: 30% -->
    <circle cx="100" cy="100" r="80" fill="none"
      stroke="#DAB3FF" stroke-width="40"
      stroke-dasharray="151 503" stroke-dashoffset="-201"
      transform="rotate(-90 100 100)"/>
    <!-- Slice 3: 20% -->
    <circle cx="100" cy="100" r="80" fill="none"
      stroke="#4F30FE" stroke-width="40"
      stroke-dasharray="100 503" stroke-dashoffset="-352"
      transform="rotate(-90 100 100)"/>
    <!-- Slice 4: 10% -->
    <circle cx="100" cy="100" r="80" fill="none"
      stroke="#22c55e" stroke-width="40"
      stroke-dasharray="50 503" stroke-dashoffset="-452"
      transform="rotate(-90 100 100)"/>
  </svg>
  <div class="chart-legend">
    <div class="legend-item"><div class="legend-dot" style="background:#4F30FE;"></div><span>[Label 1] — 40%</span></div>
    <div class="legend-item"><div class="legend-dot" style="background:#DAB3FF;"></div><span>[Label 2] — 30%</span></div>
    <div class="legend-item"><div class="legend-dot" style="background:#4F30FE;"></div><span>[Label 3] — 20%</span></div>
    <div class="legend-item"><div class="legend-dot" style="background:#22c55e;"></div><span>[Label 4] — 10%</span></div>
  </div>
</div>
```

**How to calculate slices:** The circumference of r=80 is `2 * π * 80 ≈ 503`. Each slice's `stroke-dasharray` first value = `503 * percentage / 100`. The `stroke-dashoffset` is the negative cumulative total of all preceding slices.

```css
.chart-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 48px;
  padding: 20px 0;
}
.pie-chart {
  width: 280px;
  height: 280px;
  flex-shrink: 0;
}
.chart-legend {
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.legend-item {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 18px;
  color: rgba(255,255,255,0.75);
}
.legend-dot {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  flex-shrink: 0;
}
```

---

## 19. Donut / Ring Chart (SVG)

Same as pie chart but with a thinner stroke, leaving a hollow center that can display a key number or label. Visually cleaner for single-metric emphasis.

Best for: completion percentage, single key metric, budget spent vs remaining.

```html
<div class="chart-container">
  <div class="donut-wrapper">
    <svg class="donut-chart" viewBox="0 0 200 200">
      <!-- Background ring -->
      <circle cx="100" cy="100" r="80" fill="none" stroke="rgba(255,255,255,0.06)" stroke-width="20"/>
      <!-- Filled arc (72%) -->
      <circle cx="100" cy="100" r="80" fill="none"
        stroke="url(#purple-blue-grad)" stroke-width="20"
        stroke-dasharray="362 503" stroke-dashoffset="0"
        stroke-linecap="round"
        transform="rotate(-90 100 100)"/>
      <defs>
        <linearGradient id="purple-blue-grad" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#4F30FE"/>
          <stop offset="100%" stop-color="#DAB3FF"/>
        </linearGradient>
      </defs>
    </svg>
    <div class="donut-center">
      <div class="donut-value">72%</div>
      <div class="donut-label">[Label]</div>
    </div>
  </div>
</div>
```

```css
.donut-wrapper {
  position: relative;
  width: 280px;
  height: 280px;
}
.donut-chart {
  width: 100%;
  height: 100%;
}
.donut-center {
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}
.donut-value {
  font-size: 48px;
  font-weight: 600;
  color: #4F30FE;
}
.donut-label {
  font-size: 16px;
  color: rgba(255,255,255,0.5);
  margin-top: 4px;
}
```

---

## 20. Horizontal Bar Chart (CSS)

Simple horizontal bars for comparing values across categories. No SVG needed — pure CSS with width percentages. Visually impactful and easy to read on camera.

Best for: ranking items, comparing quantities, showing scores or performance.

```html
<div class="bar-chart">
  <div class="bar-row">
    <div class="bar-label">[Category 1]</div>
    <div class="bar-track">
      <div class="bar-fill" style="width: 85%; background: linear-gradient(90deg, #4F30FE, #DAB3FF);"></div>
    </div>
    <div class="bar-value">85%</div>
  </div>
  <div class="bar-row">
    <div class="bar-label">[Category 2]</div>
    <div class="bar-track">
      <div class="bar-fill" style="width: 62%; background: linear-gradient(90deg, #4F30FE, #DAB3FF);"></div>
    </div>
    <div class="bar-value">62%</div>
  </div>
  <div class="bar-row">
    <div class="bar-label">[Category 3]</div>
    <div class="bar-track">
      <div class="bar-fill" style="width: 41%; background: linear-gradient(90deg, #4F30FE, #DAB3FF);"></div>
    </div>
    <div class="bar-value">41%</div>
  </div>
</div>
```

```css
.bar-chart {
  display: flex;
  flex-direction: column;
  gap: 18px;
}
.bar-row {
  display: flex;
  align-items: center;
  gap: 16px;
}
.bar-label {
  font-size: 18px;
  font-weight: 600;
  color: rgba(255,255,255,0.8);
  min-width: 160px;
  text-align: right;
}
.bar-track {
  flex: 1;
  height: 28px;
  background: rgba(255,255,255,0.06);
  border-radius: 14px;
  overflow: hidden;
}
.bar-fill {
  height: 100%;
  border-radius: 14px;
  transition: width 0.8s ease;
}
.bar-value {
  font-size: 20px;
  font-weight: 600;
  color: #4F30FE;
  min-width: 60px;
}
```

---

## 21. Gantt Chart

A horizontal timeline-based chart showing tasks/phases with overlapping time bars. Built with CSS grid. Each row is a task, columns represent time periods.

Best for: project timelines, campaign phases, sprint planning, launch schedules.

```html
<div class="gantt">
  <!-- Header: time periods -->
  <div class="gantt-header">
    <div class="gantt-task-col">Task</div>
    <div class="gantt-timeline">
      <div class="gantt-period">Week 1</div>
      <div class="gantt-period">Week 2</div>
      <div class="gantt-period">Week 3</div>
      <div class="gantt-period">Week 4</div>
      <div class="gantt-period">Week 5</div>
      <div class="gantt-period">Week 6</div>
    </div>
  </div>
  <!-- Task rows -->
  <div class="gantt-row">
    <div class="gantt-task-name">[Task 1]</div>
    <div class="gantt-timeline">
      <div class="gantt-bar" style="grid-column: 1 / 3; background: linear-gradient(90deg, #4F30FE, #4840CC);"></div>
    </div>
  </div>
  <div class="gantt-row">
    <div class="gantt-task-name">[Task 2]</div>
    <div class="gantt-timeline">
      <div class="gantt-bar" style="grid-column: 2 / 5; background: linear-gradient(90deg, #DAB3FF, #E5A830);"></div>
    </div>
  </div>
  <div class="gantt-row">
    <div class="gantt-task-name">[Task 3]</div>
    <div class="gantt-timeline">
      <div class="gantt-bar" style="grid-column: 4 / 7; background: linear-gradient(90deg, #4F30FE, #CC1F70);"></div>
    </div>
  </div>
</div>
```

The `grid-column` values control where each bar starts and ends. `1 / 3` means "start at column 1, end before column 3" (spans weeks 1–2). Adjust the total column count to match the number of time periods.

```css
.gantt {
  display: flex;
  flex-direction: column;
  gap: 6px;
}
.gantt-header, .gantt-row {
  display: flex;
  align-items: center;
  gap: 0;
}
.gantt-task-col, .gantt-task-name {
  width: 200px;
  flex-shrink: 0;
  padding: 12px 16px;
  font-size: 16px;
}
.gantt-task-col {
  font-weight: 600;
  color: rgba(255,255,255,0.4);
  text-transform: uppercase;
  font-size: 14px;
  letter-spacing: 1px;
}
.gantt-task-name {
  font-weight: 600;
  color: rgba(255,255,255,0.8);
}
.gantt-timeline {
  flex: 1;
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 2px;
  min-height: 44px;
  align-items: center;
}
.gantt-period {
  font-size: 14px;
  font-weight: 600;
  color: rgba(255,255,255,0.35);
  text-align: center;
  padding: 8px 0;
  border-bottom: 1px solid rgba(79, 48, 254, 0.1);
}
.gantt-bar {
  height: 28px;
  border-radius: 14px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.3);
}
.gantt-row {
  background: rgba(255, 255, 255, 0.03);
  border-radius: 8px;
}
.gantt-row:hover {
  background: rgba(79, 48, 254, 0.05);
}
```

---

## 22. Radial / Circular Diagram (SVG)

A circular layout with items positioned around a center, connected by arcs or lines. Good for showing relationships, ecosystems, or cyclic processes.

Best for: tool ecosystems, process cycles, relationship maps, technology stacks around a core.

```html
<div class="radial-diagram">
  <svg viewBox="0 0 500 500" class="radial-svg">
    <!-- Center circle -->
    <circle cx="250" cy="250" r="60" fill="url(#radial-grad)" />
    <text x="250" y="255" text-anchor="middle" fill="#fff" font-size="18" font-weight="800" font-family="DM Sans">[Core]</text>

    <!-- Connecting lines -->
    <line x1="250" y1="190" x2="250" y2="80" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>
    <line x1="307" y1="217" x2="400" y2="130" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>
    <line x1="310" y1="250" x2="420" y2="250" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>
    <line x1="307" y1="283" x2="400" y2="370" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>
    <line x1="250" y1="310" x2="250" y2="420" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>
    <line x1="193" y1="283" x2="100" y2="370" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>
    <line x1="190" y1="250" x2="80" y2="250" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>
    <line x1="193" y1="217" x2="100" y2="130" stroke="rgba(79,48,254,0.25)" stroke-width="2"/>

    <!-- Outer nodes (positioned at 8 compass points) -->
    <circle cx="250" cy="60" r="36" fill="rgba(16,14,50,0.95)" stroke="#4F30FE" stroke-width="1.5"/>
    <text x="250" y="65" text-anchor="middle" fill="#e8e8e8" font-size="14" font-weight="600" font-family="DM Sans">[Node 1]</text>

    <circle cx="400" cy="115" r="36" fill="rgba(16,14,50,0.95)" stroke="#DAB3FF" stroke-width="1.5"/>
    <text x="400" y="120" text-anchor="middle" fill="#e8e8e8" font-size="14" font-weight="600" font-family="DM Sans">[Node 2]</text>

    <!-- ... repeat for remaining nodes around the circle ... -->

    <defs>
      <linearGradient id="radial-grad" x1="0%" y1="0%" x2="100%" y2="100%">
        <stop offset="0%" stop-color="#4F30FE"/>
        <stop offset="100%" stop-color="#DAB3FF"/>
      </linearGradient>
    </defs>
  </svg>
</div>
```

Position nodes using the circle equation: for N nodes evenly spaced, node i sits at `x = cx + r * cos(2πi/N - π/2)`, `y = cy + r * sin(2πi/N - π/2)` where r is the orbit radius (~190px for a 500x500 viewBox).

```css
.radial-diagram {
  display: flex;
  justify-content: center;
  padding: 20px 0;
}
.radial-svg {
  width: 480px;
  height: 480px;
}
```

---

## 23. Progress Bars

Labeled progress indicators showing completion or skill levels. Simpler than bar charts — used for status dashboards and progress tracking.

Best for: skill levels, project completion, feature readiness, goal tracking.

```html
<div class="progress-list">
  <div class="progress-item">
    <div class="progress-header">
      <div class="progress-name">[Item Name]</div>
      <div class="progress-pct">85%</div>
    </div>
    <div class="progress-track">
      <div class="progress-fill" style="width: 85%;"></div>
    </div>
  </div>
  <!-- more items... -->
</div>
```

```css
.progress-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.progress-item { }
.progress-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 8px;
}
.progress-name {
  font-size: 18px;
  font-weight: 600;
  color: rgba(255,255,255,0.8);
}
.progress-pct {
  font-size: 18px;
  font-weight: 600;
  color: #4F30FE;
}
.progress-track {
  height: 16px;
  background: rgba(255,255,255,0.06);
  border-radius: 8px;
  overflow: hidden;
}
.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #4F30FE, #DAB3FF);
  border-radius: 8px;
}
```

---

## 24. Flowchart

A process diagram with rectangular steps, diamond decision nodes, and directional arrows. Supports branching (yes/no), loops, and parallel paths. Built with inline SVG.

Best for: customer journeys, onboarding flows, approval processes, troubleshooting guides.

**Key elements:** Rounded rectangles for steps, diamond `<polygon>` for decisions, `<line>` or `<path>` for arrows with `marker-end`. Use CSS `stroke-dasharray` + `stroke-dashoffset` animation for flowing dash effect on connections. Add SVG `<filter>` glow on decision nodes.

---

## 25. Network Diagram (D3.js)

A force-directed graph showing relationships between entities. Nodes are draggable. Uses D3.js force simulation (`d3.forceSimulation`, `d3.forceLink`, `d3.forceManyBody`, `d3.forceCollide`).

Best for: tool ecosystems, technology stacks, team collaboration maps, dependency graphs.

**Key setup:** Color-code nodes by group. Size nodes by importance (larger `r` for central nodes). Add SVG glow filter on the primary hub node. Labels positioned below each node.

---

## 26. Block Diagram

A layered system architecture diagram showing components at different levels connected by arrows. Pure SVG with labeled rectangles arranged in horizontal layers.

Best for: SaaS architecture, infrastructure diagrams, data pipeline stacks, microservice layouts.

**Key layout:** Horizontal layers (Client → API → Services → Data). Layer labels on the left. Use different stroke colors per layer. Add `:hover` CSS `drop-shadow` glow on blocks.

---

## 27. Sitemap (D3.js)

A tree diagram showing website page hierarchy. Uses D3.js `d3.tree()` layout. Root node at top with branches expanding downward.

Best for: website structure, content hierarchy, navigation architecture, information taxonomy.

**Key setup:** D3 `d3.hierarchy()` + `d3.tree()`. Curved links via cubic Bézier paths. Purple glow on root node, gold tint on leaf nodes. Node width fixed at ~110px for readable labels.

---

## 28. Organizational Chart (D3.js)

A top-down tree diagram showing team structure with name and title per node. Uses D3.js `d3.tree()` with elbow-style connecting lines.

Best for: company structure, team reporting lines, role hierarchies, department org charts.

**Key setup:** Similar to sitemap but with cards (rect + two text lines: role + name). CEO node gets purple stroke + glow. Department heads get teal. Elbow-style links (horizontal + vertical segments).

---

## 29. Venn Diagram

Overlapping circles showing intersections between 2-3 categories. Pure SVG with semi-transparent fills and labeled regions.

Best for: strategy alignment, skill overlap, market positioning, concept intersections.

**Key layout:** 3 circles offset so they overlap in the center. Use `opacity: 0.8` on circles with colored fills. Center intersection gets a smaller circle with glow filter + pulse animation. Label each region and intersection.

---

## 30. Cycle Diagram

A circular arrangement of stages connected by curved arrows forming a closed loop. Pure SVG.

Best for: continuous improvement, feedback loops, agile sprints, sales funnels, seasonal processes.

**Key layout:** 4 stages (or 3-6) positioned at compass points on a circle. Each stage is a circle with label + subtitle text. Curved arrow paths (`<path>` with quadratic curves) connect each stage to the next with animated dashes. Different accent color per stage.

---

## 31. Hierarchy Pyramid

Stacked trapezoid layers, widest at the bottom, narrowing to a peak. Each layer represents a level. Pure SVG with `<polygon>` elements.

Best for: maturity models, Maslow-style hierarchies, funnel stages, priority levels, organizational tiers.

**Key layout:** 5-7 trapezoid layers calculated with decreasing widths. Top layer gets purple glow filter. Each layer has a centered label + a smaller metric or subtitle. Use gradient colors from muted (bottom) to purple (top).

---

## 32. Quadrant Diagram

A 2-axis matrix with 4 labeled quadrants and positioned data points. Pure SVG.

Best for: prioritization matrices, risk assessments, competitive positioning, strategy maps, Eisenhower matrices.

**Key layout:** Two crossing lines at center forming 4 quadrants. Each quadrant gets a subtle color-tinted background rect. Label quadrants (e.g., "Quick Wins", "Strategic Bets", "Fill-ins", "Avoid"). Position data points as circles with labels. Items in the "best" quadrant get glow effect. Axis labels at ends.

---

## 33. Line Chart (SVG)

An inline SVG line chart for showing trends over time with 1–3 data series. Each series is a `<polyline>` with optional data point dots. Include a legend below.

Best for: trends over time, growth curves, performance tracking, adoption rates, quarter-over-quarter comparison.

```html
<div class="line-chart-container">
  <svg class="line-chart-svg" viewBox="0 0 800 400" xmlns="http://www.w3.org/2000/svg">
    <!-- Grid lines (4-5 horizontal) -->
    <line x1="80" y1="60" x2="760" y2="60" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="130" x2="760" y2="130" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="200" x2="760" y2="200" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="270" x2="760" y2="270" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="340" x2="760" y2="340" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <!-- Y-axis labels -->
    <text x="70" y="65" text-anchor="end" fill="rgba(255,255,255,0.5)" font-size="14" font-family="DM Sans">[Max]</text>
    <text x="70" y="205" text-anchor="end" fill="rgba(255,255,255,0.5)" font-size="14" font-family="DM Sans">[Mid]</text>
    <text x="70" y="345" text-anchor="end" fill="rgba(255,255,255,0.5)" font-size="14" font-family="DM Sans">[Min]</text>
    <!-- X-axis labels -->
    <text x="[x]" y="375" text-anchor="middle" fill="rgba(255,255,255,0.5)" font-size="14" font-family="DM Sans">[Label]</text>
    <!-- Line 1 -->
    <polyline points="[x1,y1 x2,y2 ...]"
      fill="none" stroke="#4F30FE" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
    <circle cx="[x1]" cy="[y1]" r="5" fill="#4F30FE"/>
    <!-- Line 2 (optional) -->
    <polyline points="[...]"
      fill="none" stroke="#DAB3FF" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
    <!-- Line 3 (optional) -->
    <polyline points="[...]"
      fill="none" stroke="#4F30FE" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>
  <div class="line-chart-legend">
    <div class="legend-item"><div class="legend-dot" style="background:#4F30FE;"></div><span>[Series 1]</span></div>
    <div class="legend-item"><div class="legend-dot" style="background:#DAB3FF;"></div><span>[Series 2]</span></div>
  </div>
</div>
```

**How to calculate Y positions:** The chart area runs from y=60 (top, max value) to y=340 (bottom, zero/min). For a value as a percentage of the range: `y = 340 - (percentage * 280)`. For example, 50% = `340 - 140 = 200`.

**X positions:** Distribute data points evenly between x=80 and x=760. For N points: spacing = `680 / (N - 1)`, first point at x = `80 + spacing/2` or x=80.

```css
.line-chart-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
}
.line-chart-svg {
  width: 100%;
  max-width: 800px;
}
.line-chart-legend {
  display: flex;
  gap: 32px;
  justify-content: center;
}
```

---

## 34. Area Chart (SVG)

An inline SVG area chart — like a line chart but with a filled region below each line extending to the baseline. Uses `<polygon>` for the filled area and `<polyline>` for the top edge. Multiple areas are layered with low opacity so they don't occlude each other.

Best for: volume over time, cumulative data, market size evolution, user growth, revenue trends.

```html
<div class="area-chart-container">
  <svg class="area-chart-svg" viewBox="0 0 800 400" xmlns="http://www.w3.org/2000/svg">
    <!-- Grid lines (same as line chart) -->
    <line x1="80" y1="60" x2="760" y2="60" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="130" x2="760" y2="130" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="200" x2="760" y2="200" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="270" x2="760" y2="270" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="340" x2="760" y2="340" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <!-- Y-axis and X-axis labels (same pattern as line chart) -->
    <!-- Area 1 (paint largest/back area first) -->
    <polygon points="[x1,y1 x2,y2 ... xN,yN xN,340 x1,340]"
      fill="#4F30FE" opacity="0.15"/>
    <polyline points="[x1,y1 x2,y2 ... xN,yN]"
      fill="none" stroke="#4F30FE" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    <!-- Area 2 (paint smaller/front area second) -->
    <polygon points="[x1,y1 x2,y2 ... xN,yN xN,340 x1,340]"
      fill="#DAB3FF" opacity="0.15"/>
    <polyline points="[x1,y1 x2,y2 ... xN,yN]"
      fill="none" stroke="#DAB3FF" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>
  <div class="area-chart-legend">
    <div class="legend-item"><div class="legend-dot" style="background:#4F30FE;"></div><span>[Series 1]</span></div>
    <div class="legend-item"><div class="legend-dot" style="background:#DAB3FF;"></div><span>[Series 2]</span></div>
  </div>
</div>
```

**How to build the polygon:** Take the same polyline points for the top edge, then append `xN,340 x1,340` to close the shape down to the baseline (y=340). Paint the largest area first so smaller areas render on top.

```css
.area-chart-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
}
.area-chart-svg {
  width: 100%;
  max-width: 800px;
}
.area-chart-legend {
  display: flex;
  gap: 32px;
  justify-content: center;
}
```

---

## 35. Column Chart (SVG)

Vertical bars for comparing categories. Each column is an SVG `<rect>` with rounded top corners and a purple-to-blue gradient fill. Value labels sit above each bar.

Best for: comparing categories, revenue by department, scores by team, quarterly figures.

```html
<div class="column-chart-container">
  <svg class="column-chart-svg" viewBox="0 0 800 400" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient id="col-grad" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#4F30FE"/>
        <stop offset="100%" stop-color="#DAB3FF"/>
      </linearGradient>
    </defs>
    <!-- Grid lines -->
    <line x1="80" y1="60" x2="760" y2="60" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="130" x2="760" y2="130" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="200" x2="760" y2="200" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="270" x2="760" y2="270" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <line x1="80" y1="340" x2="760" y2="340" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <!-- Y-axis labels -->
    <text x="70" y="65" text-anchor="end" fill="rgba(255,255,255,0.5)" font-size="14" font-family="DM Sans">[Max]</text>
    <text x="70" y="345" text-anchor="end" fill="rgba(255,255,255,0.5)" font-size="14" font-family="DM Sans">[Min]</text>
    <!-- Column: value label above, rect bar, category label below -->
    <rect x="[x]" y="[top]" width="50" height="[height]" rx="6" fill="url(#col-grad)"/>
    <text x="[center]" y="[top - 12]" text-anchor="middle" fill="#4F30FE" font-size="16" font-weight="700" font-family="DM Sans">[Value]</text>
    <text x="[center]" y="370" text-anchor="middle" fill="rgba(255,255,255,0.5)" font-size="14" font-family="DM Sans">[Category]</text>
    <!-- Repeat for each category -->
  </svg>
</div>
```

**How to calculate columns:** The chart area runs from y=60 (top) to y=340 (bottom), giving 280px of vertical range. For each value: `height = (value / maxValue) * 280`, `top = 340 - height`. Space columns evenly across the 680px horizontal range (x=80 to x=760). Bar width of 50px works well for 4–8 categories.

**Grouped columns:** For multi-series data, place 2–3 narrower bars (width 30px) side by side per category, each with a different fill color (`#4F30FE`, `#DAB3FF`, `#4F30FE`). Add a legend below using the standard `.legend-item` pattern.

```css
.column-chart-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
}
.column-chart-svg {
  width: 100%;
  max-width: 800px;
}
```

---

## 36. Agenda/Outline Slide

A full-viewport slide showing a numbered list of topics or sections with optional time markers. Used at the start of YouTube videos, webinars, and presentations to set expectations. The numbered items feature purple badges and clean vertical spacing.

```html
<section class="agenda-slide">
  <div class="section-label">WHAT WE'LL COVER</div>
  <h2 class="agenda-title">[Agenda Title]</h2>
  <div class="agenda-list">
    <div class="agenda-item">
      <div class="agenda-number">1</div>
      <div class="agenda-item-content">
        <div class="agenda-item-title">[Topic Title]</div>
        <div class="agenda-item-desc">[Optional description of this topic]</div>
      </div>
      <div class="agenda-item-time">[~5 min]</div>
    </div>
    <div class="agenda-divider"></div>
    <div class="agenda-item">
      <div class="agenda-number">2</div>
      <div class="agenda-item-content">
        <div class="agenda-item-title">[Topic Title]</div>
        <div class="agenda-item-desc">[Optional description]</div>
      </div>
      <div class="agenda-item-time">[~10 min]</div>
    </div>
    <div class="agenda-divider"></div>
    <div class="agenda-item">
      <div class="agenda-number">3</div>
      <div class="agenda-item-content">
        <div class="agenda-item-title">[Topic Title]</div>
      </div>
      <div class="agenda-item-time">[~8 min]</div>
    </div>
    <div class="agenda-divider"></div>
    <div class="agenda-item">
      <div class="agenda-number">4</div>
      <div class="agenda-item-content">
        <div class="agenda-item-title">[Topic Title]</div>
        <div class="agenda-item-desc">[Optional description]</div>
      </div>
      <div class="agenda-item-time">[~7 min]</div>
    </div>
  </div>
</section>
```

```css
.agenda-slide {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 40px;
}
.agenda-title {
  font-size: 44px;
  font-weight: 600;
  color: #fff;
  margin-bottom: 48px;
  line-height: 1.2;
}
.agenda-list {
  display: flex;
  flex-direction: column;
  gap: 0;
  width: 100%;
  max-width: 720px;
  text-align: left;
}
.agenda-item {
  display: flex;
  align-items: center;
  gap: 20px;
  padding: 20px 0;
}
.agenda-number {
  width: 44px;
  height: 44px;
  border-radius: 12px;
  background: rgba(79, 48, 254, 0.15);
  color: #4F30FE;
  font-size: 20px;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}
.agenda-item-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.agenda-item-title {
  font-size: 22px;
  font-weight: 600;
  color: #fff;
}
.agenda-item-desc {
  font-size: 16px;
  color: rgba(255,255,255,0.5);
  line-height: 1.5;
}
.agenda-item-time {
  font-size: 15px;
  font-weight: 600;
  color: rgba(255,255,255,0.4);
  white-space: nowrap;
  flex-shrink: 0;
}
.agenda-divider {
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(79,48,254,0.15), transparent);
}
```

---

## 37. Section Header Slide

A full-viewport "chapter title card" for major transitions between sections. Unlike the thin Section Divider (#16), this is a full-screen pause moment. Sits directly on the parallax background with no card container.

```html
<section class="section-header-slide">
  <div class="section-header-number">02</div>
  <h2 class="section-header-title">[Section Title]</h2>
  <div class="section-header-rule"></div>
  <p class="section-header-subtitle">[Optional subtitle or teaser sentence]</p>
</section>
```

```css
.section-header-slide {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 40px;
}
.section-header-number {
  font-size: 18px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 3px;
  color: #4F30FE;
  margin-bottom: 20px;
  padding: 8px 20px;
  border: 1px solid rgba(79, 48, 254, 0.25);
  border-radius: 8px;
}
.section-header-title {
  font-size: 56px;
  font-weight: 600;
  color: #fff;
  line-height: 1.15;
  margin-bottom: 24px;
  max-width: 900px;
}
.section-header-rule {
  width: 120px;
  height: 3px;
  background: linear-gradient(90deg, #4F30FE, #DAB3FF);
  border-radius: 2px;
  margin-bottom: 24px;
}
.section-header-subtitle {
  font-size: 24px;
  color: rgba(255,255,255,0.6);
  line-height: 1.5;
  max-width: 650px;
}
```

---

## 38. Title + Content Split Slide

A two-column "workhorse" layout: the left column carries the heading and text or bullet list, the right column holds a visual placeholder (image, screenshot, diagram). Use this whenever you need a heading paired with an illustration.

```html
<section class="section">
  <div class="split-slide">
    <div class="split-left">
      <div class="section-label">[CATEGORY LABEL]</div>
      <h3 class="split-title">[Heading]</h3>
      <p class="split-body">[Body paragraph text explaining the concept. Can be 2-3 sentences.]</p>
      <ul class="split-bullets">
        <li class="split-bullet-item">[Bullet point one]</li>
        <li class="split-bullet-item">[Bullet point two]</li>
        <li class="split-bullet-item">[Bullet point three]</li>
      </ul>
    </div>
    <div class="split-right">
      <div class="split-visual-placeholder">
        <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="6" y="6" width="36" height="36" rx="4" stroke="rgba(255,255,255,0.3)" stroke-width="2" fill="none"/>
          <path d="M6 34 L18 22 L26 30 L34 18 L42 26" stroke="rgba(255,255,255,0.3)" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
          <circle cx="32" cy="16" r="4" fill="rgba(255,255,255,0.2)"/>
        </svg>
        <span class="split-visual-label">Image / Visual</span>
      </div>
    </div>
  </div>
</section>
```

```css
.split-slide {
  display: grid;
  grid-template-columns: 55% 45%;
  gap: 40px;
  align-items: center;
}
.split-left {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.split-title {
  font-size: 32px;
  font-weight: 600;
  color: #fff;
  line-height: 1.25;
  margin-bottom: 8px;
}
.split-body {
  font-size: 18px;
  color: rgba(255,255,255,0.65);
  line-height: 1.65;
  margin-bottom: 8px;
}
.split-bullets {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.split-bullet-item {
  font-size: 18px;
  color: rgba(255,255,255,0.7);
  padding-left: 22px;
  position: relative;
  line-height: 1.5;
}
.split-bullet-item::before {
  content: '';
  position: absolute;
  left: 0;
  top: 10px;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #4F30FE;
}
.split-right {
  display: flex;
  align-items: center;
  justify-content: center;
}
.split-visual-placeholder {
  width: 100%;
  aspect-ratio: 4 / 3;
  border: 2px dashed rgba(79, 48, 254, 0.25);
  border-radius: 14px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
  background: rgba(20, 18, 60, 0.5);
}
.split-visual-label {
  font-size: 15px;
  color: rgba(255,255,255,0.3);
  font-weight: 600;
}
```

---

## 39. Summary/Recap Slide

A grid of key takeaways with checkmark icons. Used near the end of a presentation to recap the main points. Supports an optional "bottom line" callout.

```html
<section class="section">
  <div class="section-label">KEY TAKEAWAYS</div>
  <h2 class="section-title">[Recap Title]</h2>
  <div class="recap-grid">
    <div class="recap-item">
      <div class="recap-check">&#10003;</div>
      <div class="recap-item-content">
        <div class="recap-item-title">[Takeaway Title]</div>
        <div class="recap-item-desc">[Short description of this takeaway]</div>
      </div>
    </div>
    <div class="recap-item">
      <div class="recap-check">&#10003;</div>
      <div class="recap-item-content">
        <div class="recap-item-title">[Takeaway Title]</div>
        <div class="recap-item-desc">[Short description of this takeaway]</div>
      </div>
    </div>
    <div class="recap-item">
      <div class="recap-check">&#10003;</div>
      <div class="recap-item-content">
        <div class="recap-item-title">[Takeaway Title]</div>
        <div class="recap-item-desc">[Short description of this takeaway]</div>
      </div>
    </div>
    <div class="recap-item">
      <div class="recap-check">&#10003;</div>
      <div class="recap-item-content">
        <div class="recap-item-title">[Takeaway Title]</div>
        <div class="recap-item-desc">[Short description of this takeaway]</div>
      </div>
    </div>
  </div>
  <div class="recap-bottomline">
    <div class="recap-bottomline-label">THE BOTTOM LINE</div>
    <div class="recap-bottomline-text">[One-sentence summary of the entire presentation]</div>
  </div>
</section>
```

```css
.recap-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  margin-bottom: 28px;
}
.recap-item {
  display: flex;
  align-items: flex-start;
  gap: 16px;
  padding: 22px;
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 14px;
}
.recap-check {
  width: 36px;
  height: 36px;
  border-radius: 10px;
  background: rgba(218, 179, 255, 0.2);
  color: #4CAF50;
  font-size: 18px;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}
.recap-item-content {
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.recap-item-title {
  font-size: 20px;
  font-weight: 600;
  color: #fff;
}
.recap-item-desc {
  font-size: 16px;
  color: rgba(255,255,255,0.5);
  line-height: 1.5;
}
.recap-bottomline {
  padding: 24px 28px;
  background: rgba(79, 48, 254, 0.08);
  border: 1px solid rgba(79, 48, 254, 0.2);
  border-radius: 14px;
  text-align: center;
}
.recap-bottomline-label {
  font-size: 14px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  color: #4F30FE;
  margin-bottom: 8px;
}
.recap-bottomline-text {
  font-size: 20px;
  color: rgba(255,255,255,0.8);
  line-height: 1.5;
  max-width: 700px;
  margin: 0 auto;
}
```

---

## 40. Testimonial Wall

A grid of short testimonial cards for social proof. Each card includes a quote, person name, role, and optional star rating.

```html
<section class="section">
  <div class="section-label">WHAT OTHERS SAY</div>
  <h2 class="section-title">[Social Proof Title]</h2>
  <div class="testimonial-grid">
    <div class="testimonial-card">
      <div class="testimonial-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
      <div class="testimonial-quote">"[Testimonial quote text goes here. Keep it to 1-3 sentences for readability.]"</div>
      <div class="testimonial-author">
        <div class="testimonial-name">[Person Name]</div>
        <div class="testimonial-role">[Role / Title / Company]</div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="testimonial-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
      <div class="testimonial-quote">"[Testimonial quote text.]"</div>
      <div class="testimonial-author">
        <div class="testimonial-name">[Person Name]</div>
        <div class="testimonial-role">[Role / Title]</div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="testimonial-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
      <div class="testimonial-quote">"[Testimonial quote text.]"</div>
      <div class="testimonial-author">
        <div class="testimonial-name">[Person Name]</div>
        <div class="testimonial-role">[Role / Title]</div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="testimonial-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
      <div class="testimonial-quote">"[Testimonial quote text.]"</div>
      <div class="testimonial-author">
        <div class="testimonial-name">[Person Name]</div>
        <div class="testimonial-role">[Role / Title]</div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="testimonial-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
      <div class="testimonial-quote">"[Testimonial quote text.]"</div>
      <div class="testimonial-author">
        <div class="testimonial-name">[Person Name]</div>
        <div class="testimonial-role">[Role / Title]</div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="testimonial-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
      <div class="testimonial-quote">"[Testimonial quote text.]"</div>
      <div class="testimonial-author">
        <div class="testimonial-name">[Person Name]</div>
        <div class="testimonial-role">[Role / Title]</div>
      </div>
    </div>
  </div>
</section>
```

```css
.testimonial-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
.testimonial-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(79, 48, 254, 0.1);
  border-radius: 14px;
  padding: 26px 24px;
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.testimonial-stars {
  font-size: 18px;
  color: #4F30FE;
  letter-spacing: 2px;
}
.testimonial-quote {
  font-size: 17px;
  color: rgba(255,255,255,0.7);
  line-height: 1.6;
  font-style: italic;
  flex: 1;
}
.testimonial-author {
  display: flex;
  flex-direction: column;
  gap: 2px;
  padding-top: 12px;
  border-top: 1px solid rgba(79, 48, 254, 0.1);
}
.testimonial-name {
  font-size: 17px;
  font-weight: 600;
  color: #4F30FE;
}
.testimonial-role {
  font-size: 14px;
  color: rgba(255,255,255,0.4);
}
```

---

## 41. Offer Stack Slide

A value-stack layout for VSL and webinar offers. Lists each deliverable with its perceived value, then contrasts the total value against the actual price. The purple border accent reinforces premium positioning.

```html
<section class="offer-stack-section">
  <div class="section-label">EVERYTHING YOU GET</div>
  <h2 class="section-title">[Offer Title]</h2>
  <div class="offer-stack">
    <div class="offer-item">
      <div class="offer-item-info">
        <div class="offer-item-name">[Item Name]</div>
        <div class="offer-item-desc">[Brief description of what this includes]</div>
      </div>
      <div class="offer-item-value"><del>$997 Value</del></div>
    </div>
    <div class="offer-item-divider"></div>
    <div class="offer-item">
      <div class="offer-item-info">
        <div class="offer-item-name">[Item Name]</div>
        <div class="offer-item-desc">[Brief description]</div>
      </div>
      <div class="offer-item-value"><del>$497 Value</del></div>
    </div>
    <div class="offer-item-divider"></div>
    <div class="offer-item">
      <div class="offer-item-info">
        <div class="offer-item-name">[Item Name]</div>
        <div class="offer-item-desc">[Brief description]</div>
      </div>
      <div class="offer-item-value"><del>$297 Value</del></div>
    </div>
    <div class="offer-item-divider"></div>
    <div class="offer-item">
      <div class="offer-item-info">
        <div class="offer-item-name">[Bonus Item]</div>
        <div class="offer-item-desc">[Brief description]</div>
      </div>
      <div class="offer-item-value"><del>$197 Value</del></div>
    </div>
    <div class="offer-total">
      <div class="offer-total-row">
        <span class="offer-total-label">Total Value:</span>
        <span class="offer-total-crossed"><del>$1,988</del></span>
      </div>
      <div class="offer-price-row">
        <span class="offer-price-label">Your Investment:</span>
        <span class="offer-price">$497</span>
      </div>
    </div>
  </div>
</section>
```

```css
.offer-stack-section {
  background: rgba(255, 255, 255, 0.06);
  border-radius: 16px;
  padding: 40px 44px;
  border: 1px solid rgba(79, 48, 254, 0.3);
  margin-bottom: 40px;
}
.offer-stack {
  display: flex;
  flex-direction: column;
  gap: 0;
}
.offer-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 0;
}
.offer-item-info {
  display: flex;
  flex-direction: column;
  gap: 4px;
  flex: 1;
}
.offer-item-name {
  font-size: 20px;
  font-weight: 600;
  color: #fff;
}
.offer-item-desc {
  font-size: 16px;
  color: rgba(255,255,255,0.5);
  line-height: 1.5;
}
.offer-item-value {
  font-size: 18px;
  font-weight: 600;
  color: rgba(255,255,255,0.4);
  white-space: nowrap;
  flex-shrink: 0;
  margin-left: 24px;
}
.offer-item-value del {
  text-decoration: line-through;
}
.offer-item-divider {
  height: 1px;
  background: rgba(79, 48, 254, 0.12);
}
.offer-total {
  margin-top: 8px;
  padding-top: 24px;
  border-top: 2px solid rgba(79, 48, 254, 0.25);
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: flex-end;
}
.offer-total-row {
  display: flex;
  align-items: center;
  gap: 12px;
}
.offer-total-label {
  font-size: 18px;
  color: rgba(255,255,255,0.5);
  font-weight: 600;
}
.offer-total-crossed {
  font-size: 22px;
  color: rgba(255,255,255,0.35);
}
.offer-total-crossed del {
  text-decoration: line-through;
}
.offer-price-row {
  display: flex;
  align-items: center;
  gap: 12px;
}
.offer-price-label {
  font-size: 20px;
  color: rgba(255,255,255,0.7);
  font-weight: 600;
}
.offer-price {
  font-size: 44px;
  font-weight: 600;
  color: #4F30FE;
}
```

---

## 42. Guarantee Badge Slide

A centered guarantee statement with a shield icon. Full-viewport layout that sits directly on the parallax background with no card container. Builds trust and reduces purchase anxiety.

```html
<section class="guarantee-slide">
  <div class="guarantee-shield">
    <svg width="120" height="120" viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M60 10 L105 30 L105 65 C105 90 85 110 60 115 C35 110 15 90 15 65 L15 30 Z"
        stroke="#4F30FE" stroke-width="3" fill="rgba(79, 48, 254, 0.06)" stroke-linejoin="round"/>
      <path d="M42 62 L54 74 L78 50" stroke="#4F30FE" stroke-width="4" fill="none"
        stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
  </div>
  <h2 class="guarantee-title">[30-Day Money-Back Guarantee]</h2>
  <p class="guarantee-desc">[If you're not completely satisfied within 30 days, we'll refund every penny. No questions asked.]</p>
</section>
```

```css
.guarantee-slide {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 40px;
}
.guarantee-shield {
  margin-bottom: 32px;
}
.guarantee-title {
  font-size: 36px;
  font-weight: 600;
  color: #fff;
  margin-bottom: 16px;
  line-height: 1.25;
  max-width: 700px;
}
.guarantee-desc {
  font-size: 20px;
  color: rgba(255,255,255,0.6);
  line-height: 1.6;
  max-width: 600px;
}
```

---

## 43. Emotional Contrast Slide

A two-panel "Without vs. With" comparison that highlights pain points on the left and benefits on the right. The red/gold tinting creates an immediate emotional contrast. Wrapped in a card background container.

```html
<section class="section">
  <div class="contrast-grid">
    <div class="contrast-panel contrast-without">
      <div class="contrast-header contrast-header-negative">Without [Product]</div>
      <ul class="contrast-list">
        <li class="contrast-list-item">
          <span class="contrast-icon-x">&#10007;</span>
          <span class="contrast-text">[Pain point or negative outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-x">&#10007;</span>
          <span class="contrast-text">[Pain point or negative outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-x">&#10007;</span>
          <span class="contrast-text">[Pain point or negative outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-x">&#10007;</span>
          <span class="contrast-text">[Pain point or negative outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-x">&#10007;</span>
          <span class="contrast-text">[Pain point or negative outcome]</span>
        </li>
      </ul>
    </div>
    <div class="contrast-panel contrast-with">
      <div class="contrast-header contrast-header-positive">With [Product]</div>
      <ul class="contrast-list">
        <li class="contrast-list-item">
          <span class="contrast-icon-check">&#10003;</span>
          <span class="contrast-text">[Benefit or positive outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-check">&#10003;</span>
          <span class="contrast-text">[Benefit or positive outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-check">&#10003;</span>
          <span class="contrast-text">[Benefit or positive outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-check">&#10003;</span>
          <span class="contrast-text">[Benefit or positive outcome]</span>
        </li>
        <li class="contrast-list-item">
          <span class="contrast-icon-check">&#10003;</span>
          <span class="contrast-text">[Benefit or positive outcome]</span>
        </li>
      </ul>
    </div>
  </div>
</section>
```

```css
.contrast-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}
.contrast-panel {
  border-radius: 14px;
  padding: 28px;
}
.contrast-without {
  background: rgba(255, 70, 46, 0.1);
  border: 1px solid rgba(255, 70, 46, 0.3);
}
.contrast-with {
  background: rgba(218, 179, 255, 0.1);
  border: 1px solid rgba(218, 179, 255, 0.3);
}
.contrast-header {
  font-size: 22px;
  font-weight: 600;
  margin-bottom: 20px;
  padding-bottom: 14px;
  border-bottom: 1px solid rgba(255,255,255,0.08);
}
.contrast-header-negative {
  color: #ff462e;
}
.contrast-header-positive {
  color: #4CAF50;
}
.contrast-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.contrast-list-item {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  font-size: 18px;
  line-height: 1.5;
}
.contrast-icon-x {
  color: #ff462e;
  font-size: 18px;
  font-weight: 600;
  flex-shrink: 0;
  width: 24px;
  text-align: center;
}
.contrast-icon-check {
  color: #4CAF50;
  font-size: 18px;
  font-weight: 600;
  flex-shrink: 0;
  width: 24px;
  text-align: center;
}
.contrast-text {
  color: rgba(255,255,255,0.7);
}
```
