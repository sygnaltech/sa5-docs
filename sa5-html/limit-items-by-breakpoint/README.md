---
description: >-
  Make your collection list & static content fully responsive by controlling the
  quantity
---

# Limit Items by Breakpoint ❺

Webflow has a built-in **Limit Items** feature on Collection Lists, however it is not [breakpoint](https://university.webflow.com/lesson/intro-to-breakpoints)-sensitive.&#x20;

This often presents a problem for designers because if you're displaying e.g. blog posts in a grid, you may want to show a 4x3 grid at desktop, 3x3 on tablet, 2x2 on mobile landscape and 1x4 on mobile portrait.&#x20;

SA5 allows you to specify and adjust the number of items you want to appear at each breakpoint _dynamically_.&#x20;

### Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/limit-collection-items-by-breakpoint" %}
Cloneable
{% endembed %}

{% hint style="success" %}
If you're unsure of how to apply the documentation, use the demo cloneables above as an implementation reference.&#x20;
{% endhint %}

## Getting Started <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).&#x20;

{% hint style="info" %}
This attribute is CSS-based, and it's possible to paste the `<style>` block directly into an Embed if you want [design time support](./#advanced-note).&#x20;
{% endhint %}

### STEP 2 - Apply the attributes for the limits you want applied <a href="#step-2---apply-the-attributes-for-the-limits-you-want-applied" id="step-2---apply-the-attributes-for-the-limits-you-want-applied"></a>

See below for the attributes.&#x20;

## Usage Notes  <a href="#usage-notes" id="usage-notes"></a>

This attribute uses breakpoint suffixes; which appear like this;&#x20;

```
wfu-limit-items:t = 10
```

The `:t` indicates that this attribute applies to Webflow's tablet breakpoint and below, until it is overridden by another more specific breakpoint like `:l` ( mobile landscape ) or `:p` ( mobile portrait ).&#x20;

It's important to understand the fundamentals of how Webflow's breakpoints work in order to configure this attribute properly.&#x20;

### About Webflow Breakpoints&#x20;

If you're unfamiliar with responsive design in Webflow, breakpoint-specific styling is applied in a desktop-outward fashion-

<img src="../../.gitbook/assets/file.excalidraw (7).svg" alt="" class="gitbook-drawing">

From [Webflow Help Center](https://help.webflow.com/hc/en-us/articles/33961300305811-Breakpoints-overview#01JDAHFPB3NZBQYN7BE61NWH26);&#x20;

Each breakpoint view lets you style elements for a particular viewport range:

* Styles set on the **1920px** breakpoint apply to screens 1920px wide and above
* Styles set on the **1440px** breakpoint apply to screens 1440px wide and above
* Styles set on the **1280px** breakpoint apply to screens 1280px wide and above
* Styles set on the **desktop (base)** breakpoint apply to all devices unless overridden at other device breakpoints
* Styles set on the **tablet** breakpoint apply to screens 991px wide and below
* Styles set on the **mobile landscape** breakpoint apply to screens 767px wide and below
* Styles set on the **mobile portrait** breakpoint apply to screens 478px wide and below

{% hint style="info" %}
Learn how responsiveness works with [Webflow' breakpoints](https://university.webflow.com/videos/intro-to-breakpoints).&#x20;
{% endhint %}

### Using SA5's Limit Items Attributes&#x20;

For each breakpoint-specific attribute, set the value to the number of items you want to show, 1 to 30.&#x20;

{% hint style="success" %}
Place the custom attributes you want on the Collection List element directly ( not the Collection List Wrapper element ). &#x20;
{% endhint %}

| Attribute               | Breakpoints Affected          |
| ----------------------- | ----------------------------- |
| `wfu-limit-items`       | Desktop ( base breakpoint )   |
| `wfu-limit-items:t`     | Tablet, and below             |
| `wfu-limit-items:l`     | Mobile Landscape, and below   |
| `wfu-limit-items:p`     | Mobile Portrait               |
| `wfu-limit-items:1280`  | Large ( 1280+ ), and above    |
| `wfu-limit-items:1440`  | X-Large ( 1440+ ), and above  |
| `wfu-limit-items:1920`  | XX-Large ( 1920+ ), and above |

### Designer support  <a href="#advanced-note" id="advanced-note"></a>

If you want to have the item limits also shown _directly in the Designer_, you can add the CSS code directly into an HTML Embed.&#x20;

[Copy the CSS style block here](designer-css-embed.md)&#x20;

## Notes&#x20;

{% hint style="success" %}
This attribute can be used with `wfu-sort`. Using the `random` setting, it allows you to maintain limited length lists that are re-randomized on every page refresh. &#x20;
{% endhint %}



