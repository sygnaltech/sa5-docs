---
description: >-
  How to Easily Add SA5's User Info & Advanced Routing Enhancements to Your
  Webflow Memberships Site
---

# 🚀 Quick Start | SA5 Detect

{% hint style="danger" %}
UNDER DEVELOPMENT&#x20;
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
<!-- Sygnal Attributes 5 | Detect --> 
<script>
// Routing rules
</script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.5.0/dist/css/webflow-detect.css"> 
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.5.0/dist/nocode/webflow-detect.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Detect --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.5.0/dist/css/webflow-detect.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-detect.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.5.0/dist/nocode/webflow-detect.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-detect.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}













