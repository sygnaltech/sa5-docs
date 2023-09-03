---
description: Get started with SA5 Cache
---

# 🚀 Quick Start | SA5 Cache

{% hint style="warning" %}
SA5 Cache is primarily an internal mechanism within the library, and may be come part of SA5 Core. We're considering whether an how to make it accessible and usable by other devs in their projects.&#x20;
{% endhint %}

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="info" %}
This feature is using SA5's new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site. If you are only using it on specific pages, you can add it to **page-specific** custom code instead.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Cache --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.32/dist/css/webflow-cache.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.32/dist/nocode/webflow-cache.js"></script>
```
{% endcode %}













