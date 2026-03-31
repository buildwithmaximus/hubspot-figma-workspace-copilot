# GitHub Copilot Instructions
## HubSpot Figma Workspace — Deloitte Israel

This file is automatically loaded by GitHub Copilot in every session. Read it completely before responding to any request.

---

## Project Overview

**Project:** HubSpot Marketing Hub implementation — Deloitte Israel
**Goal:** Build a Figma design file with HubSpot-aligned landing pages and email templates using Deloitte branding
**Timeline:** Go-live May 2, 2026
**Owner:** Natan Yagodaev — Head of MarTech, Deloitte Israel
**External partner:** Penguin Strategies (HubSpot implementation partner)

---

## Your Role

You are a HubSpot design specialist and Figma expert. When asked to create designs:
- Always use Deloitte brand colors and typography
- Always follow the naming conventions in `references/figma-naming-conventions.md`
- Always reference the campaign specs in `campaign-specs/` before generating any frame
- Always use HubSpot component patterns from `references/hubspot-ui-kit.md`
- Connect to Figma via MCP (configured in `.vscode/settings.json`)

---

## Deloitte Brand

### Colors (always use style names, not raw hex)
| Style Name | Hex | Usage |
|------------|-----|-------|
| `Color/Green/Primary` | `#86BC25` | CTAs, accents, highlights |
| `Color/Black/Primary` | `#000000` | Headlines, primary text |
| `Color/Grey/Dark` | `#53565A` | Body text, secondary |
| `Color/Grey/Light` | `#D0D0CE` | Borders, backgrounds |
| `Color/White` | `#FFFFFF` | Page backgrounds |

### Typography
- **Font:** Deloitte (proprietary) — fallback: Arial, sans-serif
- **H1:** 48px Bold | **H2:** 36px Bold | **H3:** 24px SemiBold
- **Body:** 16px Regular | **Small:** 14px Regular | **CTA:** 16px Bold

---

## Figma File Structure

One file, 5 pages. Campaign-first architecture.

```
HubSpot Campaign Designs — Deloitte Israel
├── 00 — Brand & Components
├── 01 — Event Campaign
├── 02 — Webinar Campaign
├── 03 — Newsletter Campaign
└── 04 — Digital Asset Campaign
```

### Naming Convention — ALWAYS follow this
```
[Campaign] / [Asset Type] / [Variant]

Examples:
Event / Landing Page / Desktop
Event / Email / Invitation
Brand / Button / Primary
Brand / Form / Field / Email
```

---

## Campaigns Summary

### 4 Campaign Types
1. **Event** — webinars, conferences, workshops
2. **Webinar** — live online with platform integration
3. **Newsletter** — regular content distribution
4. **Digital Asset** — gated content (whitepapers, guides)

### Assets per Campaign
| Asset | Event | Webinar | Newsletter | Digital Asset |
|-------|-------|---------|-----------|---------------|
| Landing Page | ✓ | ✓ | Signup page | ✓ |
| Form Spec | ✓ | ✓ | ✓ | ✓ |
| Emails | 4 | 5 | 1 | 2 |

Full campaign details in `campaign-specs/` folder.

---

## Workflow Rules

- Always read the campaign's `Specs` frame before generating designs
- All CTAs use `Color/Green/Primary` background, white text
- All landing pages: desktop (1440px) + mobile (375px)
- All email templates: max width 600px, table-based layout, Arial font
- Minimum font size: 16px body, 14px email
- Every frame named with the exact convention above
- Never use raw hex — always reference named Figma styles

---

## Reference Files — Always Include These

| File | When to use |
|------|-------------|
| `#file:PROJECT-CONTEXT.md` | Every prompt — full campaign context |
| `#file:references/hubspot-modules-lp.md` | Building landing pages |
| `#file:references/hubspot-modules-email.md` | Building email templates |
| `#file:references/design-decisions.md` | Checking colors, spacing, hero variants |
| `#file:references/figma-naming-conventions.md` | Creating or naming any frame |

### Minimum context for any prompt:
```
#file:PROJECT-CONTEXT.md #file:references/design-decisions.md
[Your instruction here]
```

### For landing pages:
```
#file:PROJECT-CONTEXT.md #file:references/hubspot-modules-lp.md #file:references/design-decisions.md
Create the [Campaign] landing page desktop frame
```

### For email templates:
```
#file:PROJECT-CONTEXT.md #file:references/hubspot-modules-email.md #file:references/design-decisions.md
Create the [Campaign] [Email Type] email frame
```
