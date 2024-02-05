---
description: Automatically open external links in a new tab
---

# External Link Targeting ❺

{% hint style="success" %}
We are planning to move this into the Rich Text lib.
{% endhint %}

In most situations, you will automatically want external links to open in a new tab.

This library automatically looks for FQDN links such as `https://...` and adds a `target=_blank`.

It will only add a target if none is specified.

## Demonstration

{% embed url="https://url-tracking.webflow.io/external-links" %}
Demonstration page
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/url-tracking" %}
Cloneable site
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Add the `wfu-external-links` custom attribute to any link, text, or richtext element. Can also be added to DIVs.&#x20;

## Configuration

This library has extensive configuration options.&#x20;

{% hint style="info" %}
All **SA5 Url** lib features are handled in a single `urlConfig` configuration block, however feature-specific configurations are represented as sub objects. Typically you can enable or disable a feature, and provide a custom configuration if you choose.
{% endhint %}

Here is an example configuration for External link targeting;&#x20;

```html
<!-- Sygnal Attributes 5 | Url | Config -->
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['urlConfig', 
  (config) => {
    config.targetExternal = true;
    return config;
  }]); 
</script>
```

### Options&#x20;

#### targetExternal = true | false

Enables or disables external targeting. Defaults to false.&#x20;

## Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Add your Configuration Callback

Add this configuration section above right after the library in your **before HEAD** custom code. Typically this will be in the site-wide custom code configuration. \
