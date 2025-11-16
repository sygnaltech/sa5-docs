---
description: >-
  How to Easily Add SA5's User Info & Advanced Routing Enhancements to Your
  Webflow Memberships Site
---

# 🚀 Quick Start | SA5 Components

{% hint style="danger" %}
UNDER DEVELOPMENT \
These are advanced tools for component developers only.&#x20;
{% endhint %}

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="warning" %}
**IMPORTANT** \
We've made some enhancements to SA5 Core in v5.5.0. \
If you are already using other SA5 Libs, please make certain to upgrade them to at least v5.5.0 as well to ensure cross-compatibility.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site.&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Social Share --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.8.7/dist/css/webflow-components.css"> 
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.8.7/dist/nocode/webflow-components.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal Devmode](https://devmode.sygnal.com/) and [Sygnal DevProxy](https://engine.sygnal.com/devproxy).  These make it easier to develop and test code changes with Webflow sites.&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Components --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.8.7/dist/css/webflow-components.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-components.css"
  group="SA5 Components"
  > 
<script 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.8.7/dist/webflow-components.js" 
  dev-src="http://127.0.0.1:4000/dist/webflow-components.js"
  group="SA5 Components"
  ></script>
```
{% endcode %}













