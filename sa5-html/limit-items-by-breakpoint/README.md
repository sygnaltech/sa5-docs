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

### STEP 2 - Apply the attributes for the limits you want applied <a href="#step-2---apply-the-attributes-for-the-limits-you-want-applied" id="step-2---apply-the-attributes-for-the-limits-you-want-applied"></a>

See below for the attributes.&#x20;

## Usage Notes  <a href="#usage-notes" id="usage-notes"></a>

### About Webflow Breakpoints&#x20;

From [Webflow Help Center](https://help.webflow.com/hc/en-us/articles/33961300305811-Breakpoints-overview#01JDAHFPB3NZBQYN7BE61NWH26);&#x20;

Each breakpoint view lets you style elements for a particular viewport range:

* Styles set on the **1920px** breakpoint apply to screens 1920px wide and above
* Styles set on the **1440px** breakpoint apply to screens 1440px wide and above
* Styles set on the **1280px** breakpoint apply to screens 1280px wide and above
* Styles set on the **desktop (base)** breakpoint apply to all devices unless overridden at other device breakpoints
* Styles set on the **tablet** breakpoint apply to screens 991px wide and below
* Styles set on the **mobile landscape** breakpoint apply to screens 767px wide and below
* Styles set on the **mobile portrait** breakpoint apply to screens 478px wide and below



<img src="../../.gitbook/assets/file.excalidraw (7).svg" alt="" class="gitbook-drawing">





Place the custom attributes you want on the Collection List element directly ( not the Collection List Wrapper element ).&#x20;

For each breakpoint-specific attribute, set the value to the number of items you want to show, 1 to 30.&#x20;

{% hint style="success" %}
SA5's breakpoint-specific attributes works the same way that Webflow's breakpoints work
{% endhint %}



| Attribute               | Breakpoints Affected            | Notes                           |
| ----------------------- | ------------------------------- | ------------------------------- |
| `wfu-limit-items`       | Desktop ( base breakpoint )     | the number to show for desktops |
| `wfu-limit-items:t`     | Tablet ( and below )            |                                 |
| `wfu-limit-items:l`     | Mobile Landscape ( and below )  |                                 |
| `wfu-limit-items:p`     | Mobile Portrait                 |                                 |
| `wfu-limit-items:1280`  | Large ( 1280+ )                 |                                 |
| `wfu-limit-items:1440`  | X-Large ( 1440+ )               |                                 |
| `wfu-limit-items:1920`  | XX-Large ( 1920+ )              |                                 |
|                         |                                 |                                 |









{% hint style="warning" %}
IMPORTANT\
This attribute works by hiding extra items.  The Collection List itself must contain enough items&#x20;
{% endhint %}

&#x20;

{% hint style="info" %}
This is most commonly used in combination with `wfu-sort`, using the `random` setting. With the combination of random sorting and item limits, you can display a random set of items on every page refresh.
{% endhint %}

### Advanced note <a href="#advanced-note" id="advanced-note"></a>

If you want to have the item limits also shown _directly in the Designer_, you can add the CSS code directly into an HTML Embed. Copy and paste the code below. It's longer than it looks, however it will fit within Webflow's 10,000 character limit.

```html
<!-- Limit Items by Breakpoint | Sygnal Attributes -->
<style>
@media screen {[wfu-limit-items="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 1920px) {[wfu-limit-items-1920="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 1440px) and (max-width: 1919px) {[wfu-limit-items-1440="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 1280px) and (max-width: 1439px) {[wfu-limit-items-1280="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 992px) {[wfu-limit-items-d-max="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 992px) and (max-width: 1279px) {[wfu-limit-items-d="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 768px) and (max-width: 991px) {[wfu-limit-items-t="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 480px) and (max-width: 767px) {[wfu-limit-items-l="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (max-width: 479px) {[wfu-limit-items-p="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}
 </style>
```

{% hint style="success" %}
Place the HTML Embed inside of your site-wide nav or footer symbol if you want it to be available on all pages.&#x20;
{% endhint %}



