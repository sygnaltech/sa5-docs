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

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this feature, so we’ll use a _no-code_ integration approach.

Install JS in **HEAD**, generally site-wide.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Urls -->
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@v5.2.5/dist/nocode/webflow-url.min.js"></script>
```
{% endcode %}

### STEP 2 - Create Links as desired <a href="#step-2---create-cms-links-as-desired" id="step-2---create-cms-links-as-desired"></a>

See above notes for the supported formats.

\
