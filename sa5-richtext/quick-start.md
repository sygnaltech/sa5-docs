---
description: How to Easily Add SA5's Rich Text Enhancements to Your Webflow Site
---

# 🚀 Quick Start | SA5 Rich Text

{% hint style="success" %}
All of SA5's Rich Text features are now consolidated into a single library, so you only need one library include.&#x20;
{% endhint %}

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="info" %}
This feature is using SA5's new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site. If you are only using it on specific pages, you can add it to **page-specific** custom code instead.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Rich Text --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.0/dist/css/webflow-richtext.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.0/dist/nocode/webflow-richtext.js"></script>
```
{% endcode %}













