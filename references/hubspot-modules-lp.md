# HubSpot Landing Page Modules — Visual Anatomy
## Native Drag & Drop Editor — What Each Module Contains

All designs must use only these native HubSpot modules. No custom CSS unless noted.

---

## 1. Global Header Module

**HubSpot name:** Header (global module)
**Width:** Full-width (100%)
**Height:** 72px standard

### Elements:
| Element | Spec | Notes |
|---------|------|-------|
| Logo | Left-aligned, max height 40px | SVG preferred |
| Navigation links | Right-aligned, horizontal | Max 5-6 items |
| CTA button | Far right, optional | Primary button style |
| Background | Solid color or transparent | White default |
| Border bottom | 1px solid | Subtle separator |

### Figma frame name: `Brand / LP / Header`

---

## 2. Hero Module

**HubSpot name:** Rich Text + Background Image (or Banner module)
**Width:** Full-width (100%)
**Height:** 480–640px (configurable)

HubSpot natively supports 3 hero layouts in the drag-and-drop editor:

---

### Hero Variant A — Centered Text on Color Background
**Best for:** Event, Webinar campaigns
**HubSpot implementation:** Full-width section with background color, rich text centered

| Element | Spec |
|---------|------|
| Background | Solid color (Deloitte black `#000000` or dark grey `#53565A`) |
| Headline H1 | Centered, white, 48px Bold |
| Subheadline | Centered, light grey, 20px Regular, max 2 lines |
| Meta info row | Date · Location · Duration — centered, 16px, grey |
| CTA button | Centered, green `#86BC25`, white text, 52px height, 200px min-width |
| Green accent | 4px top border OR left accent bar |

**Figma frame name:** `Brand / LP / Hero / Variant-A / Desktop`

---

### Hero Variant B — Split Layout (Text Left, Image Right)
**Best for:** Digital Asset, Speaker-focused events
**HubSpot implementation:** 2-column layout module, left = rich text, right = image module

| Element | Spec |
|---------|------|
| Left column | 55% width |
| Right column | 45% width |
| Background | White or light grey `#F5F5F5` |
| Headline H1 | Left-aligned, black, 48px Bold |
| Subheadline | Left-aligned, dark grey, 20px Regular |
| CTA button | Left-aligned, green, 52px height |
| Right image | Asset cover mockup or speaker photo, full column height |
| Image treatment | Rounded corners 8px or straight edge |

**Figma frame name:** `Brand / LP / Hero / Variant-B / Desktop`

---

### Hero Variant C — Full-Width Background Image with Text Overlay
**Best for:** High-impact event launches, webinar campaigns
**HubSpot implementation:** Full-width section with background image + color overlay

| Element | Spec |
|---------|------|
| Background image | Full-width, 640px height |
| Color overlay | Black at 60% opacity |
| Headline H1 | Centered or left, white, 48px Bold |
| Subheadline | White, 20px Regular |
| CTA button | Green `#86BC25`, white text |
| Green accent | Bottom border OR left vertical bar |

**Figma frame name:** `Brand / LP / Hero / Variant-C / Desktop`

---

## 3. Rich Text Module

**HubSpot name:** Rich Text
**Width:** Full-width or column-constrained
**Max content width:** 800px centered

### Elements:
| Element | Spec |
|---------|------|
| Section heading H2 | Black, 36px Bold |
| Section heading H3 | Black, 24px SemiBold |
| Body paragraph | Dark grey `#53565A`, 16px Regular, line-height 1.7 |
| Bullet list | 16px, 8px left indent, green bullet `#86BC25` |
| Bold inline text | Same size, 700 weight |
| Link | Green `#86BC25`, underline on hover |
| Section padding | 80px top/bottom, 24px left/right |

**Figma frame name:** `Brand / LP / Rich Text`

---

## 4. Form Module

**HubSpot name:** Form (embedded HubSpot form)
**Width:** 480px centered (standalone) or full column (2-col layout)

### Elements:
| Element | Spec |
|---------|------|
| Form title | H3, black, 24px Bold, optional |
| Form description | Grey, 14px Regular, optional |
| Field label | Black, 14px Medium, above field |
| Text input | 48px height, border `#D0D0CE`, radius 4px, full width |
| Email input | Same as text input |
| Dropdown select | Same height, chevron icon right |
| Checkbox | 18px square, green check when selected |
| Textarea | 120px height, same border style |
| Required indicator | Red asterisk `*` after label |
| Hidden field | Not visible — shown in spec only |
| Submit button | Full width, 52px height, green `#86BC25`, white text bold |
| Thank-you message | Replaces form on submission, green checkmark + text |
| Field spacing | 16px between fields |
| Form padding | 32px all sides |
| Form background | White with subtle shadow or border |

**Figma frame name:** `Brand / LP / Form / [Campaign Name]`

---

## 5. Image Module

**HubSpot name:** Image
**Width:** Full-width or column-constrained

### Elements:
| Element | Spec |
|---------|------|
| Image | Responsive, max full-width |
| Alt text | Always included (accessibility) |
| Caption | 14px grey, below image, optional |
| Padding | 0 (edge-to-edge) or 40px (contained) |

**Figma frame name:** `Brand / LP / Image Block`

---

## 6. Speakers Module

**HubSpot name:** 3-column layout (native columns module)
**Width:** Full-width, 3 equal columns

### Elements per speaker card:
| Element | Spec |
|---------|------|
| Photo | 120x120px circle crop |
| Name | H4, black, 20px Bold |
| Title | Dark grey, 14px Regular |
| Organization | Dark grey, 14px Regular |
| Bio (optional) | 14px, 4-5 lines max |
| Column padding | 24px |
| Card background | White or transparent |

**Figma frame name:** `Brand / LP / Speakers Section`

---

## 7. Agenda / Timeline Module

**HubSpot name:** Rich Text (structured list)
**Width:** 800px centered

### Elements:
| Element | Spec |
|---------|------|
| Time label | Green `#86BC25`, 14px Bold, left column (120px) |
| Topic title | Black, 16px Bold |
| Topic description | Grey, 14px Regular |
| Row divider | 1px `#D0D0CE` between items |
| Row padding | 16px top/bottom |
| Section heading | H2 above the timeline |

**Figma frame name:** `Brand / LP / Agenda Section`

---

## 8. Social Proof Module

**HubSpot name:** Rich Text + Image (logo strip)
**Width:** Full-width, grey background

### Elements:
| Element | Spec |
|---------|------|
| Section label | "Trusted by" or "Past attendees", 12px grey uppercase |
| Logo strip | Grayscale logos, max height 40px, horizontal row |
| Attendee count | Large number (e.g. "500+"), black, 36px Bold |
| Quote | Italic, 18px, dark grey, max 2 lines |
| Attribution | Name + title, 14px grey |
| Background | Light grey `#F5F5F5` |
| Padding | 60px top/bottom |

**Figma frame name:** `Brand / LP / Social Proof`

---

## 9. CTA Section Module

**HubSpot name:** Full-width section with rich text + button

### Elements:
| Element | Spec |
|---------|------|
| Background | Deloitte green `#86BC25` OR black |
| Headline | White, H2, 36px Bold, centered |
| Subtext | White 80% opacity, 18px, centered |
| Button | White background, black text (inverted on green bg) |
| Padding | 80px top/bottom |

**Figma frame name:** `Brand / LP / CTA Section`

---

## 10. Global Footer Module

**HubSpot name:** Footer (global module)
**Width:** Full-width

### Elements:
| Element | Spec |
|---------|------|
| Logo | Left-aligned, white version on dark bg |
| Navigation links | Horizontal row, 14px |
| Social icons | Right-aligned row |
| Legal text | 12px grey, bottom row |
| Copyright | "© [Year] Deloitte" |
| Background | Black `#000000` or dark grey |
| Padding | 48px top/bottom |

**Figma frame name:** `Brand / LP / Footer`

---

## Campaign → Hero Variant Mapping

| Campaign | Hero Variant | Reason |
|----------|-------------|--------|
| Event | Variant A (centered, dark) | Creates urgency, clean registration focus |
| Webinar | Variant C (image overlay) | High-impact, with countdown timer added |
| Newsletter | Variant B (split layout) | Lighter feel, content-focused |
| Digital Asset | Variant B (split layout) | Asset cover image on right, form prominent |
