---
description: How to Setup SA5's Embeds Library
---

# 🚀 Quick Start | SA5 Embeds

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

{% hint style="info" %}
This feature is using SA5's new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the custom code **HEAD** area of your **404 page** only.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Embeds -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.3.14/dist/css/webflow-embed.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.3.14/dist/nocode/webflow-embed.js"></script> 
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;
