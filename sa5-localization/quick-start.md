---
description: How to Setup SA5's 404 Library
---

# 🚀 Quick Start | SA5 Localization

## How to Add the Library  <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="warning" %}
**IMPORTANT** \
We've made some enhancements to SA5 Core in v5.5.0. \
If you are already using other SA5 Libs, please make certain to upgrade them to at least v5.5.0 as well to ensure cross-compatibility.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site. If this functionality is only needed on specific pages, you can add it to those page-specific HEADs instead. &#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Localization --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/css/webflow-localization.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/nocode/webflow-localization.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Localization --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/css/webflow-localization.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-localization.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/nocode/webflow-localization.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-localization.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}



