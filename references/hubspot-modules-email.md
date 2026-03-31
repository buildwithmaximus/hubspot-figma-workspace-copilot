# HubSpot Email Modules — Visual Anatomy
## Native Email Editor — What Each Module Contains

All email designs must use only these native HubSpot email modules.
Max width: 600px. Table-based layout. Font: Arial only (Outlook compatible).

---

## Email Canvas Rules (Non-Negotiable)

| Rule | Value |
|------|-------|
| Max width | 600px |
| Font family | Arial, Helvetica, sans-serif |
| Minimum font size | 14px (mobile) / 16px (desktop) |
| Background | White `#FFFFFF` (email body) |
| Outer background | Light grey `#F5F5F5` (canvas) |
| Link color | Deloitte green `#86BC25` |
| Image format | JPG/PNG, always with alt text |
| No CSS Grid/Flexbox | Table-based layout only |
| No web fonts | Arial only — web fonts don't render in Outlook |

---

## 1. Email Header Module

**HubSpot name:** Logo/Header section
**Height:** 72px

### Elements:
| Element | Spec |
|---------|------|
| Top border | 4px solid Deloitte green `#86BC25` |
| Background | White `#FFFFFF` |
| Logo | Centered or left-aligned, max height 40px |
| Logo link | Links to deloitte.com/il |
| Padding | 16px top/bottom, 24px left/right |

**Figma frame name:** `Brand / Email / Header`

---

## 2. Hero Banner Module

**HubSpot name:** Image module (full-width)
**Width:** 600px
**Height:** 200–280px

### Elements:
| Element | Spec |
|---------|------|
| Image | 600px wide, 200–280px tall, JPG |
| Alt text | Event/webinar name |
| Link | Optional — links to landing page |
| Border radius | None (flat edges for Outlook) |

> For text overlay on hero image — use a pre-designed image (text baked in). HubSpot email editor does not support CSS text overlay reliably in Outlook.

**Figma frame name:** `Brand / Email / Hero Banner`

---

## 3. Headline + Body Text Module

**HubSpot name:** Rich Text module
**Width:** 600px, 32px left/right padding (effective content: 536px)

### Elements:
| Element | Spec |
|---------|------|
| H1 headline | Arial Bold, 28px, black `#000000` |
| H2 sub-headline | Arial Bold, 22px, black |
| Body paragraph | Arial Regular, 16px, dark grey `#53565A`, line-height 1.6 |
| Bullet list | 16px, standard disc bullets, 8px indent |
| Bold inline | Arial Bold, same size |
| Link | Deloitte green `#86BC25`, underline |
| Personalization | `{{contact.firstname}}` token — renders first name |
| Padding | 24px top/bottom, 32px left/right |

**Figma frame name:** `Brand / Email / Text Block`

---

## 4. CTA Button Module

**HubSpot name:** Button module (bulletproof button)
**Width:** Auto or full-width

### Elements:
| Element | Spec |
|---------|------|
| Button background | Deloitte green `#86BC25` |
| Button text | White `#FFFFFF`, Arial Bold, 16px |
| Button height | 52px |
| Button width | 220px min, auto max |
| Border radius | 4px |
| Alignment | Centered |
| Padding around button | 24px top/bottom |
| Arrow | Optional " →" appended to label |
| Implementation | VML bulletproof button (renders in Outlook) |

### Button labels by email type:
| Email | CTA Label |
|-------|-----------|
| Invitation | Register Now → |
| Confirmation | Add to Calendar → |
| Reminder -1d | Full Details → |
| Reminder -1h | Join Now → |
| Follow-up | Watch Recording → |
| Delivery | Download Now → |
| Promotion | Download for Free → |

**Figma frame name:** `Brand / Email / CTA Button`

---

## 5. Event Details Row Module

**HubSpot name:** Rich Text (structured table or list)
**Width:** 536px (600px - 32px padding each side)

### Elements (one row per detail):
| Element | Spec |
|---------|------|
| Icon | 20x20px inline image (calendar, clock, location) |
| Label | Arial Bold, 14px, black |
| Value | Arial Regular, 14px, dark grey |
| Row height | 40px |
| Row border | 1px bottom `#D0D0CE` optional |
| Background | White or very light grey `#F9F9F9` |

### Details shown:
- 📅 Date: [Event date]
- ⏰ Time: [Start time] – [End time]
- 📍 Location: [Venue or "Online via Zoom"]
- 🔗 Join link (webinar only)

**Figma frame name:** `Brand / Email / Event Details Row`

---

## 6. Summary Card Module

**HubSpot name:** Rich Text with background color section

Used in: Confirmation emails, reminder emails

### Elements:
| Element | Spec |
|---------|------|
| Background | Light grey `#F5F5F5` |
| Border | 1px `#D0D0CE` |
| Border radius | 4px |
| Padding | 24px |
| Content | Event name (bold) + date + time + location |
| Font | Arial, 14px |
| Margin | 16px top/bottom |

**Figma frame name:** `Brand / Email / Summary Card`

---

## 7. Divider Module

**HubSpot name:** Divider module
**Width:** Full (600px)

### Elements:
| Element | Spec |
|---------|------|
| Line | 1px solid `#D0D0CE` |
| Margin | 24px top/bottom |
| Width | 100% or 80% centered |

**Figma frame name:** `Brand / Email / Divider`

---

## 8. Image Block Module

**HubSpot name:** Image module (inline)
**Width:** Up to 536px

### Elements:
| Element | Spec |
|---------|------|
| Image | Max 536px wide, auto height |
| Alt text | Always required |
| Caption | 12px Arial grey, below image, optional |
| Padding | 16px top/bottom |
| Alignment | Centered |

**Figma frame name:** `Brand / Email / Image Block`

---

## 9. Social Icons Row Module

**HubSpot name:** Social Follow module
**Width:** Auto, centered

Used in: Footer area of most emails

### Elements:
| Element | Spec |
|---------|------|
| Icons | LinkedIn, Twitter/X, Facebook — 32x32px |
| Icon style | Solid grey `#53565A` or color |
| Spacing | 12px between icons |
| Links | Deloitte social profiles |
| Padding | 16px top/bottom |

**Figma frame name:** `Brand / Email / Social Icons`

---

## 10. Email Footer Module

**HubSpot name:** Footer (required on all marketing emails)
**Width:** 600px

### Elements:
| Element | Spec |
|---------|------|
| Background | Light grey `#F5F5F5` or white |
| Top border | 1px `#D0D0CE` |
| Unsubscribe link | Required by law — green link, 12px |
| Manage preferences | Link to HubSpot preference center |
| Legal text | "You're receiving this because..." — 12px grey |
| Address | Deloitte Israel address — 12px grey |
| Copyright | "© [Year] Deloitte" — 12px grey |
| Social icons | Optional row above legal |
| Padding | 24px top/bottom, 32px left/right |

**Figma frame name:** `Brand / Email / Footer`

---

## Complete Email Structure per Type

### Invitation / Promotion Email
```
Header (72px)
Hero Banner (240px)
Text Block — headline + body (auto)
Event Details Row OR Bullet benefits (auto)
CTA Button (100px)
Divider
Footer (120px)
```

### Confirmation Email
```
Header (72px)
Text Block — "Confirmed!" headline with checkmark (auto)
Summary Card — event details (auto)
CTA Button — "Add to Calendar" (100px)
Text Block — preparation info (auto)
Divider
Footer (120px)
```

### Reminder -1 Day Email
```
Header (72px)
Text Block — "Tomorrow!" headline (auto)
Summary Card — date, time, location (auto)
Text Block — what to expect (auto)
CTA Button — "Full Details" (100px)
Footer (120px)
```

### Reminder -1 Hour Email
```
Header (72px)
Text Block — urgent headline (auto)
CTA Button — large "Join Now" (100px)
Text Block — webinar name + time (auto)
Footer (120px)
```

### Follow-up + Recording Email
```
Header (72px)
Text Block — thank you headline (auto)
CTA Button — "Watch Recording" (100px)
Image Block — presentation thumbnail (auto)
Text Block — key takeaways (auto)
Divider
Text Block — related content (auto)
Footer (120px)
```

### Newsletter Email
```
Header (72px) — logo + issue date
Text Block — greeting with {{contact.firstname}} (auto)
[Article 1] Image Block + Text Block + CTA link
Divider
[Article 2] Image Block + Text Block + CTA link
Divider
[Article 3] Image Block + Text Block + CTA link
Divider (optional) — upcoming event callout
Footer (120px)
```
