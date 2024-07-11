---
description: >-
  How to Easily Add SA5's User Info & Advanced Routing Enhancements to Your
  Webflow Memberships Site
---

# 🚀 Quick Start | SA5 SEO

{% hint style="success" %}
All of SA5's Membership features are now consolidated into a single library, so you only need one library include.&#x20;
{% endhint %}

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site. If this functionality is only needed on specific pages, you can add it to those page-specific HEADs instead. &#x20;

{% hint style="warning" %}
Currently no `defer` used during the experimental phase.
{% endhint %}

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | SEO --> 
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.0/dist/webflow-seo.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | SEO --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.1/dist/css/webflow-seo.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-seo.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.1/dist/nocode/webflow-seo.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-seo.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}















