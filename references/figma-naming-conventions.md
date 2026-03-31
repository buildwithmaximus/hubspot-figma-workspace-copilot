# Figma Naming Conventions
## Optimized for Figma MCP + AI Coding Assistants

These conventions ensure GitHub Copilot and Claude Code can navigate, read, and write the Figma file predictably and without ambiguity.

---

## Core Rule

**Every frame, component, and style follows one pattern:**

```
[Scope] / [Type] / [Variant]
```

Examples:
- `Event / Landing Page / Desktop`
- `Event / Email / Invitation`
- `Brand / Button / Primary / Green`
- `Brand / Color / Green / Primary`

The `/` creates a navigable hierarchy. The AI traverses it like a file path.

---

## Page Names

| Page | Name |
|------|------|
| 1 | `00 — Brand & Components` |
| 2 | `01 — Event Campaign` |
| 3 | `02 — Webinar Campaign` |
| 4 | `03 — Newsletter Campaign` |
| 5 | `04 — Digital Asset Campaign` |

**Rules:**
- Always use the number prefix — keeps pages in order
- Never rename pages after MCP work has begun (AI references by name)

---

## Frame Names per Page

### 00 — Brand & Components

| Frame Name | Purpose |
|------------|---------|
| `Index` | Master list of all pages and frames — AI reads first |
| `Brand / Colors` | All named color swatches |
| `Brand / Typography` | All text style samples |
| `Brand / Logo / Primary` | Main Deloitte logo |
| `Brand / Logo / White` | White version for dark backgrounds |
| `Brand / Button / Primary` | Green CTA button component |
| `Brand / Button / Secondary` | Outlined button component |
| `Brand / Form / Field / Text` | Single-line text input |
| `Brand / Form / Field / Email` | Email input |
| `Brand / Form / Field / Dropdown` | Dropdown select |
| `Brand / Form / Field / Checkbox` | Checkbox input |
| `Brand / Form / Field / Textarea` | Multi-line input |
| `Brand / Form / Field / Hidden` | Hidden field indicator |
| `Brand / Email / Header` | Logo + green top border |
| `Brand / Email / Footer` | Unsubscribe + legal + social |
| `Brand / Email / Hero` | Full-width banner block |
| `Brand / Email / CTA Block` | Button + surrounding padding |
| `Brand / Email / Text Block` | Body copy section |
| `Brand / Email / Divider` | Horizontal separator |
| `Brand / LP / Hero` | Landing page hero section |
| `Brand / LP / Form Section` | Form embed area |
| `Brand / LP / Footer` | Page footer |

---

### Campaign Pages (01–04)

Each campaign page contains these frames in this order:

| Frame Name | Purpose |
|------------|---------|
| `[Campaign] / Specs` | Written spec — form fields, automation, KPIs |
| `[Campaign] / Landing Page / Desktop` | Full LP at 1440px |
| `[Campaign] / Landing Page / Mobile` | Full LP at 375px |
| `[Campaign] / Form Spec` | Visual form field table |
| `[Campaign] / Email / [Name]` | One frame per email template |

**Campaign name prefix:**
- Event Campaign → `Event`
- Webinar Campaign → `Webinar`
- Newsletter Campaign → `Newsletter`
- Digital Asset Campaign → `Digital Asset`

---

## Full Frame List

### 01 — Event Campaign
```
Event / Specs
Event / Landing Page / Desktop
Event / Landing Page / Mobile
Event / Form Spec
Event / Email / Invitation
Event / Email / Confirmation
Event / Email / Reminder -1d
Event / Email / Follow-up
```

### 02 — Webinar Campaign
```
Webinar / Specs
Webinar / Landing Page / Desktop
Webinar / Landing Page / Mobile
Webinar / Form Spec
Webinar / Email / Invitation
Webinar / Email / Confirmation
Webinar / Email / Reminder -1d
Webinar / Email / Reminder -1h
Webinar / Email / Follow-up + Recording
```

### 03 — Newsletter Campaign
```
Newsletter / Specs
Newsletter / Signup Page / Desktop
Newsletter / Signup Page / Mobile
Newsletter / Form Spec
Newsletter / Email / Newsletter Template
```

### 04 — Digital Asset Campaign
```
Digital Asset / Specs
Digital Asset / Landing Page / Desktop
Digital Asset / Landing Page / Mobile
Digital Asset / Form Spec
Digital Asset / Email / Promotion
Digital Asset / Email / Delivery
```

---

## Named Figma Styles

### Color Styles
All colors must be saved as named Figma styles — never use raw hex in prompts.

| Style Name | Hex | Usage |
|------------|-----|-------|
| `Color/Green/Primary` | `#86BC25` | CTAs, accents |
| `Color/Black/Primary` | `#000000` | Headlines |
| `Color/Grey/Dark` | `#53565A` | Body text |
| `Color/Grey/Light` | `#D0D0CE` | Borders, backgrounds |
| `Color/White` | `#FFFFFF` | Page backgrounds |

### Text Styles

| Style Name | Size | Weight | Usage |
|------------|------|--------|-------|
| `Text/H1/Desktop` | 48px | Bold | Page headlines |
| `Text/H2/Desktop` | 36px | Bold | Section headlines |
| `Text/H3/Desktop` | 24px | SemiBold | Subsections |
| `Text/H4/Desktop` | 20px | SemiBold | Card titles |
| `Text/Body/Regular` | 16px | Regular | Body copy |
| `Text/Body/Small` | 14px | Regular | Captions, labels |
| `Text/CTA` | 16px | Bold | Button text |
| `Text/H1/Mobile` | 32px | Bold | Mobile headlines |
| `Text/Body/Email` | 16px | Regular | Email body (Arial) |

---

## MCP Prompt Patterns

Use these patterns for consistent AI interactions:

### Creating a frame
```
Create a frame named "[Campaign] / [Asset] / [Variant]" on page "[Page Name]"
```

### Referencing components
```
Use the component "Brand / Button / Primary" for all CTAs
Apply color style "Color/Green/Primary" to the hero background
Use text style "Text/H1/Desktop" for the main headline
```

### Reading specs
```
Read the frame "[Campaign] / Specs" and use that data to populate the form spec frame
```

### Batch operations
```
Update all frames matching "* / Email / *" to use "Brand / Email / Footer" at the bottom
```

---

## Index Frame Template

The `Index` frame in `00 — Brand & Components` should contain this text (update as you add frames):

```
HUBSPOT CAMPAIGN DESIGNS — DELOITTE ISRAEL
Last updated: [date]

PAGES & FRAMES
══════════════

00 — Brand & Components
  Index ← you are here
  Brand / Colors
  Brand / Typography
  Brand / Logo / *
  Brand / Button / *
  Brand / Form / Field / *
  Brand / Email / *
  Brand / LP / *

01 — Event Campaign
  Event / Specs
  Event / Landing Page / Desktop + Mobile
  Event / Form Spec
  Event / Email / Invitation, Confirmation, Reminder -1d, Follow-up

02 — Webinar Campaign
  Webinar / Specs
  Webinar / Landing Page / Desktop + Mobile
  Webinar / Form Spec
  Webinar / Email / Invitation, Confirmation, Reminder -1d, Reminder -1h, Follow-up + Recording

03 — Newsletter Campaign
  Newsletter / Specs
  Newsletter / Signup Page / Desktop + Mobile
  Newsletter / Form Spec
  Newsletter / Email / Newsletter Template

04 — Digital Asset Campaign
  Digital Asset / Specs
  Digital Asset / Landing Page / Desktop + Mobile
  Digital Asset / Form Spec
  Digital Asset / Email / Promotion, Delivery
```
