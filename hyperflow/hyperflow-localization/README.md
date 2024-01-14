---
description: Add capabilities to Webflow's Localization features
---

# Hyperflow Localization

See subpages for features we're exploring.&#x20;

* Locale path fixes
* Locale-specific domains
* Programmatic detection & control

## SA5 Functionality



* Get current locale
* Get locales
* Set locale
* Remember locale
* Get preferred locale

Fixes Needed\
As of 06-Dec-2023;&#x20;
------------------------

Add self-referencing hreflang tags, and possibly x-default;&#x20;

```html
<link rel="alternate" hreflang="en" href="https://www.example.com/"/>
<link rel="alternate" hreflang="zh" href="https://www.example.com/zh/"/>
<link rel="alternate" hreflang="x-default" href="https://www.example.com/"/>
```

Sitemap.xml looks good.&#x20;
