# HubSpot CLI Setup Guide
## Local Development → Design Manager → Portal

---

## Step 1 — Install HubSpot CLI

```bash
npm install -g @hubspot/cli
```

Verify:
```bash
hs --version
```

---

## Step 2 — Get Your Portal ID

1. Log in to app-eu1.hubspot.com (Deloitte Israel — EU1)
2. Click your account name (top right)
3. Your Portal ID is the number shown — copy it

---

## Step 3 — Generate Personal Access Key

1. Go to: app-eu1.hubspot.com → Settings → Account Setup → Integrations → Private Apps
2. Or use the direct link: app-eu1.hubspot.com/personal-access-key
3. Click **Generate personal access key**
4. Select scopes:
   - ✅ Content (read + write)
   - ✅ Design Manager (read + write)
   - ✅ File Manager (read + write)
5. Copy the key — you only see it once

---

## Step 4 — Configure This Project

Open `hubspot.config.yml` and replace:
- `YOUR_PORTAL_ID_HERE` → your actual portal ID
- `YOUR_PERSONAL_ACCESS_KEY_HERE` → your personal access key

> ⚠️ `hubspot.config.yml` is gitignored after you add credentials. Never commit it.

---

## Step 5 — Authenticate

```bash
hs auth
```

Follow the prompts. Select your portal when asked.

Verify connection:
```bash
hs whoami
```

Should return: `Logged in as [your name] in portal [portal ID]`

---

## Step 6 — Fetch Existing Portal Assets (Optional)

If there are already files in Design Manager:
```bash
hs fetch --portal=deloitte-israel
```

---

## Core Commands

```bash
# Upload a single file
hs upload src/templates/event-landing-page.html @templates/event-landing-page.html

# Upload a module
hs upload src/modules/deloitte-hero-a @modules/deloitte-hero-a

# Watch for changes and auto-upload (development mode)
hs watch src/ @

# Download everything from Design Manager
hs fetch @

# List remote files
hs ls @templates/
```

---

## File Path Convention

| Local path | Remote path in Design Manager |
|-----------|-------------------------------|
| `src/templates/event-landing-page.html` | `@templates/event-landing-page.html` |
| `src/modules/deloitte-hero-a/` | `@modules/deloitte-hero-a/` |
| `src/css/deloitte-theme.css` | `@css/deloitte-theme.css` |

---

## Development Workflow

```bash
# Start watching — auto-syncs every save
hs watch src/ @

# Open VS Code + save a file → instantly appears in Design Manager
# Preview in HubSpot: Marketing → Landing Pages → New → select your template
```

---

## Where Your Templates Appear in HubSpot

After uploading:
1. Go to **Marketing → Landing Pages → Create**
2. Click **Choose a template**
3. Your templates appear under **"Custom templates"** or **"My templates"**
4. Select → opens in drag-and-drop editor with your layout as the base
