# HubSpot UI Kit — Reference

## Official HubSpot Figma Resources

### HubSpot UI Kit (Official)
- **Figma Community:** https://www.figma.com/community/file/1009168150716699516/hubspot-ui-kit
- Contains: Forms, buttons, inputs, cards, nav, modals, tables
- Duplicate into your Figma project → use as base components

### HubSpot Email Design System
- **Figma Community:** https://www.figma.com/community/file/1006539982038607488
- Contains: Email header, hero, content blocks, CTA, footer
- All components are Outlook-compatible table-based layouts

### HubSpot Landing Page Templates Reference
- https://www.hubspot.com/resources/template/landing-page
- Browse real HubSpot landing page structures

---

## How to Import into Figma

1. Open the Figma Community links above
2. Click **"Duplicate to your drafts"**
3. Move the file into your "HubSpot Campaign Designs — Deloitte Israel" project
4. In your main design file: Assets panel → Libraries → Enable the UI kit

---

## Key HubSpot Landing Page Modules

| Module | HubSpot Name | Usage |
|--------|-------------|-------|
| Hero Banner | `rich_text` + `image` | Top section of every LP |
| Form embed | `form` | Registration / download forms |
| Rich text | `rich_text` | Body content, descriptions |
| CTA Button | `cta` | Tracked call-to-action |
| Image | `image` | Speakers, logos, assets |
| Section divider | `divider` | Visual separation |
| Social sharing | `social_sharing` | Event/webinar pages |
| Header | Global module | Every page |
| Footer | Global module | Every page |

---

## Key HubSpot Email Modules

| Module | Usage |
|--------|-------|
| Logo header | All emails |
| Hero image + text | Invitation, promotion emails |
| Text block | Body copy |
| Button (tracked) | All CTAs |
| Divider | Section separation |
| Social icons | Footer |
| Unsubscribe footer | Required on all emails |
| Personalization token | `{{contact.firstname}}` |

---

## Outlook Compatibility Rules

All email designs must follow these constraints:
- Table-based layout (no CSS Grid or Flexbox)
- Max width: 600px
- No background images in Outlook sections
- All fonts: Arial / system fonts (web fonts may not render)
- CTA buttons: use bulletproof button technique (VML)
- Images: always include `alt` text
- Minimum font size: 14px (mobile)
