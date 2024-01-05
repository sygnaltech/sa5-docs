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
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.3.16/dist/webflow-seo.js"></script>
```
{% endcode %}

Add the custom attributes for the features you need, described in each feature separately. &#x20;













