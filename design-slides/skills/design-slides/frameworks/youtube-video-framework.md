# YouTube Video Slide Framework

---

## 1. Scope Statement

This framework applies to **educational and tutorial YouTube videos** delivered as screen-recorded scrollable HTML pages. Each page is a single long-scroll document designed for 1920x1080 recording, where the creator scrolls through visual sections while narrating.

**In scope:** Tutorials, walkthroughs, strategy breakdowns, framework explanations, tool reviews, case studies, rankings, and any educational content presented as a scrollable visual page.

**Out of scope:** Sales pages, landing pages, webinar presentations, VSLs, talking-head videos without visual slides.

---

## 2. Section Structure

Every YouTube video page follows this fixed structure:

| # | Section | Required? | Source |
|---|---------|-----------|--------|
| 1 | Hero | Always first | Generated per video topic |
| 2 | About Me | Always second | Copy from `templates/sections/about-me.html` |
| 3-N | Topic Sections | Variable (from approved visual outline) | Generated per video topic |
| Last | Your Next Step | Always last | Copy from `templates/sections/next-step-youtube.html` |

### Section Rules

- **Hero** is always the first section. Contains the video title, subtitle, and logo. Sets the topic and hooks the viewer.
- **About Me** is always the second section. Establishes credibility before diving into content. Copy directly from `templates/sections/about-me.html` -- do not rewrite or modify.
- **Topic Sections** come from the approved visual outline (Phase 1 output). Each section maps to one component from the component library.
- **Your Next Step** is always the last section. Contains the YouTube-specific CTA (subscribe, like, related video links). Copy directly from `templates/sections/next-step-youtube.html` -- do not rewrite or modify.

### What NOT to Include

- No Nav Bar (this is a video, not a website)
- No Pricing sections
- No FAQ sections
- No Footer
- No opt-in forms

---

## 3. Section Count Guidance

Section count scales with video length. Use this as a guide:

| Video Length | Estimated Sections (including Hero, About Me, Next Step) | Topic Sections Only |
|-------------|----------------------------------------------------------|---------------------|
| 5 min | 5-7 | 2-4 |
| 10 min | 8-12 | 5-9 |
| 15 min | 10-14 | 7-11 |
| 20 min | 12-18 | 9-15 |
| 30 min | 16-22 | 13-19 |

**Rule of thumb:** 1 topic section per 1-2 minutes of video. Dense technical content (code walkthroughs, complex diagrams) needs more time per section. Conceptual content (strategy, frameworks) moves faster.

---

## 4. Required Fixed Sections

These sections are non-negotiable and must appear in every YouTube video page:

### About Me (Section 2 -- always)
- **Source:** `templates/sections/about-me.html`
- **Purpose:** Quick credibility establishment. The viewer needs to know why they should listen.
- **Rules:** Copy as-is. Do not rewrite, restyle, or remove elements.

### YouTube Next Step CTA (Last Section -- always)
- **Source:** `templates/sections/next-step-youtube.html`
- **Purpose:** Drive subscriptions, likes, and traffic to the next video.
- **Rules:** Copy as-is. Do not rewrite, restyle, or remove elements.

---

## 5. Tone & Visual Philosophy

- **Educational, clear, visual-first.** Every section should lead with a visual element (diagram, chart, grid, flow), not a wall of text.
- **Show, don't tell.** If something can be a diagram, make it a diagram. If something can be a comparison grid, make it a grid. Text is narrated -- the page is for visuals.
- **Readability at 1080p.** No text smaller than 14px. Prefer 20px+ for body content. The viewer is watching a compressed YouTube video, not reading a webpage up close.
- **One idea per section.** Each section should communicate one concept clearly. If a section needs to cover multiple sub-ideas, use a component that structures them (Card Grid, Icon Grid, Step Sequence).
- **Generous whitespace.** Sections should breathe. The creator scrolls at a natural pace -- cramped sections scroll past too quickly.

---

## 6. Component Affinity Table

Use this table to select the right component for each topic section. Match the content type to the recommended components.

### By Content Type

| Content Type | Primary Components | Secondary Components |
|-------------|-------------------|---------------------|
| **Tutorials / How-to** | Step Sequence, Code Block, Flow Diagram | Callout Box, Icon Grid |
| **Strategy / Framework** | Mind Map, Hierarchy Pyramid, Comparison Grid | Flowchart, Block Diagram, Quadrant Diagram |
| **Case Studies** | Before/After, Stat Cards, Timeline | Quote Block, Bar Chart, Line Chart |
| **Tool Reviews** | Comparison Grid, Icon Grid, Pricing Table | Stat Cards, Before/After, Progress Bars |
| **Lists / Rankings** | Card Grid, Icon Grid, Horizontal Bar Chart | Stat Cards, Step Sequence |
| **Architecture / Systems** | Block Diagram, Network Diagram, Flowchart | Flow Diagram, Sitemap, Cycle Diagram |
| **Data / Analytics** | Stat Cards, Bar Chart, Pie Chart, Line Chart | Donut Chart, Area Chart, Column Chart |
| **Processes / Workflows** | Flow Diagram, Step Sequence, Gantt Chart | Timeline, Cycle Diagram, Flowchart |
| **Comparisons** | Comparison Grid, Before/After, Quadrant Diagram | Stat Cards, Horizontal Bar Chart |
| **Concepts / Theory** | Mind Map, Venn Diagram, Hierarchy Pyramid | Callout Box, Block Diagram, Radial Diagram |

### By Component (Reverse Lookup)

| Component | Best Used For |
|-----------|--------------|
| Hero Section | Opening slide -- every video |
| Section Container | Wrapping any topic section with a heading |
| Flow Diagram / Node Row | Linear processes, data pipelines, automation chains |
| Card Grid | Multi-item overviews, feature lists, tool collections |
| Comparison Grid | Side-by-side evaluation of 2-4 options |
| Stat Cards | Key metrics, results, performance numbers |
| Timeline | Chronological events, project phases, history |
| Before/After | Transformation results, improvement comparisons |
| Step Sequence | Numbered instructions, ordered processes |
| Icon Grid | Feature overviews, benefit lists, tool ecosystems |
| Callout Box | Key takeaways, warnings, important notes |
| Quote Block | Testimonials, expert quotes, key principles |
| Pricing Table | Cost comparisons, plan breakdowns |
| Mind Map | Topic overviews, brainstorms, concept relationships |
| Code Block | Code examples, configurations, technical snippets |
| Hierarchy Pyramid | Priority levels, maturity models, tiered systems |
| Quadrant Diagram | 2x2 analysis, strategic positioning |
| Flowchart | Decision trees, conditional logic, process routing |
| Block Diagram | System architecture, module relationships |
| Cycle Diagram | Recurring processes, feedback loops |
| Venn Diagram | Overlapping concepts, shared characteristics |
| Pie / Donut Chart | Proportion breakdowns, market share |
| Bar / Column Chart | Quantity comparisons, performance metrics |
| Line / Area Chart | Trends over time, growth trajectories |
| Progress Bars | Completion status, skill levels, scoring |
| Gantt Chart | Project timelines, parallel workstreams |
| Network Diagram | Complex interconnections, system maps |
| Radial Diagram | Multi-axis evaluation, feature scoring |

---

## 7. Phase 1 Outline Format

Before building the HTML page, produce a **Visual Outline** for approval. The outline is a numbered list where each entry specifies the section name and its mapped component.

### Format

```
VISUAL OUTLINE: [Video Title]
Estimated sections: [N] (for ~[X] min video)

1. Hero — Component: Hero Section — [Title with subtitle description]
2. About Me — Component: About Me (from template) — [Brief note: copied from templates/sections/about-me.html]
3. [Section Name] — Component: [Component Name] — [What this section shows]
4. [Section Name] — Component: [Component Name] — [What this section shows]
...
N. Your Next Step — Component: YouTube Next Step CTA (from template) — [Brief note: copied from templates/sections/next-step-youtube.html]
```

### Rules for Outline Creation

1. Every outline starts with Hero and ends with Your Next Step.
2. About Me is always section 2.
3. Each topic section maps to exactly one primary component from the component library.
4. Section names should be clear and descriptive (the viewer never sees them -- they're for production reference).
5. The component choice should match the content type (use the affinity table above).
6. Include a brief description of what the section visualizes.
7. The section count should match the video length guidance.

---

## 8. Example Outline

```
VISUAL OUTLINE: n8n Master Workflow Architecture
Estimated sections: 8 (for ~12 min video)

1. Hero — Component: Hero Section — Title with subtitle about automating promo campaigns
2. About Me — Component: About Me (from template) — Copied from templates/sections/about-me.html
3. The Architecture Decision — Component: Comparison Grid (3 columns) — Three approaches compared: manual, basic automation, master workflow
4. Master Workflow Overview — Component: Flow Diagram — End-to-end flow from trigger through processing to output
5. The Trigger Layer — Component: Block Diagram — Webhook, schedule, and manual trigger options with routing
6. Content Processing Engine — Component: Step Sequence — 5-step content transformation pipeline
7. Multi-Channel Distribution — Component: Card Grid (4 cards) — Email, social, CRM, and analytics output channels
8. Results & Performance — Component: Stat Cards (4 stats) — Time saved, error reduction, campaigns processed, ROI
9. Your Next Step — Component: YouTube Next Step CTA (from template) — Copied from templates/sections/next-step-youtube.html
```

---

## 9. Build Rules

When converting an approved outline into an HTML page:

1. **Use the component library exactly.** Copy the HTML/CSS pattern from `components/components.md` and adapt the content. Do not invent new component styles.
2. **Use the brand specification exactly.** All colors, fonts, spacing, and surface treatments come from `brand/brand.md`.
3. **Copy fixed sections verbatim.** About Me and Your Next Step come from their template files unchanged.
4. **One continuous HTML file.** The entire page is a single `.html` file with all CSS inline or in a `<style>` block. No external stylesheets (except Google Fonts).
5. **Background layer is global.** The background image and overlay from `brand/brand.md` apply to the entire page, not per-section.
6. **Sections stack vertically.** Each section is a full-width block inside the `.page-wrapper`. Vertical gap between sections: 80-100px.
7. **Section dividers are optional.** Use the Section Divider component between major topic shifts, not between every section.
8. **Responsive is irrelevant.** This page is only ever viewed at 1920x1080 in a screen recording. Do not add responsive breakpoints or mobile considerations.
