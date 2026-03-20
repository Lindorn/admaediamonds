# A. D'Mae Diamonds - Web Style Guide
## Version 1.0 | March 2026

This style guide documents the design system established across admaediamonds.com during the P3/P3.5 build. Every pattern here has been validated against luxury web design best practices and WCAG AA accessibility standards. Use this as the reference for all future page builds, content updates, and design decisions.

---

## Design Philosophy

A. D'Mae Diamonds is a luxury custom jewelry studio. The website should feel like walking into a private showroom - sophisticated, warm, personal, and never pushy. The design supports Ali's brand voice: direct, honest, technically precise, and emotionally accessible.

**Core principles:**
- Dark theme conveys sophistication and lets jewelry imagery shine (industry standard for luxury brands)
- Generous spacing creates a premium, unhurried feel - luxury design lets content breathe
- Every page has one clear job and one clear next step - no dead ends
- Content is scannable (cards, short paragraphs, clear headings) but never shallow
- The gold accent is used sparingly for emphasis, CTAs, and brand identity - never decoratively overused

---

## Color Palette

All color combinations have been tested against WCAG AA accessibility standards. Every combination passes for both normal and large text.

### Primary Colors

| Role | Hex | Usage | Contrast on #111 |
|------|-----|-------|-------------------|
| Background | `#111111` | Site-wide dark background (Squarespace theme) | - |
| Headings | `#ffffff` | All h1, h2, h3 elements, bold/strong text | 18.88:1 PASS |
| Body Text | `#e0dbd2` | Paragraph text, descriptions, content | 13.70:1 PASS |
| Secondary Text | `#c4bfb4` | Subheadings, section intros, card descriptions | 10.30:1 PASS |
| Muted Text | `#999999` | Trust signals, attribution, timestamps, labels | 6.63:1 PASS |
| Gold Accent | `#d4af37` | Links, CTAs, dividers, card titles, credential badges | 8.98:1 PASS |

### Functional Colors

| Role | Hex/Value | Usage |
|------|-----------|-------|
| Card Background | `rgba(255, 255, 255, 0.02)` | Subtle lift for card elements |
| Card Border | `rgba(212, 175, 55, 0.2)` | Default card border |
| Card Border (hover) | `#d4af37` | Card hover state, interactive elements |
| Container Background | `rgba(212, 175, 55, 0.04)` | Lead magnet, Acuity embed, final CTA containers |
| Container Border | `rgba(212, 175, 55, 0.25)` | Featured containers (lead magnet, scheduler) |
| Form Input Background | `rgba(255, 255, 255, 0.08)` | Restyled native form fields |
| Form Input Border | `rgba(212, 175, 55, 0.3)` | Form field borders |
| Acuity Background | `#f5f2ed` | Off-white for Acuity embed interior |

### Color Usage Rules

- **Never use pure black `#000000` as a background** - use `#111111` or let Squarespace's theme handle it. Pure black causes OLED smearing and feels harsher than dark gray.
- **Gold `#d4af37` is reserved for interactive and emphasis elements** - links, buttons, dividers, card headings, credential badges. Do not use it for body text or large blocks of color.
- **Body text is `#e0dbd2`, not `#ffffff`** - pure white body text on dark backgrounds causes halation (glowing effect) and eye strain. The warm off-white is more comfortable to read.
- **Headings use `#ffffff`** - the brightness difference between headings and body text creates natural visual hierarchy.
- **`#999999` is the floor for text contrast** - do not use anything darker than this for text on dark backgrounds. Consider bumping to `#aaaaaa` for improved mobile readability in bright environments.

---

## Typography

Typography is inherited from Squarespace's site-wide font settings. The style guide controls sizing, weight, spacing, and alignment within our code injection pages.

### Heading Scale

| Level | Size | Weight | Color | Usage |
|-------|------|--------|-------|-------|
| H1 | `clamp(2rem, 5vw, 3rem)` | 400 (light) | `#ffffff` | Page titles. One per page. |
| H2 | `clamp(1.5rem, 3.5vw, 2rem)` | 400 (light) | `#ffffff` | Section headings. Centered. |
| H3 | `1.05rem - 1.15rem` | 600 (semibold) | `#d4af37` | Card headings, sub-section labels. |

### Body Text

| Element | Size | Color | Line Height |
|---------|------|-------|-------------|
| Body paragraphs | `1.1rem` (body sections), `1.05rem` (SEO paragraphs) | `#e0dbd2` | 1.8 |
| Section intros | `1.05rem` | `#c4bfb4` | 1.7 |
| Card descriptions | `0.95rem` | `#c4bfb4` | 1.7 |
| Trust signals | `0.8rem` | `#999999` | - |
| Labels/notes | `0.8rem - 0.85rem` | `#999999` or `#c4bfb4` | - |

### Typography Rules

- **Letter spacing on headings:** `0.01em` - subtle, not aggressive
- **Letter spacing on trust signals and labels:** `0.08em` with `text-transform: uppercase`
- **Letter spacing on CTAs:** `0.15em` with `text-transform: uppercase`
- **H1 uses italic gold for emphasis word** (e.g., "What Does Custom Jewelry *Really* Cost?")
- **Hero subtitles are italic** in `#c4bfb4`
- **No bold in body paragraphs** except for lead-in sentences (first sentence of a section)
- **`strong` tags render in `#ffffff`** to stand out from `#e0dbd2` body text

---

## Layout & Spacing

### Universal Top Spacing

Applied site-wide via Squarespace Custom CSS to normalize the gap between the top navigation and page content across all pages:

```css
/* Universal top spacing fix - normalizes header gap across all pages */
#page .page-section:first-child .content-wrapper {
  padding-top: 4vw !important;
  padding-bottom: 2vw !important;
}
#page .page-section:first-child {
  min-height: unset !important;
}
```

- This ensures consistent spacing regardless of Squarespace section settings
- `4vw` top padding scales proportionally with viewport width
- `min-height: unset` prevents Squarespace from forcing tall first sections

### Page Structure

| Element | Max Width | Notes |
|---------|-----------|-------|
| `.admae-service-page` | 900px | Standard content pages (pricing, about, booking, service pages) |
| `.admae-homepage` | varies | Homepage uses wider layout for service cards (1100px) |
| SEO paragraphs | 800px | Slightly narrower for comfortable reading |
| Body text sections | 720px | Optimal line length for readability (50-75 characters) |
| FAQ sections | 700px | Slightly narrower for focused reading |

### Spacing

| Element | Value | Notes |
|---------|-------|-------|
| Gold divider | `width: 60px; height: 1px;` | Centered, `margin: 56px auto` |
| Section margin | 48px-56px | Between major sections |
| Card gap | 24px | Grid gap between cards |
| Paragraph margin | 20px bottom | Between body paragraphs |
| Page padding (sides) | 24px desktop, 18px mobile | Consistent site-wide |
| Page padding (bottom) | 80px desktop, 60px mobile | Before footer |

### The Gold Divider

The short centered gold line (`60px wide, 1px tall, #d4af37`) is the signature visual separator across the site. It replaces traditional horizontal rules.

- Used between every major section
- Always centered (`margin: 56px auto`)
- Never full-width - the short length is intentional and matches luxury design conventions (similar to how Cartier and Tiffany use thin rules)
- Do not substitute with Squarespace native horizontal rules (those are full-width and a different aesthetic)

---

## Components

### CTA Buttons

Two variants, used consistently across all pages:

**Outline CTA (primary):**
```css
padding: 20px 48px;
border: 2px solid #d4af37;
color: #d4af37;
font-size: 0.95rem;
font-weight: 600;
letter-spacing: 0.15em;
text-transform: uppercase;
border-radius: 2px;
/* Hover: background #d4af37, color #111 */
```

**Filled CTA (emphasis - used for final page CTAs):**
```css
background: #d4af37;
color: #111;
border: 2px solid #d4af37;
font-weight: 700;
/* Hover: background #c9a42e */
```

**CTA placement rules:**
- Hero section: outline CTA
- Mid-page CTA: text link style (uppercase, letterspaced, gold, underlined)
- Final CTA section: filled CTA inside bordered container with trust signals
- Never more than 3 booking CTAs per page

### Cards

Used for service offerings, "What to Expect" items, commitment statements, pricing factors.

```css
border: 1px solid rgba(212, 175, 55, 0.2);
padding: 28px 24px;
border-radius: 3px;
background: rgba(255, 255, 255, 0.02);
```

- Card headings: `#d4af37`, semibold
- Card body: `#c4bfb4`
- Responsive: 2-column grid on desktop, single column on mobile (breakpoint 680px)
- Service cards on homepage use 4-column grid (2-column on tablet, 1-column on mobile)

### Testimonials

Gold left-border pullquote format:

```css
border-left: 2px solid #d4af37;
padding: 0 0 0 24px;
```

- Quote text: `1rem`, italic, `#e0dbd2`
- Attribution: `0.85rem`, `#999999`, not italic
- Max width: 680px, centered
- 32px margin between testimonials

### FAQ Accordion

```css
/* Question */
padding: 20px 0;
font-size: 1.05rem;
font-weight: 600;
color: #fff;
/* Plus icon in #d4af37, rotates 45deg to X on open */

/* Answer */
font-size: 0.95rem;
color: #c4bfb4;
/* max-height transition for smooth open/close */
```

- Items separated by `1px solid rgba(212, 175, 55, 0.15)` bottom border
- FAQ sections max 700px wide

### Trust Signals

Displayed as a horizontal flex row below final CTAs:

```css
font-size: 0.8rem;
color: #999;
letter-spacing: 0.08em;
text-transform: uppercase;
```

Standard set: "GIA Graduate Gemologist", "Third-Generation Jeweler", "Free Consultation", "No Inventory to Push"

### Credential Badges

Used on the About page:

```css
font-size: 0.8rem;
color: #d4af37;
letter-spacing: 0.08em;
text-transform: uppercase;
border: 1px solid rgba(212, 175, 55, 0.3);
padding: 8px 16px;
border-radius: 2px;
```

### Styled Containers (Featured Elements)

Used for Acuity embed, lead magnet, final CTA blocks:

```css
border: 1px solid rgba(212, 175, 55, 0.25);
border-radius: 6px;
background: rgba(212, 175, 55, 0.04);
box-shadow: 0 4px 24px rgba(0, 0, 0, 0.3), 0 0 0 1px rgba(212, 175, 55, 0.08);
```

These create a "framed" premium feel that prevents embeds and forms from looking like raw elements pasted onto the page.

---

## Links

### Inline Content Links

```css
color: #d4af37;
text-decoration: none;
border-bottom: 1px solid rgba(212, 175, 55, 0.3);
/* Hover: border-color #d4af37 (solid) */
```

### Link Placement Rules

- Target roughly 1 link per 200-300 words of content
- 8+ unique destinations per major page
- Every page must link to `/schedule-an-appointment` at least once
- Blog posts should be linked from service pages (and vice versa)
- Don't place links inside H1, H2, H3 tags (exception: hero subtitles)
- Don't place links inside testimonial blockquotes
- Links should feel natural in the sentence - never "click here" style

---

## Final CTA Block Pattern

Every major page ends with this structure:

```
[Bordered container with gold tint]
  H2: "Curious What's Possible?" / "Ready to Start the Conversation?" / etc.
  Paragraph: brief, warm, ties back to page content
  Filled CTA Button: "Book Your Free Consultation"
  Trust Signals row
[/container]
```

Optionally followed by an "Explore" links row for cross-navigation.

---

## Page Templates

### Service Page Template
Hero (title + subtitle + CTA) -> Content sections with cards -> Pullquote -> FAQ accordion -> Final CTA with trust signals

### Blog Post Template
Title -> Body content with mid-article CTA after emotional climax -> Keep Reading section -> End CTA

### Legacy Page Template (About, Pricing, Booking)
Hero -> Unique content sections -> Testimonials (if applicable) -> Final CTA with trust signals -> Explore links

---

## Responsive Behavior

### Breakpoints

| Breakpoint | Behavior |
|------------|----------|
| > 900px | Full desktop layout, multi-column grids |
| 680px - 900px | Tablet - service cards collapse to 2-column |
| < 680px | Mobile - single column, reduced padding (18px), smaller images |

### Mobile-Specific Rules

- Side padding reduces from 24px to 18px
- Card grids collapse to single column
- Photo + text layouts (About page) stack vertically
- Pullquote left padding reduces from 28px to 20px
- Lead magnet image moves above form (if present)
- Trust signal gaps reduce from 32px to 20px
- Sticky mobile CTA bar appears at bottom of screen (gold background, "Book Free Consultation")

---

## SEO Metadata Format

All pages use pipe-separated format:

**Title:** `[Page Topic] [Location if applicable] | A. D'Mae Diamonds`

Examples:
- `Custom Engagement Rings Los Angeles | A. D'Mae Diamonds`
- `Meet Alexandria | GIA Gemologist & Custom Jeweler Los Angeles | A. D'Mae Diamonds`
- `Book Your Free Jewelry Consultation | A. D'Mae Diamonds`

**Description:** Under 155 characters. Include primary keyword, GIA credential, location, and free consultation where natural.

---

## Copy Style Rules

- **No em dashes or en dashes** - use hyphens or restructure the sentence
- **No emojis** anywhere on the site
- **GIA compliance:** Only "GIA Graduate Gemologist" or "GIA GG" - never "GIA certified"
- **Pricing framing:** "starting at $3K" with no ceiling - never attach prices to specific portfolio images
- **Ali's voice:** Direct, warm, anti-corporate, technically precise, emotionally accessible
- **Use specific stories and examples** rather than generic claims
- **No hedging on things Ali believes strongly** - confidence is part of the brand
- **"Custom" needs to be earned** - when we say custom, we mean truly generative design from scratch, not modifications to templates

---

## Code Organization

### File Structure (GitHub)

```
pages/
  blog/
    why-i-left-brilliant-earth.html
    lab-grown-vs-natural-diamonds.html
    how-much-does-a-custom-engagement-ring-cost.html
  services/
    custom-engagement-rings-los-angeles.html
    custom-mens-wedding-bands-los-angeles.html
    engagement-ring-consultation-los-angeles.html
    heirloom-jewelry-redesign-los-angeles.html
  other/
    custom-jewelry-pricing-information.html
    schedule-an-appointment.html
    aboutadmaediamonds.html
  homepage/
    homepage.html
```

### CSS Class Naming

- Service pages: `.admae-service-page` wrapper
- Blog posts: `.admae-blog` wrapper
- Homepage: `.admae-homepage` wrapper
- All component classes prefixed with `admae-` to avoid Squarespace conflicts

### Squarespace Integration

- All custom pages use body-level code injection via code blocks
- Native Squarespace blocks used only when code injection can't handle the functionality (forms, scheduling widgets, Trustindex embeds)
- When mixing code blocks with native blocks, each code block must be fully self-contained HTML (no orphaned opening/closing tags across blocks)
- CSS overrides for native elements use `!important` to override Squarespace defaults

---

## Accessibility Checklist

Before deploying any new page:

- [ ] All text/background combinations meet WCAG AA (4.5:1 for normal text, 3:1 for large text)
- [ ] All images have descriptive alt text
- [ ] All links are descriptive (no "click here")
- [ ] FAQ accordions are keyboard-accessible (onclick handlers)
- [ ] Form fields have visible labels
- [ ] Gold accent text is only used at sizes where 8.98:1 contrast is sufficient
- [ ] Page has logical heading hierarchy (one H1, H2s for sections, H3s for subsections)
- [ ] Mobile layout tested at 375px width (iPhone SE)

---

*Last updated: March 20, 2026*
*Maintained by: Aaron (strategy/operations) with Claude Code for QA*
