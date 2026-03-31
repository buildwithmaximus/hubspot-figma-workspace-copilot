# PROJECT-CONTEXT.md
## HubSpot Figma Workspace — Deloitte Israel

Full project context. Reference this file in every Copilot prompt using `#file:PROJECT-CONTEXT.md`.

---

## Project

**Client:** Deloitte Israel
**Project:** Marketo → HubSpot Marketing Hub migration
**Goal:** Build complete Figma design file — landing pages + email templates for all 4 campaign types
**Go-Live:** May 2, 2026
**Owner:** Natan Yagodaev, Head of MarTech
**Partner:** Penguin Strategies (HubSpot implementation)

---

## Deloitte Brand

### Colors
| Name | Hex |
|------|-----|
| Green (primary) | `#86BC25` |
| Black | `#000000` |
| Dark Grey | `#53565A` |
| Light Grey | `#D0D0CE` |
| White | `#FFFFFF` |

> ⚠️ In Figma prompts, always use style names not hex: `Color/Green/Primary`

### Typography
- Font: Deloitte (proprietary) / fallback: Arial
- H1: 48px Bold · H2: 36px Bold · H3: 24px SemiBold
- Body: 16px Regular · Email body: 16px Arial

---

## Campaign 1 — Event Campaign

### Landing Page Sections
1. Hero: Event title · Date · Location · Banner · Register CTA
2. Event Details: Description · Goals · Audience
3. Agenda: Times · Topics · Breaks
4. Speakers: Photo · Name · Title · Org
5. Registration Form (embedded)
6. Social Proof: Quotes · Logos · Count
7. Footer

### Form — Visible Fields
| Field | HubSpot Property | Required |
|-------|-----------------|----------|
| First Name | firstname | ✓ |
| Last Name | lastname | ✓ |
| Business Email | email | ✓ |
| Company | company | |
| Job Title | jobtitle | |
| Session Preference | custom dropdown | |

### Form — Hidden Fields
UTM Source · UTM Campaign · UTM Medium

### Post-Submission
Thank-you message + redirect · Internal alert email · Activate workflow · Add to list · Lifecycle → Lead · reCAPTCHA

### Email Templates (4)
1. **Invitation** [Manual] — banner, details, Register Now CTA
2. **Confirmation** [Auto] — confirmed, calendar link
3. **Reminder** [Auto, -1 day] — tomorrow reminder
4. **Follow-up** [Auto, +1 day] — recording + materials

### Automation (6 steps)
Trigger → List → Lifecycle → Lead Source → Confirmation → Wait(-1d) → Reminder → Wait(+1d) → Follow-up

---

## Campaign 2 — Webinar Campaign

### Landing Page Sections
1. Hero: Title · Date · Duration · **Countdown timer**
2. Description: Topics · Outcomes · Audience
3. Speakers: Photo · Bio · Org
4. Agenda: Topics · Q&A
5. Registration Form
6. Platform info: Zoom/Teams/GoToWebinar
7. Social Proof · Footer

### Form — Visible Fields
| Field | HubSpot Property | Required |
|-------|-----------------|----------|
| First Name | firstname | ✓ |
| Last Name | lastname | ✓ |
| Business Email | email | ✓ |
| Company | company | |
| Job Title | jobtitle | |
| Phone | phone | |
| Question for Speaker | custom textarea | |

### Form — Hidden Fields
UTM Source · UTM Campaign · UTM Medium

### Email Templates (5)
1. **Invitation** [Manual] — details, speakers, Register CTA
2. **Confirmation** [Auto] — confirmed + join link + calendar
3. **Reminder -1 day** [Auto] — tomorrow + join link
4. **Reminder -1 hour** [Auto] — starts in 1 hour + join link
5. **Follow-up + Recording** [Auto, +1 day] — recording + slides + Q&A

### Automation (11 steps)
Trigger → List → Lifecycle → Lead Source → Confirmation → Wait(-1d) → Reminder → Wait(-1h) → Reminder → Wait(end+1d) → Follow-up

---

## Campaign 3 — Newsletter Campaign

### Signup Page Sections
1. Hero: "Stay informed" · Value proposition
2. What You'll Get: 3-4 bullet points
3. Signup Form (minimal)
4. Privacy assurance · Footer

### Form — Visible Fields
| Field | HubSpot Property | Required |
|-------|-----------------|----------|
| Business Email | email | ✓ |
| First Name | firstname | |
| Last Name | lastname | |
| Content Preference | custom checkbox | |

### Form — Hidden Fields
UTM Source · UTM Campaign

### Email Templates (1 recurring + optional welcome)
- **Welcome Email** [Auto, optional]
- **Newsletter Issue** [Manual/scheduled] — logo + date + 3 articles + footer

### Automation (5 steps)
Trigger → Subscription type → Lifecycle → Lead source → Welcome email

---

## Campaign 4 — Digital Asset Campaign

### Landing Page Sections
1. Hero: Asset title · Description · Cover image
2. Left (60%): What you'll learn · Preview · Social proof
3. Right (40%): Gated download form (sticky)
4. Footer

### Form — Visible Fields
| Field | HubSpot Property | Required |
|-------|-----------------|----------|
| First Name | firstname | ✓ |
| Last Name | lastname | ✓ |
| Business Email | email | ✓ |
| Company | company | |
| Job Title | jobtitle | |

### Form — Hidden Fields
UTM Source · UTM Campaign · Asset Name

### Email Templates (2)
1. **Promotion** [Manual] — cover image, description, Download CTA
2. **Delivery** [Auto] — asset ready, download link, related content

### Automation (5 steps)
Trigger → Delivery email → Add to list → Lifecycle → Lead source

---

## Figma File Structure

```
HubSpot Campaign Designs — Deloitte Israel
├── 00 — Brand & Components
│   ├── Index
│   ├── Brand / Colors
│   ├── Brand / Typography
│   ├── Brand / Logo / Primary + White
│   ├── Brand / Button / Primary + Secondary
│   ├── Brand / Form / Field / (Text, Email, Dropdown, Checkbox, Textarea, Hidden)
│   ├── Brand / Email / (Header, Footer, Hero, CTA Block, Text Block, Divider)
│   └── Brand / LP / (Hero, Form Section, Footer)
├── 01 — Event Campaign
│   ├── Event / Specs
│   ├── Event / Landing Page / Desktop + Mobile
│   ├── Event / Form Spec
│   └── Event / Email / (Invitation, Confirmation, Reminder -1d, Follow-up)
├── 02 — Webinar Campaign
│   ├── Webinar / Specs
│   ├── Webinar / Landing Page / Desktop + Mobile
│   ├── Webinar / Form Spec
│   └── Webinar / Email / (Invitation, Confirmation, Reminder -1d, Reminder -1h, Follow-up + Recording)
├── 03 — Newsletter Campaign
│   ├── Newsletter / Specs
│   ├── Newsletter / Signup Page / Desktop + Mobile
│   ├── Newsletter / Form Spec
│   └── Newsletter / Email / Newsletter Template
└── 04 — Digital Asset Campaign
    ├── Digital Asset / Specs
    ├── Digital Asset / Landing Page / Desktop + Mobile
    ├── Digital Asset / Form Spec
    └── Digital Asset / Email / (Promotion, Delivery)
```
