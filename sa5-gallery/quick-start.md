---
description: Proxy selects with a dropdown for better styling options
---

# 🚀 Quick Start | SA5 Gallery

{% hint style="danger" %}
UNDER DEVELOPMENT
{% endhint %}

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site. If this functionality is only needed on specific pages, you can add it to those page-specific HEADs instead. &#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Gallery --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.35/dist/css/webflow-gallery.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.35/dist/nocode/webflow-gallery.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Gallery --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.35/dist/css/webflow-gallery.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-gallery.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.35/dist/nocode/webflow-gallery.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-gallery.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}













