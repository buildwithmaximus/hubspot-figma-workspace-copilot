# Design Decisions
## HubSpot Campaign Designs — Deloitte Israel

All design decisions for Figma templates. Reference this before generating any frame.

---

## Hero Variant per Campaign

| Campaign | Hero Variant | Reason |
|----------|-------------|--------|
| Event | **Variant A** — Centered text, dark background | Creates urgency, clear registration focus, date/location prominent |
| Webinar | **Variant C** — Full-width image with overlay | High-impact, add countdown timer below hero |
| Newsletter | **Variant B** — Split layout, text left / image right | Lighter, content-focused feel |
| Digital Asset | **Variant B** — Split layout, text left / cover right | Asset cover image drives download intent |

---

## Color Usage Rules

| Situation | Color | Hex |
|-----------|-------|-----|
| All CTA buttons | Green | `#86BC25` |
| All headlines | Black | `#000000` |
| Body copy | Dark grey | `#53565A` |
| Borders, dividers | Light grey | `#D0D0CE` |
| Page backgrounds | White | `#FFFFFF` |
| Dark hero sections | Black | `#000000` |
| Section accents | Green | `#86BC25` |
| Email canvas background | Light grey | `#F5F5F5` |
| Inverted CTA (on green bg) | White button, black text | |

**Rule:** Green is used for CTAs and accents only — never as a dominant background on body sections.

---

## Typography Rules

### Landing Pages
| Element | Font | Size | Weight | Color |
|---------|------|------|--------|-------|
| H1 | Deloitte / Arial | 48px | Bold | `#000000` |
| H2 | Deloitte / Arial | 36px | Bold | `#000000` |
| H3 | Deloitte / Arial | 24px | SemiBold | `#000000` |
| H4 | Deloitte / Arial | 20px | SemiBold | `#000000` |
| Body | Deloitte / Arial | 16px | Regular | `#53565A` |
| Small / Caption | Deloitte / Arial | 14px | Regular | `#53565A` |
| CTA button | Deloitte / Arial | 16px | Bold | White |
| Label / Tag | Deloitte / Arial | 12px | Bold uppercase | `#86BC25` |

### Emails (Arial only — Outlook compatible)
| Element | Font | Size | Weight |
|---------|------|------|--------|
| H1 | Arial | 28px | Bold |
| H2 | Arial | 22px | Bold |
| Body | Arial | 16px | Regular |
| Small / Legal | Arial | 12px | Regular |
| CTA button | Arial | 16px | Bold |

---

## Spacing System

### Landing Pages
| Zone | Value |
|------|-------|
| Section padding top/bottom | 80px |
| Container max width | 1200px |
| Content max width | 800px (text only) |
| Column gap | 32px |
| Card padding | 24px |
| Element spacing (within section) | 16px |
| Button height | 52px |
| Button min-width | 180px |
| Border radius (cards) | 8px |
| Border radius (buttons) | 4px |

### Emails
| Zone | Value |
|------|-------|
| Email max width | 600px |
| Left/right padding | 32px |
| Section padding top/bottom | 24px |
| Button height | 52px |
| Element spacing | 16px |
| Border radius (buttons) | 4px |

---

## Frame Sizes

| Frame | Width | Height |
|-------|-------|--------|
| LP Desktop | 1440px | Auto (min 900px) |
| LP Mobile | 375px | Auto |
| Email | 600px | Auto |
| Form Spec | 900px | Auto |
| Specs text frame | 800px | Auto |
| Hero Variant A/C | 1440px | 560px |
| Hero Variant B | 1440px | 520px |

---

## Component Decisions

### Buttons
- Always full-width in email (600px - 64px padding = 536px)
- On landing pages: auto-width, min 180px, max 240px
- Always centered on desktop, full-width on mobile
- Text: Verb first — "Register Now", "Download", "Join" — never "Click here"

### Forms
- Always show field labels above the input (not placeholder-only)
- Required fields marked with red asterisk `*`
- Submit button: full-width, green, "Register Now" / "Download" / "Subscribe"
- Form container: white background, subtle shadow or border
- Hidden fields: shown in Form Spec frame only, not in visual designs

### Images
- All images use placeholder rectangles in Figma (grey fill `#D0D0CE`)
- Label placeholders: "[Event Banner 1440x560]", "[Speaker Photo 120x120]"
- Never use stock photo URLs in spec files

### Icons
- Use HubSpot's native icon set OR simple SVG inline icons
- Size: 20x20px inline, 32x32px social
- Color: Dark grey `#53565A` or green `#86BC25`

---

## What to Build First — Order of Operations

### Phase 1 — Foundation (do this before any campaign)
1. `00 — Brand & Components` page
   - Set up named color styles
   - Set up named text styles
   - Build all reusable components (header, footer, buttons, form fields, email modules)

### Phase 2 — Campaign by Campaign
Build in this order (simplest to most complex):
1. Newsletter Campaign (fewest assets — good for testing)
2. Digital Asset Campaign
3. Event Campaign
4. Webinar Campaign (most complex — 5 emails + countdown)

### Phase 3 — Per Campaign, in this order:
1. Specs frame (text, no design)
2. Hero variants (A, B, or C per campaign)
3. Full landing page desktop
4. Full landing page mobile
5. Form spec
6. Emails (in send-order: Invitation → Confirmation → Reminder → Follow-up)
