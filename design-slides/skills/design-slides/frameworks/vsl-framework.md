# VSL (Video Sales Letter) Slide Framework

---

## 1. Scope Statement

This framework applies to **Video Sales Letters** -- persuasion-focused, single-offer presentations designed for screen recording. A VSL is not an educational video. It has one job: move the viewer from problem-aware to purchase-ready in a tight, emotionally structured sequence.

**In scope:** Product launches, course sales, service offers, digital product pitches, high-ticket program sales -- any single-offer video presentation that follows the Problem-Agitation-Solution-Offer structure.

**Out of scope:** YouTube tutorials, webinar presentations, educational content, multi-product showcases, brand videos.

---

## 2. Section Structure

A VSL follows a strict 9-section persuasion arc. The order is non-negotiable.

| # | Section | Purpose | Recommended Components |
|---|---------|---------|----------------------|
| 1 | Hero | Benefit-focused headline, big promise | Hero Section |
| 2 | Problem | Name the pain the viewer is experiencing | Callout Box, Stat Cards (cost of problem), Icon Grid (pain points) |
| 3 | Agitation | Deepen the pain, show consequences of inaction | Before/After (reversed -- showing decline), Stat Cards (cost of inaction), Emotional Contrast |
| 4 | Solution | Introduce the product/method as the answer | Flow Diagram (how it works), Step Sequence (the method), Block Diagram |
| 5 | Features/Benefits | What's included and what it means for them | Icon Grid, Card Grid, Comparison Grid (old way vs. new way) |
| 6 | Social Proof | Results and testimonials | Quote Block, Stat Cards (results), Before/After (transformation) |
| 7 | Offer | Full value stack with price anchoring | Card Grid (line items with values), Stat Cards (total value) |
| 8 | Guarantee | Risk reversal | Callout Box (guarantee badge), Icon Grid (guarantee details) |
| 9 | CTA | VSL-specific call to action | Copy from `templates/sections/next-step-vsl.html` |

### Section Rules

- **No About Me section.** VSLs do not have a standalone credibility slide. Credentials are woven into the Solution or Social Proof sections naturally (e.g., "After 8 years of testing this with 2,400+ students...").
- **No Agenda slide.** The viewer should feel they're in a conversation, not a presentation. Never telegraph the structure.
- **Order is fixed.** The persuasion arc depends on emotional sequencing. Do not rearrange sections.
- **Hero sets the big promise.** The hero headline should articulate the transformation: what the viewer will achieve, without what they currently suffer from.

---

## 3. Section Count Guidance

VSLs are tight and punchy. The section count is fixed at approximately 9 core sections, but each section may use 1-3 slides/components internally.

| Element | Count |
|---------|-------|
| Core sections | 9 (fixed) |
| Max sections (including sub-slides) | ~10 |
| Components per section | 1-3 |
| Total viewports (scroll stops) | 10-20 |
| Target video length | 10-25 minutes |

A 15-minute VSL might have 9 sections with 12-15 total viewports. A 25-minute VSL might expand to 10 sections with 18-20 viewports by adding depth to Features/Benefits or Social Proof.

---

## 4. Required Fixed Sections

### VSL Next Step CTA (Section 9 -- always last)
- **Source:** `templates/sections/next-step-vsl.html`
- **Purpose:** Single, clear call to action with button to checkout/purchase.
- **Rules:** Copy as-is. Do not rewrite, restyle, or remove elements.

### Sections That Must NOT Appear
- **No About Me slide.** Credentials are embedded in Solution or Social Proof, never standalone.
- **No Agenda slide.** Never reveal the structure upfront.

---

## 5. Tone & Voice

### By Section Phase

| Phase | Sections | Tone |
|-------|----------|------|
| Problem + Agitation | 2-3 | Empathetic, understanding, "I've been there." Conversational, not clinical. Name the emotions the viewer feels. |
| Solution | 4 | Confident, clear, "Here's what changed everything." The shift from pain to possibility. |
| Features/Benefits | 5 | Practical, specific. Focus on what the product means for them, not just what it contains. |
| Social Proof | 6 | Authentic, results-driven. Let numbers and quotes do the heavy lifting. |
| Offer + Guarantee | 7-8 | Exciting but grounded. Generous, not hype-y. The viewer should feel they're getting a deal, not being sold. |
| CTA | 9 | Direct, warm, action-oriented. One clear next step. |

### What to Avoid
- **No hype.** No "INSANE value" or "This will BLOW YOUR MIND." Confidence, not volume.
- **No aggression.** The agitation section deepens pain through empathy, not guilt or shame.
- **No false scarcity.** If there's a deadline, it must be real. If there's no deadline, don't manufacture one.
- **No feature dumps.** Features/Benefits section leads with the benefit, then names the feature that delivers it.

---

## 6. Credibility Weaving

Since VSLs have no standalone About Me, credentials must be embedded naturally:

### Where to Embed Credibility

| Section | How to Weave |
|---------|-------------|
| Solution (4) | "After [X years/clients/tests], I discovered that..." or "Working with [N] [audience] showed me..." |
| Social Proof (6) | "Here's what happened when [student/client name] applied this..." Include specific results. |
| Offer (7) | "I've invested $[X] and [Y years] developing this system..." justifies the value anchor. |

### Rules
- Credentials serve the story, not the ego.
- Maximum 1-2 credibility mentions across the entire VSL.
- Always tie credentials to the specific outcome the viewer cares about.

---

## 7. Component Affinity Table

### By VSL Section

| Section | Primary Components | When to Use Each |
|---------|-------------------|------------------|
| **Hero** | Hero Section | Always. Benefit-focused headline + subtitle with the big promise. |
| **Problem** | Callout Box | Single powerful pain statement with emotional weight. |
| | Stat Cards | When you have data on the cost of the problem (e.g., "73% of businesses fail at X"). |
| | Icon Grid | When listing 3-5 specific pain points the viewer recognizes. |
| **Agitation** | Before/After | Show the gap between where they are and where they could be (or where they'll end up doing nothing). |
| | Stat Cards | Cost of inaction: time lost, money wasted, opportunities missed. |
| | Comparison Grid (2-col) | "What you're doing now" vs. "What's actually possible." |
| **Solution** | Flow Diagram | When the solution is a process or system (show the pipeline). |
| | Step Sequence | When the solution is a method with clear steps (3-5 steps max). |
| | Block Diagram | When the solution is a framework with interconnected parts. |
| **Features/Benefits** | Icon Grid | 4-8 features with benefit-focused descriptions. |
| | Card Grid | When features need more detail (title + description + icon per card). |
| | Comparison Grid | "Old Way vs. New Way" or "Without [Product] vs. With [Product]." |
| **Social Proof** | Quote Block | Individual testimonials with name, context, and result. |
| | Stat Cards | Aggregate results: "2,400+ students", "87% success rate", "$2.3M generated." |
| | Before/After | Client transformation stories with specific numbers. |
| **Offer** | Card Grid | Value stack: each card = one offer component with individual value. |
| | Stat Cards | Total value anchor vs. actual price (e.g., "Total Value: $4,997 / Today: $497"). |
| | Step Sequence | "Here's everything you get" as a numbered list with values. |
| **Guarantee** | Callout Box | Money-back guarantee with bold, clear terms. Shield/badge visual treatment. |
| | Icon Grid | When the guarantee has multiple components (30-day refund + lifetime access + support). |
| **CTA** | Next Step VSL (template) | Always. Copied from template. |

---

## 8. Offer Stack Slide Structure

The Offer section is the most important sales slide. It follows a specific structure:

### Format
```
[Offer Component 1] — Individual Value: $X
[Offer Component 2] — Individual Value: $X
[Offer Component 3] — Individual Value: $X
[Offer Component 4] — Individual Value: $X
───────────────────────────────────────
Total Value: $[Sum]
Today's Price: $[Actual Price]
You Save: $[Difference]
```

### Rules
- List 4-8 offer components.
- Each component gets an individual perceived value.
- Values should be believable (based on what they'd pay for each item separately or what alternatives cost).
- The total value anchor should be 5-10x the actual price.
- Use struck-through pricing for individual values when showing the final slide.
- Build the stack progressively: show items one at a time if the VSL format allows for multiple scroll stops.

---

## 9. Guarantee Badge Slide Structure

### Format
```
[Shield/Badge Icon]
[Guarantee Headline: "100% Money-Back Guarantee"]
[Guarantee Terms: "Try [Product] for [X] days. If you don't [specific result], email us and we'll refund every penny. No questions asked."]
```

### Rules
- Keep it simple and bold.
- Specify the timeframe (30 days, 60 days, etc.).
- Tie the guarantee to a specific outcome when possible.
- "No questions asked" removes the last friction point.
- Use the Callout Box component with purple border treatment for visual emphasis.

---

## 10. Phase 1 Outline Format

### Format

```
VSL OUTLINE: [Product/Offer Name]
Estimated viewports: [N] (for ~[X] min VSL)

1. Hero — Component: Hero Section — [Big promise headline]
2. Problem — Component: [Component] — [What pain is named]
3. Agitation — Component: [Component] — [How pain is deepened]
4. Solution — Component: [Component] — [What method/product is introduced]
5. Features/Benefits — Component: [Component] — [What's included]
6. Social Proof — Component: [Component] — [What results are shown]
7. Offer — Component: Card Grid + Stat Cards — [Value stack summary]
8. Guarantee — Component: Callout Box — [Guarantee type and terms]
9. CTA — Component: VSL Next Step CTA (from template) — Copied from templates/sections/next-step-vsl.html
```

### Rules for Outline Creation
1. Exactly 9 sections (unless Features/Benefits is split into 2 for longer VSLs).
2. No About Me. No Agenda.
3. Each section maps to 1-3 components.
4. The outline must name the specific emotional angle for Problem and Agitation.
5. The Offer section must include the value anchor and actual price.

---

## 11. Build Rules

When converting an approved outline into an HTML page:

1. **Use the component library exactly.** Copy the HTML/CSS pattern from `components/components.md` and adapt the content. Do not invent new component styles.
2. **Use the brand specification exactly.** All colors, fonts, spacing, and surface treatments come from `brand/brand.md`.
3. **Copy the CTA section verbatim.** The VSL Next Step CTA comes from its template file unchanged.
4. **One continuous HTML file.** The entire page is a single `.html` file with all CSS inline or in a `<style>` block. No external stylesheets (except Google Fonts).
5. **Background layer is global.** The background image and overlay from `brand/brand.md` apply to the entire page, not per-section.
6. **Sections stack vertically.** Each section is a full-width block inside the `.page-wrapper`. Vertical gap between sections: 80-100px.
7. **No section dividers in VSLs.** The emotional flow should feel continuous, not segmented. Avoid visual breaks between sections.
8. **Responsive is irrelevant.** This page is only ever viewed at 1920x1080 in a screen recording. Do not add responsive breakpoints or mobile considerations.
9. **Embed credentials, don't showcase them.** Weave credibility into Solution or Social Proof copy. Never add a standalone About Me section.
