---
description: How to Easily Add SA5's Data & Data-Binding to your Webflow Site
---

# 🚀 Quick Start | SA5 Data & Data-Binding

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="info" %}
This feature is using SA5's new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site. If you are only using it on specific pages, you can addit to **page-level** custom code instead.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Data & Data-Binding --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.3.2/dist/css/webflow-data.css"> 
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.3.2/dist/nocode/webflow-data.js"></script>
```
{% endcode %}











