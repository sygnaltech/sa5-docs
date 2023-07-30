---
description: Line-Clamp your plain-text content to a maximum number of lines, for layout.
---

# Truncate Text w/ Ellipsis ❺

## Overview&#x20;

Often, it is desirable to truncate plain text excerpts so that they do not break your layout, particularly when that text is variable ( coming from the CMS ), and when your layout involves a grid arrangement such as a card layout.

Modern CSS does provide a solution for this, but the required settings are not built into the Webflow designer \[yet].

So, here’s a solution that gives you what you need.&#x20;

{% hint style="info" %}
Custom CSS is applied only in your published site, so you will not see the truncation in the designer.
{% endhint %}

## Demonstration <a href="#demonstration" id="demonstration"></a>

{% embed url="https://webflow-smart-elements.webflow.io/line-clamping" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### `wfu-truncate` attribute <a href="#wfu-truncate-attribute" id="wfu-truncate-attribute"></a>

Use `wfu-truncate` to apply truncation to a text element.

Use a value of `1` to `5` to specify the number of lines.

e.g.;

```
wfu-truncate = 3
```

{% hint style="warning" %}
**Recently tested on Chrome ONLY.**\
Please double check your desired browsers to make sure the CSS works for your target audience.
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this code to the **before HEAD** of your site or page.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | HTML -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.10/dist/css/webflow-html.min.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.10/dist/nocode/webflow-html.js"></script>
```
{% endcode %}

### STEP 2 - Apply `wfu-truncate` to your text elements <a href="#step-2---apply-wfu-truncate-to-your-text-elements" id="step-2---apply-wfu-truncate-to-your-text-elements"></a>

See above for details.

\
