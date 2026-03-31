# HubSpot Figma Workspace — GitHub Copilot Edition
## Deloitte Israel | MarTech Migration | Go-Live: May 2, 2026

This workspace is optimized for **GitHub Copilot agents inside VS Code**.

---

## Setup Checklist

### Step 1 — Clone & Open
```bash
git clone https://github.com/buildwithmaximus/hubspot-figma-workspace-copilot.git
cd hubspot-figma-workspace-copilot
code .
```

### Step 2 — Install GitHub Copilot
- Install **GitHub Copilot** extension in VS Code
- Install **GitHub Copilot Chat** extension
- Sign in with your GitHub account (company account)

### Step 3 — Install Figma MCP
```bash
npm install -g @figma/mcp-server
```

### Step 4 — Add Your Figma Token
1. Go to figma.com → Settings → Personal access tokens → Generate new token
2. Open `.vscode/settings.json`
3. Replace `YOUR_FIGMA_TOKEN_HERE` with your actual token

> ⚠️ `.vscode/settings.json` is gitignored after you add your token — it will not be committed.

### Step 5 — Create Your Figma File
1. Create a new Figma project: **"HubSpot Campaign Designs — Deloitte Israel"**
2. Duplicate HubSpot UI Kit from Figma Community (see `references/hubspot-ui-kit.md`)
3. Save your Figma file URL

### Step 6 — Test Copilot + MCP
Open Copilot Chat in VS Code and type:
```
@workspace List my Figma files
```
If it returns your files — you're connected ✅

---

## How to Use Copilot in This Project

### Always include context in your prompts:
```
#file:PROJECT-CONTEXT.md #file:campaign-specs/event-campaign.md
Create the Event landing page desktop frame in Figma
```

### Use agent mode for multi-step tasks:
```
@workspace #file:PROJECT-CONTEXT.md
Generate all frames for the Event Campaign page in Figma:
landing page desktop, landing page mobile, form spec, and all 4 email templates
```

### Reference naming conventions:
```
#file:references/figma-naming-conventions.md
Follow the naming conventions and create the Webinar form spec frame
```

---

## File Structure

```
hubspot-figma-workspace-copilot/
├── .github/
│   └── copilot-instructions.md   ← Auto-loaded by Copilot every session
├── .vscode/
│   └── settings.json             ← Figma MCP config (add your token here)
├── brand/
│   └── brand-checklist.md        ← Brand assets to collect
├── campaign-specs/               ← Individual campaign markdown files
├── references/
│   ├── figma-naming-conventions.md
│   ├── figma-mcp-setup.md
│   ├── hubspot-ui-kit.md
│   └── prompting-guide-copilot.md
├── PROJECT-CONTEXT.md            ← Full project context (reference in prompts)
└── README.md
```

---

## Key Difference from Claude Code Version

| | This repo (Copilot) | Claude Code version |
|--|--|--|
| Context file | `.github/copilot-instructions.md` (auto-loaded) | `CLAUDE.md` (auto-loaded) |
| MCP config | `.vscode/settings.json` | `.mcp.json` |
| Prompt style | `#file:` and `@workspace` | Natural language |
| Context loading | Auto + explicit `#file:` | Auto via CLAUDE.md |
