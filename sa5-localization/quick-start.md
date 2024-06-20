---
description: How to Setup SA5's 404 Library
---

# 🚀 Quick Start | SA5 Localization

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

{% hint style="info" %}
This feature is using SA5's new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the custom code **HEAD** area of your **404 page** only.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | 404 -->
<script defer
src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.0/dist/nocode/webflow-404.js"></script> 
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;
