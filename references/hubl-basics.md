# HubL Basics for GitHub Copilot
## HubSpot's Templating Language — Quick Reference

HubL (HubSpot Markup Language) is HubSpot's templating language. It's Jinja2-based.
Use this file as context when Copilot writes HubSpot templates.

---

## File Types

| File | Extension | Purpose |
|------|-----------|---------|
| Landing page template | `.html` | Full page layout |
| Email template | `.html` | Email layout |
| Module | folder with `meta.json`, `module.html`, `module.css`, `module.js`, `fields.json` | Reusable component |
| Stylesheet | `.css` | Styles |
| Global partial | `.html` | Shared header/footer |

---

## Core HubL Syntax

### Variables
```hubl
{{ content.name }}
{{ page.meta_description }}
{{ request.current_page.id }}
```

### Editable Regions — Drag & Drop Areas
```hubl
{% dnd_area "main" label="Main Content" %}
  {% dnd_section %}
    {% dnd_column %}
      {% dnd_row %}
        {% dnd_module "module_name" path="@hubspot/rich_text" %}
        {% end_dnd_module %}
      {% end_dnd_row %}
    {% end_dnd_column %}
  {% end_dnd_section %}
{% end_dnd_area %}
```

### Standard Modules (path references)
```hubl
{# Rich Text #}
{% dnd_module path="@hubspot/rich_text" %}{% end_dnd_module %}

{# Image #}
{% dnd_module path="@hubspot/image" %}{% end_dnd_module %}

{# Form #}
{% dnd_module path="@hubspot/form" %}{% end_dnd_module %}

{# CTA #}
{% dnd_module path="@hubspot/cta" %}{% end_dnd_module %}

{# Divider #}
{% dnd_module path="@hubspot/divider" %}{% end_dnd_module %}

{# Social Follow #}
{% dnd_module path="@hubspot/social_follow" %}{% end_dnd_module %}

{# Video #}
{% dnd_module path="@hubspot/video" %}{% end_dnd_module %}

{# Spacer #}
{% dnd_module path="@hubspot/spacer" %}{% end_dnd_module %}
```

### Module Default Values
```hubl
{% dnd_module path="@hubspot/rich_text"
  html="<h1>Default Headline</h1><p>Default body text.</p>"
%}{% end_dnd_module %}

{% dnd_module path="@hubspot/form"
  form_id=""
  response_type="redirect"
  redirect_url=""
  message="Thank you for registering!"
%}{% end_dnd_module %}
```

### Section with Background Color
```hubl
{% dnd_section
  background_color={{ "r": 0, "g": 0, "b": 0, "a": 1 }}
  padding={{ "top": 80, "bottom": 80, "left": 24, "right": 24 }}
%}
{% end_dnd_section %}
```

### Section with Background Image
```hubl
{% dnd_section
  background_image={{ "src": "https://example.com/image.jpg", "size_type": "cover" }}
  background_color={{ "r": 0, "g": 0, "b": 0, "a": 0.6 }}
%}
{% end_dnd_section %}
```

### Column Width (12-column grid)
```hubl
{% dnd_column width=6 %}  {# 50% width #}
{% dnd_column width=4 %}  {# 33% width #}
{% dnd_column width=8 %}  {# 66% width #}
{% dnd_column width=12 %} {# 100% width #}
```

---

## Full Landing Page Template Structure

```hubl
<!--
  Template: Event Campaign Landing Page
  Portal: Deloitte Israel
  Author: Natan Yagodaev
-->

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ content.html_title }}</title>
  {{ standard_header_includes }}
  <link rel="stylesheet" href="{{ get_asset_url('../../css/deloitte-theme.css') }}">
</head>
<body class="deloitte-template">

  {# Global Header #}
  {% global_partial path="../../partials/deloitte-header.html" %}

  {# Main drag-and-drop area #}
  {% dnd_area "main_content" label="Page Content" %}

    {# Hero Section — Variant A (dark background, centered) #}
    {% dnd_section
      background_color={{ "r": 0, "g": 0, "b": 0, "a": 1 }}
      padding={{ "top": 100, "bottom": 100, "left": 24, "right": 24 }}
    %}
      {% dnd_column width=12 %}
        {% dnd_row %}
          {% dnd_module path="@hubspot/rich_text"
            html="<h1 style='color:#fff;text-align:center;font-size:48px;'>Event Title</h1><p style='color:#ccc;text-align:center;font-size:20px;'>Date · Location</p>"
          %}{% end_dnd_module %}
        {% end_dnd_row %}
        {% dnd_row %}
          {% dnd_module path="@hubspot/cta" %}{% end_dnd_module %}
        {% end_dnd_row %}
      {% end_dnd_column %}
    {% end_dnd_section %}

    {# Form Section #}
    {% dnd_section
      background_color={{ "r": 255, "g": 255, "b": 255, "a": 1 }}
      padding={{ "top": 80, "bottom": 80, "left": 24, "right": 24 }}
    %}
      {% dnd_column width=6 offset=3 %}
        {% dnd_row %}
          {% dnd_module path="@hubspot/form" %}{% end_dnd_module %}
        {% end_dnd_row %}
      {% end_dnd_column %}
    {% end_dnd_section %}

  {% end_dnd_area %}

  {# Global Footer #}
  {% global_partial path="../../partials/deloitte-footer.html" %}

  {{ standard_footer_includes }}
</body>
</html>
```

---

## Custom Module Structure

Every custom module is a folder with these files:

```
deloitte-hero-a/
├── meta.json         ← Module metadata
├── fields.json       ← Editable fields definition
├── module.html       ← Template markup
├── module.css        ← Module styles
└── module.js         ← Module scripts (optional)
```

### meta.json
```json
{
  "label": "Deloitte Hero A — Dark Centered",
  "css_assets": [],
  "external_js": [],
  "global": false,
  "help_text": "Dark background hero with centered text and CTA. Use for Event and Webinar campaigns.",
  "host_template_types": ["LANDING_PAGE", "PAGE"],
  "js_assets": [],
  "other_assets": [],
  "smart_type": "NOT_SMART",
  "tags": ["deloitte", "hero"],
  "is_available_for_new_content": true
}
```

### fields.json (example for hero)
```json
[
  {
    "name": "headline",
    "label": "Headline",
    "type": "text",
    "default": "Event Title"
  },
  {
    "name": "subheadline",
    "label": "Subheadline",
    "type": "text",
    "default": "Date · Location"
  },
  {
    "name": "cta_text",
    "label": "CTA Button Text",
    "type": "text",
    "default": "Register Now"
  },
  {
    "name": "cta_url",
    "label": "CTA Button URL",
    "type": "link",
    "default": { "url": { "href": "#form" } }
  },
  {
    "name": "background_color",
    "label": "Background Color",
    "type": "color",
    "default": { "r": 0, "g": 0, "b": 0, "a": 100 }
  }
]
```

### module.html (hero example)
```hubl
<section class="deloitte-hero deloitte-hero--variant-a"
  style="background-color: rgba({{ module.background_color.r }}, {{ module.background_color.g }}, {{ module.background_color.b }}, {{ module.background_color.a / 100 }});">
  <div class="deloitte-hero__content">
    <h1 class="deloitte-hero__headline">{{ module.headline }}</h1>
    <p class="deloitte-hero__subheadline">{{ module.subheadline }}</p>
    <a href="{{ module.cta_url.url.href }}" class="deloitte-btn deloitte-btn--primary">
      {{ module.cta_text }}
    </a>
  </div>
</section>
```

---

## Deloitte CSS Variables

Always define in `deloitte-theme.css`:

```css
:root {
  --deloitte-green: #86BC25;
  --deloitte-black: #000000;
  --deloitte-grey-dark: #53565A;
  --deloitte-grey-light: #D0D0CE;
  --deloitte-white: #FFFFFF;

  --font-primary: 'Arial', sans-serif;

  --spacing-xs: 8px;
  --spacing-sm: 16px;
  --spacing-md: 24px;
  --spacing-lg: 48px;
  --spacing-xl: 80px;

  --container-max: 1200px;
  --content-max: 800px;
  --email-max: 600px;

  --radius-sm: 4px;
  --radius-md: 8px;

  --btn-height: 52px;
}
```
