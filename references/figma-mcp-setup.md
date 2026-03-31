# Figma MCP Setup Guide

Connect VS Code / Claude Code to Figma so AI can read and write designs directly.

---

## Step 1 — Get Your Figma Access Token

1. Go to figma.com → log in
2. Click your profile icon → **Settings**
3. Scroll to **Personal access tokens**
4. Click **Generate new token**
5. Name it: `VS Code MCP`
6. Copy the token — you only see it once

---

## Step 2 — Install Figma MCP Server

```bash
npm install -g @figma/mcp-server
```

Verify installation:
```bash
figma-mcp --version
```

---

## Step 3 — Configure `.mcp.json`

Open `.mcp.json` in this project and replace `YOUR_FIGMA_TOKEN_HERE` with your actual token:

```json
{
  "mcpServers": {
    "figma": {
      "command": "npx",
      "args": ["@figma/mcp-server"],
      "env": {
        "FIGMA_ACCESS_TOKEN": "figd_your_token_here"
      }
    }
  }
}
```

> ⚠️ Never commit your token to GitHub. Add `.mcp.json` to `.gitignore` after adding your token.

---

## Step 4 — Add .mcp.json to .gitignore

```bash
echo ".mcp.json" >> .gitignore
```

---

## Step 5 — Test the Connection

In VS Code with Claude Code extension:
1. Open the Claude Code panel
2. Type: `List my Figma files`
3. If it returns your files — MCP is working ✅

---

## What Figma MCP Can Do

Once connected, Claude Code / GitHub Copilot can:

- **Read** your Figma file structure, components, frames
- **Create** new frames and components
- **Update** text, colors, styles
- **Export** frame specs as JSON
- **Navigate** the component hierarchy

### Example prompts you can use:

```
"Create a new frame called 'Event — Landing Page' in my HubSpot Campaign Designs file"

"Add a hero section using Deloitte green (#86BC25) as the background"

"Create the Event Registration form spec with all the fields from CLAUDE.md"

"Generate the Event Invitation email template using HubSpot email components"
```

---

## Figma File URL

After creating your Figma project, save the URL here:

```
FIGMA_FILE_URL=https://www.figma.com/file/YOUR_FILE_ID/HubSpot-Campaign-Designs-Deloitte-Israel
```

You'll need this URL when prompting the AI to work on a specific file.
