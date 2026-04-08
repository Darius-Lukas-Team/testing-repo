# Brand Specification — Hyper AI University

## Logo
- **Dark version (for light backgrounds — default):** `https://assets.cdn.filesafe.space/lNzgml2EfCzIl04kmDr2/media/69c6dec39fc63ab17f2737ea.png`
- **Light version (for dark backgrounds):** `https://assets.cdn.filesafe.space/lNzgml2EfCzIl04kmDr2/media/69c6dec331ffeb8677e90560.png`
- **Default:** Use the dark version (light backgrounds are standard)
- **Placement:** Top-left of the hero section, or centered above the title
- **Max height:** 42px (30% smaller than original 60px)
- **Opacity:** 70% (`opacity: 0.7`)
- **Margin below:** 24px before the title

## Theme

Light mode is the default. All pages use a white background with dark text. A `.section-dark` utility class is available for optional dark accent sections.

### Light Theme (default)
- **Background:** `#ffffff` (white) with very subtle purple gradient overlay
- **Text:** Black (`#000000`) for primary, muted dark for secondary
- **Cards:** White (`#ffffff`) with subtle borders and shadows

### Dark Theme (optional — for accent sections)
- **Background:** `#0a0a0a` (near-black)
- **Text:** White (`#ffffff`) for primary, muted white for secondary
- **Cards:** Semi-transparent white backgrounds (`rgba(255, 255, 255, 0.06)`)
- **Usage:** Apply `.section-dark` class to a section container

### Implementation
```css
/* Light mode (default) */
body {
  background: #ffffff;
  color: #000000;
}

/* Optional dark accent section */
.section-dark {
  background: #0a0a0a;
  color: #ffffff;
}
```

## CSS Variables
```css
:root {
  /* Primary palette */
  --color-primary: #4F30FE;
  --color-primary-light: #DAB3FF;
  --color-primary-dark: #262DFF;
  --color-accent: #DAB3FF;

  /* Light theme (default) */
  --color-bg: #ffffff;
  --color-text: #000000;
  --color-text-muted: rgba(0, 0, 0, 0.6);
  --color-text-dim: rgba(0, 0, 0, 0.35);
  --color-card-bg: #ffffff;
  --color-card-border: rgba(0, 0, 0, 0.08);
  --color-card-shadow: 0 2px 12px rgba(0, 0, 0, 0.04);

  /* Gradients */
  --gradient-primary: linear-gradient(135deg, #DAB3FF, #262DFF);
  --gradient-reverse: linear-gradient(135deg, #262DFF, #DAB3FF);
}
```

## Colors

### Primary Palette
| Name | Hex | Usage |
|------|-----|-------|
| Brand Purple | `#4F30FE` | Primary accent — headings, highlights, borders, icons, stat numbers, accent color lines |
| Light Purple | `#DAB3FF` | Secondary accent — tags, badges, secondary highlights, gradient start |
| Deep Blue | `#262DFF` | Gradient end, deep highlights |
| White | `#ffffff` | Primary text on dark backgrounds, card backgrounds on light sections |
| Black | `#000000` | Primary text on light backgrounds, dark section backgrounds |
| Off-White | `#F9F9F9` | Light section backgrounds |

### Gradients
| Name | CSS | Usage |
|------|-----|-------|
| Lavender-to-Blue | `linear-gradient(135deg, #DAB3FF, #262DFF)` | Gradient text, button backgrounds, accent bars, top borders on cards |
| Purple Warm | `linear-gradient(135deg, #DAB3FF, #4F30FE)` | Alternate accent for visual variety, warm highlights |
| Purple Fade | `linear-gradient(135deg, #4F30FE, rgba(79,48,254,0.3))` | Subtle background tints |
| Lavender Fade | `linear-gradient(135deg, #DAB3FF, rgba(218,179,255,0.3))` | Subtle background tints |

### Gradient Text
Text with gradient fill — used for highlight phrases in headings:
```css
.gradient-text {
  background: linear-gradient(135deg, #DAB3FF, #262DFF);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

### Accent Color Text
Single-color accent for inline highlights (not gradient):
```css
.accent-text {
  color: #4F30FE;
}
```

### Supporting Colors
Use sparingly — only when you need additional differentiation (e.g., in charts with 5+ categories or multi-branch diagrams):

| Name | Hex | Usage |
|------|-----|-------|
| Hot Pink | `#FF268B` | Fourth-level accent, attention states |
| Bright Green | `#22c55e` | Fifth-level accent, success/positive states |
| Coral | `#ff462e` | Warning or attention states |

### Surface Colors
| Name | CSS | Usage |
|------|-----|-------|
| Page Background | `#ffffff` | Main page background |
| Card Background | `#ffffff` | Card/container backgrounds |
| Card Border | `rgba(0, 0, 0, 0.08)` | Subtle card borders |
| Card Shadow | `0 2px 12px rgba(0, 0, 0, 0.04)` | Subtle card elevation |
| Divider | `rgba(0, 0, 0, 0.06)` | Section separators |
| Inner Element BG | `rgba(0, 0, 0, 0.02)` | Nested elements, inner cards |

## Typography

### Font
- **Family:** DM Sans (Google Fonts)
- **Load:** `https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800&display=swap`
- **Fallback:** `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`

### Heading Scale
All headings use **DM Sans Semibold (600)**.

| Element | Size | Weight | Usage |
|---------|------|--------|-------|
| H1 | 50px | 600 (Semibold) | Hero title, main page headline |
| H2 | 42px | 600 (Semibold) | Section headings |
| H3 | 30px | 600 (Semibold) | Sub-section headings, card group titles |
| H4 | 23px | 600 (Semibold) | Card titles, feature names |
| H5 | 19px | 600 (Semibold) | Small headings, labels |
| H6 | 16px | 600 (Semibold) | Smallest heading, meta labels |

### Body Text Scale
Body text uses **DM Sans Regular (400)**.

| Element | Size | Weight | Usage |
|---------|------|--------|-------|
| Body | 16px | 400 (Regular) | Paragraph text, descriptions, card content |
| Small | 14px | 400 (Regular) | Captions, meta info, secondary descriptions |

### Text Colors
| Context | Value |
|---------|-------|
| Primary text | `#000000` |
| Secondary text | `rgba(0, 0, 0, 0.6)` |
| Tertiary text | `rgba(0, 0, 0, 0.35)` |
| Accent text | `#4F30FE` |
| Gradient text | `linear-gradient(135deg, #DAB3FF, #262DFF)` |

**Important:** No text on the page should ever be smaller than 14px. Video compression destroys small text — anything under 14px becomes unreadable.

### Slide Optimization Note
When designing slides for 1920x1080 screen recording, scale up from the base type scale for on-camera readability:
- Hero title: 64–72px (scale up from H1)
- Section headings: 40–48px (scale up from H2)
- Card titles: 24–28px (scale up from H4)
- Body text: 20–22px (scale up from Body)
- Minimum text size: 14px absolute floor

### Line Heights
- Headings: 1.2–1.3
- Body text: 1.6–1.7
- Cards: 1.5

## Buttons

### Primary CTA Button
The primary call-to-action button uses the gradient background with white text:

```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 16px 32px;
  background: linear-gradient(135deg, #DAB3FF, #262DFF);
  color: #ffffff;
  font-family: 'DM Sans', sans-serif;
  font-size: 18px;
  font-weight: 600;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  text-decoration: none;
  transition: opacity 0.2s, transform 0.2s;
}
.btn-primary:hover {
  opacity: 0.9;
  transform: translateY(-1px);
}
```

```html
<a href="#" class="btn-primary">Become a Member <span>&#9654;</span></a>
```

## Stacked Text Pattern

For text-heavy sections, use this alignment and color pattern:
- **Heading:** Black text with accent phrases in gradient or accent purple
- **Sub-text:** Slightly smaller, with key phrases in accent color (`#4F30FE`)
- **CTA button** below the text block
- **Alignment:** Left-aligned or center-aligned (both are valid, choose based on section layout)

```html
<!-- Left-aligned example (on light background) -->
<div class="stacked-text">
  <h2>These aren't blog posts or random tips. Think of them as
    <span class="gradient-text">your private AI intelligence briefings,</span>
    built to give you the clarity and edge most people will miss.
  </h2>
  <p>The result? <span class="accent-text">In just 10 minutes a week,</span> you'll always know
    what's worth paying attention to, and how to turn it into leverage
    before the rest of the market catches up.</p>
  <a href="#" class="btn-primary">Become a Member <span>&#9654;</span></a>
</div>
```

## Spacing

### Page Layout
- Max width: 1200px
- Side padding: 40px
- Section vertical gap: 80–100px (enough to create clear separation on scroll)

### Card Spacing
- Card padding: 24–32px
- Card gap (in grids): 16–20px
- Card border-radius: 14–16px

### Inner Element Spacing
- Element gap within cards: 12–16px
- Icon/badge size: 28–36px with 8–10px border-radius
- Dot indicators: 8–10px

## Company Info
- **Brand name:** Hyper AI University
- **Company:** Hyper Entrepreneurship
- **Domain:** hyperentrepreneurship.com
