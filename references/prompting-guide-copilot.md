# Prompting Guide — GitHub Copilot Agents
## VS Code Agent Mode + Figma MCP

---

## Core Pattern

Always include context files in your prompts:

```
#file:PROJECT-CONTEXT.md #file:campaign-specs/[campaign].md
[Your instruction here]
```

---

## Session Starter Prompt

Paste this at the start of every Copilot Chat session:

```
#file:PROJECT-CONTEXT.md #file:references/figma-naming-conventions.md

You are a HubSpot design specialist working on the Deloitte Israel marketing migration.
Read the project context and naming conventions completely.
All Figma work uses Deloitte branding (green #86BC25, black #000000, grey #53565A).
All frame names follow the convention: [Campaign] / [Asset Type] / [Variant].
Confirm you're ready.
```

---

## Landing Page Prompts

### Event Campaign — Desktop Landing Page
```
#file:PROJECT-CONTEXT.md

Create a Figma frame named "Event / Landing Page / Desktop" on page "01 — Event Campaign".
Width: 1440px. Use Deloitte brand colors and typography.

Sections in order:
1. Hero — dark background, green accent, H1 event title, date/location row, "Register Now" CTA button (Color/Green/Primary)
2. Event Details — 2-column: description left, key info right
3. Agenda — timeline with times and topics
4. Speakers — 3-column grid: photo placeholder, name, title, organization
5. Form Section — centered white background, embedded form placeholder with all 6 visible fields labeled
6. Social Proof — logo strip + attendee count
7. Footer — Deloitte logo, nav links, legal text

Apply text styles: Text/H1/Desktop for headline, Text/Body/Regular for body copy.
Apply color styles: Color/Green/Primary for CTA, Color/Black/Primary for headlines.
```

### Webinar Campaign — Desktop Landing Page
```
#file:PROJECT-CONTEXT.md

Create frame "Webinar / Landing Page / Desktop" on page "02 — Webinar Campaign".
Same structure as Event landing page with these additions:
- Add countdown timer component in the hero section
- Platform logos row (Zoom / Teams / GoToWebinar) in a "Technical Info" section
- Form has 7 fields (add Phone and Question for Speaker)
```

### Digital Asset — Desktop Landing Page
```
#file:PROJECT-CONTEXT.md

Create frame "Digital Asset / Landing Page / Desktop" on page "04 — Digital Asset Campaign".
Width: 1440px. Use 2-column layout below the hero.

Layout:
- Hero: asset title H1, 1-2 sentence description, cover image mockup right side
- Left column (60%): "What you'll learn" bullets, content preview, social proof (download count, logos)
- Right column (40%): Sticky download form card with 5 visible fields + hidden fields note
- Footer
```

---

## Email Template Prompts

### Event — Invitation Email
```
#file:PROJECT-CONTEXT.md

Create frame "Event / Email / Invitation" on page "01 — Event Campaign".
Width: 600px, auto height. Table-based layout. Font: Arial.

Structure:
1. Header: Deloitte logo centered, 4px green (Color/Green/Primary) top border
2. Hero: Full-width banner image placeholder (600x240px)
3. Headline: "You're invited to [Event Name]" — Text/H1 black
4. Event details: 3 rows with icon placeholder + text: Date · Time · Location
5. Description: 2-3 lines body text (Text/Body/Email)
6. CTA: "Register Now →" button — Color/Green/Primary background, white text, centered, 48px height
7. Footer: Unsubscribe link · Legal text · Social icons row

Max 600px width. Outlook-compatible.
```

### Event — Confirmation Email
```
#file:PROJECT-CONTEXT.md

Create frame "Event / Email / Confirmation" on page "01 — Event Campaign".
Width: 600px.

Structure:
1. Header: Deloitte logo
2. Green checkmark icon + "Registration Confirmed!" headline (Color/Green/Primary)
3. Summary card: grey background box with Event Name · Date · Time · Location
4. Calendar CTA: "Add to Calendar →" button (Color/Green/Primary)
5. Preparation text: "What to expect" section
6. Footer
```

### Webinar — Reminder -1 Hour Email
```
#file:PROJECT-CONTEXT.md

Create frame "Webinar / Email / Reminder -1h" on page "02 — Webinar Campaign".
Width: 600px. This is a short, urgent email.

Structure:
1. Header: Deloitte logo
2. Red urgency badge: "Starting in 1 hour"
3. Headline: "The webinar starts in 1 hour!"
4. Large CTA button: "Join Webinar Now →" (Color/Green/Primary, prominent)
5. Webinar name + time reminder (small text)
6. Footer
```

---

## Form Spec Prompts

### Event Form Spec
```
#file:PROJECT-CONTEXT.md

Create frame "Event / Form Spec" on page "01 — Event Campaign".
Width: 900px. This is a specification document, not a visual form.

Create two tables:

Table 1 — Visible Fields (header: Field Name | HubSpot Property | Type | Required):
- First Name | firstname | Text | ✓
- Last Name | lastname | Text | ✓
- Business Email | email | Email | ✓
- Company | company | Text | —
- Job Title | jobtitle | Text | —
- Session Preference | custom | Dropdown | —

Table 2 — Hidden Fields (header: Field | Type):
- UTM Source | Hidden
- UTM Campaign | Hidden
- UTM Medium | Hidden

Table 3 — Post-Submission Settings (header: Setting | Value):
- After submission | Thank-you message + redirect
- Internal alert | Send to event manager
- Automation trigger | Activate Event Registration Workflow
- Add to list | Registrants list — [Event Name]
- Lifecycle stage | Lead (if empty)
- CAPTCHA | reCAPTCHA enabled

Use Deloitte brand colors for table headers (Color/Green/Primary).
```

---

## Specs Frame Prompt

### Event Specs Frame
```
#file:PROJECT-CONTEXT.md

Create frame "Event / Specs" on page "01 — Event Campaign".
Width: 800px. This is a text reference frame the AI reads before generating designs.

Include:
- Campaign name and type
- Number of assets (1 LP, 1 form, 4 emails)
- Full form field list
- Automation workflow steps (numbered)
- KPI list
- Key notes (reCAPTCHA required, max 2 external walls, etc.)

Format as clean structured text with headers. Use Deloitte typography styles.
```

---

## Batch Generation Prompt

### Generate All Event Campaign Frames
```
#file:PROJECT-CONTEXT.md #file:references/figma-naming-conventions.md

Generate all frames for page "01 — Event Campaign" in sequence:
1. Event / Specs
2. Event / Landing Page / Desktop (1440px)
3. Event / Landing Page / Mobile (375px)
4. Event / Form Spec (900px)
5. Event / Email / Invitation (600px)
6. Event / Email / Confirmation (600px)
7. Event / Email / Reminder -1d (600px)
8. Event / Email / Follow-up (600px)

Use Deloitte branding throughout. Follow naming conventions exactly.
Confirm each frame as you complete it.
```

---

## Useful Copilot Agent Commands

```bash
# Check MCP connection
@workspace Can you list my Figma files?

# Navigate to a specific frame
@workspace Go to frame "Event / Landing Page / Desktop" in my Figma file

# Update all CTAs
@workspace Update all CTA buttons across all campaign pages to use Color/Green/Primary

# Export assets
@workspace Export all email frames from page "01 — Event Campaign" as PNG at 2x

# Add a new frame
@workspace Add frame "Webinar / Email / Reminder -1h" to page "02 — Webinar Campaign"
```
