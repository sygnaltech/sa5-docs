---
description: >-
  How to Easily Add SA5's User Info & Advanced Routing Enhancements to Your
  Webflow Memberships Site
---

# 🚀 Quick Start | SA5 HTML

{% hint style="success" %}
All of **SA5's HTML** features are now consolidated into a single library, so you only need one library include.&#x20;
{% endhint %}

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="info" %}
This feature is using SA5's new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site. If you are only using it on specific pages, you can add it to **page-specific** custom code instead.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | HTML --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.36/dist/css/webflow-html.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.36/dist/nocode/webflow-html.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | HTML --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.36/dist/css/webflow-html.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-html.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.36/dist/nocode/webflow-html.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-html.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}











