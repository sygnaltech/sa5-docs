---
description: How to Easily Add SA5's Video Enhancements to Your Webflow Site
---

# 🚀 Quick Start | SA5 Elements

## How to Add the Library   <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="danger" %}
**WEBFLOW CHANGE NOTE | 20-FEB-2025** \
Webflow has [added support for async loading](https://help.webflow.com/hc/en-us/articles/38265301927059-Understanding-per-page-JavaScript-and-asynchronously-loading-JavaScript) of Webflow.js.  This is an optional feature, however it can impact code which uses Webflow.js, such as the SA5 Elements Lib.&#x20;

The safest approach is to disable async loading, to ensure that the library is fully loaded for SA5 Element needs to connect.  However, you can try async, simply make sure to test it well.&#x20;
{% endhint %}

{% hint style="warning" %}
**IMPORTANT** \
We've made some enhancements to SA5 Core in v5.5.0. \
If you are already using other SA5 Libs, please make certain to upgrade them to at least v5.5.0 as well to ensure cross-compatibility.&#x20;
{% endhint %}



[Add this script](../overview/how-to-add-custom-code.md) to the **page-specific** or **site wide** custom code **HEAD** area of your site or page.&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Elements --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.7.1/dist/css/webflow-elements.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.7.1/dist/nocode/webflow-elements.js"></script>
```
{% endcode %}

{% hint style="success" %}
Once the library is installed, use the attributes you want for the specific features you're looking for in this library. Those are documented with each feature.&#x20;
{% endhint %}

Add the custom attributes for the features you need, described in each feature separately.  &#x20;

## SA5 Library Developers&#x20;

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy). &#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Elements --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.7.1/dist/css/webflow-elements.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-elements.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.7.1/dist/nocode/webflow-elements.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-elements.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}



