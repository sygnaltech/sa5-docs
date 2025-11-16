---
description: How to Easily Add SA5's Analytics to Your Webflow Site
---

# 🚀 Quick Start | SA5 Analytics

{% hint style="danger" %}
COMING SOON.
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
<!-- Sygnal Attributes 5 | Analytics --> 
<script>
// Routing rules
</script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/css/webflow-analytics.css"> 
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/nocode/webflow-analytics.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Analytics --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/css/webflow-analytics.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-analytics.css"
  group="SA5 Analytics"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/nocode/webflow-analytics.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-analytics.js"
  group="SA5 Analytics"
  ></script>
```
{% endcode %}













