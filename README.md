# HubSpot Local Dev Workspace — Deloitte Israel
## Marketing Hub Enterprise | EU1 | Go-Live: May 2, 2026

VS Code workspace for building HubSpot landing page templates using the HubSpot CLI.
Optimized for GitHub Copilot agents.

---

## What This Is

Real HubSpot templates (HTML + HubL) that sync directly to your Design Manager via the HubSpot CLI.
When the team creates a new landing page in HubSpot, they select your template and get a fully structured, Deloitte-branded page ready to fill with content.

---

## Setup Checklist

### Step 1 — Install dependencies
```bash
npm install -g @hubspot/cli @figma/mcp-server
```

### Step 2 — Configure HubSpot CLI
Open `hubspot.config.yml` and add:
- Your Portal ID (from app-eu1.hubspot.com → account name → top right)
- Your Personal Access Key (app-eu1.hubspot.com/personal-access-key)

### Step 3 — Authenticate
```bash
hs auth
hs whoami
```

### Step 4 — Configure Figma MCP
Open `.vscode/settings.json` → add your Figma token

### Step 5 — Collect brand assets
See `brand/brand-checklist.md`

### Step 6 — Start developing
```bash
# Watch mode — auto-syncs every save to Design Manager
hs watch src/ @
```

---

## Project Structure

```
hubspot-figma-workspace-copilot/
├── .github/
│   └── copilot-instructions.md    ← Auto-loaded by Copilot every session
├── .vscode/
│   └── settings.json              ← Figma MCP config
├── hubspot.config.yml             ← HubSpot CLI config (add your credentials)
├── src/
│   ├── templates/                 ← Landing page HTML/HubL templates
│   │   ├── event-landing-page.html
│   │   ├── webinar-landing-page.html     (coming next)
│   │   ├── newsletter-signup.html        (coming next)
│   │   └── digital-asset-landing-page.html (coming next)
│   ├── modules/                   ← Custom reusable modules
│   │   ├── deloitte-hero-a/       ← Dark, centered (Event)
│   │   ├── deloitte-hero-b/       ← Split layout (Digital Asset, Newsletter)
│   │   └── deloitte-hero-c/       ← Image overlay (Webinar)
│   ├── partials/                  ← Global header + footer
│   └── css/
│       └── deloitte-theme.css     ← Full Deloitte design system
├── campaign-specs/                ← Campaign content reference
├── references/
│   ├── hubspot-cli-setup.md       ← CLI install + auth guide
│   ├── hubl-basics.md             ← HubL syntax reference for Copilot
│   ├── hubspot-modules-lp.md      ← Module anatomy reference
│   ├── hubspot-modules-email.md   ← Email module reference
│   ├── design-decisions.md        ← Colors, spacing, hero variants
│   └── figma-naming-conventions.md
├── brand/
│   └── brand-checklist.md
└── PROJECT-CONTEXT.md             ← Full campaign context for Copilot
```

---

## Templates Built

| Template | Status | Hero Variant |
|----------|--------|-------------|
| Event Landing Page | ✅ Done | Variant A (dark, centered) |
| Webinar Landing Page | 🔜 Next | Variant C (image overlay) |
| Newsletter Signup | 🔜 Next | Variant B (split layout) |
| Digital Asset Landing Page | 🔜 Next | Variant B (split layout) |

---

## How to Use in HubSpot

1. Run `hs watch src/ @` to sync templates
2. Go to **Marketing → Landing Pages → Create**
3. Click **Choose a template → My Templates**
4. Select a Deloitte template
5. Opens in drag-and-drop editor — fill in your content
6. Publish

---

## Key Copilot Prompts

```
#file:PROJECT-CONTEXT.md #file:references/hubl-basics.md #file:references/design-decisions.md

Create the Webinar landing page template at src/templates/webinar-landing-page.html
Use Variant C hero (full-width image overlay with countdown timer section below)
Follow the same structure as event-landing-page.html
```
