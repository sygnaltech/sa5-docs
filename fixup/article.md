---
description: Fix common Webflow issues in the Editor and published site.
---

# Webflow Fixups ❺

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

### Unsupported Browser pop-up

Problem- this appears even when you are not logged into the editor.

### ![](<../.gitbook/assets/image (3) (1).png>)

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

{% hint style="info" %}
This feature is using WFU's v5 new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;

You can use both the v4 and v5 libraries simultaneously to get the full feature set during migration.
{% endhint %}

Add this to the **before HEAD** custom code area of your site or page.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Webflow Fixup -->
<script defer
src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.2/dist/nocode/webflow-fixup.min.js"
></script> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.2/dist/css/webflow-fixup.css">
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;



