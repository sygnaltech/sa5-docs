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

### Add the SA5 Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### I want this text element to be truncated to N lines

Add the `wfu-truncate` custom attribute to apply truncation to any text element. If it exceeds the line count you specify, you'll see an ellipses ( ... ) at the point of truncation.&#x20;

Use a value of `1` to `5` to specify the number of lines.

e.g.;

```
wfu-truncate = 3
```

{% hint style="info" %}
Truncation will only appear in the published site, not in the designer.
{% endhint %}

\
