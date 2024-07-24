---
description: How to Easily Add SA5's Video Enhancements to Your Webflow Site
---

# 🚀 Quick Start | SA5 Elements

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

[Add this script](../overview/how-to-add-custom-code.md) to the **page-specific** or **site wide** custom code **HEAD** area of your site or page.&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Elements --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.7/dist/css/webflow-elements.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.7/dist/nocode/webflow-elements.js"></script>
```
{% endcode %}

{% hint style="success" %}
Once the library is installed, use the attributes you want for the specific features you're looking for in this library. Those are documented with each feature.&#x20;
{% endhint %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Elements --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.7/dist/css/webflow-elements.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-elements.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.7/dist/nocode/webflow-elements.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-elements.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}



