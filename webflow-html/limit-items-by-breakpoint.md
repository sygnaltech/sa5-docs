# Limit Items by Breakpoint

## Overview

Webflow has a built-in **Limit Items** feature on Collection Lists, however it is not [breakpoint](https://university.webflow.com/lesson/intro-to-breakpoints)-sensitive.

This Sygnal Attributes solution dynamically adjusts the number of items shown for the breakpoint that the site is being viewed at, with no refresh needed.

### Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/limit-collection-items-by-breakpoint" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Place the custom attributes you want on the Collection List element directly ( not the Collection List Wrapper element ).&#x20;

For each attribute you use, specify the number of items you want to show from 1 to 12.&#x20;

{% hint style="danger" %}
Important, use only ONE of these configuration approaches per collection list.
{% endhint %}

### OPTION 1 - Use the Desktop-max, Tablet, and Mobile configs <a href="#or-use-the-breakpoint-variations" id="or-use-the-breakpoint-variations"></a>

Use this when you want breakpoint-specific item counts, but desktop and higher breakpoints should all show the same item count.&#x20;

See [demonstration](https://limit-collection-items-by-breakpoint.webflow.io/desktop).

* `wfu-limit-items-D-max` the number to show for desktops and _higher breakpoints_
* `wfu-limit-items-T` the number to show for tablet
* `wfu-limit-items-L` the number to show for mobile landscape
* `wfu-limit-items-P` the number to show for mobile portrait

### OPTION 2 - Specify _every_ breakpoint config <a href="#or-use-the-breakpoint-variations" id="or-use-the-breakpoint-variations"></a>

Use this if you want breakpoint-specific counts at every breakpoint.&#x20;

See [demonstration](https://limit-collection-items-by-breakpoint.webflow.io/).

* `wfu-limit-items-1920` the number to show for 1920px
* `wfu-limit-items-1440` the number to show for 1440px
* `wfu-limit-items-1280` the number to show for 1280px
* `wfu-limit-items-D` the number to show for desktops
* `wfu-limit-items-T` the number to show for tablet
* `wfu-limit-items-L` the number to show for mobile landscape
* `wfu-limit-items-P` the number to show for mobile portrait

{% hint style="warning" %}
Make sure to specify all 7. Skipping any will have unpredictable CSS behavior.
{% endhint %}

### OPTION 3 - Use the global `wfu-limit-items` attribute <a href="#wfu-limit-items-attribute" id="wfu-limit-items-attribute"></a>

This will limit all items, at all breakpoints.

{% hint style="info" %}
This is most commonly used in combination with `wfu-sort`, using the `random` setting. With the combination of random sorting and item limits, you can display a random set of items on every page refresh.
{% endhint %}

### Advanced note <a href="#advanced-note" id="advanced-note"></a>

If you want to have the item limits also shown directly in the Designer, you can add the CSS code directly into an HTML Embed. Copy and paste the code below. It's longer than it looks, however it will fit within Webflow's 10,000 character limit.

```html
<!-- Limit Items by Breakpoint | Sygnal Attributes -->
<style>
@media screen {[wfu-limit-items="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 1920px) {[wfu-limit-items-1920="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-1920="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 1440px) and (max-width: 1919px) {[wfu-limit-items-1440="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-1440="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 1280px) and (max-width: 1439px) {[wfu-limit-items-1280="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-1280="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 992px) {[wfu-limit-items-d-max="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-d-max="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 992px) and (max-width: 1279px) {[wfu-limit-items-d="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-d="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 768px) and (max-width: 991px) {[wfu-limit-items-t="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-t="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (min-width: 480px) and (max-width: 767px) {[wfu-limit-items-l="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-l="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}@media screen and (max-width: 479px) {[wfu-limit-items-p="1"] > div:nth-child(n+2):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="2"] > div:nth-child(n+3):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="3"] > div:nth-child(n+4):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="4"] > div:nth-child(n+5):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="5"] > div:nth-child(n+6):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="6"] > div:nth-child(n+7):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="7"] > div:nth-child(n+8):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="8"] > div:nth-child(n+9):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="9"] > div:nth-child(n+10):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="10"] > div:nth-child(n+11):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="11"] > div:nth-child(n+12):nth-child(-n+1000) {display: none;}[wfu-limit-items-p="12"] > div:nth-child(n+13):nth-child(-n+1000) {display: none;}}
 </style>
```

{% hint style="success" %}
Place the HTML Embed inside of your site-wide nav or footer symbol if you want it to be available on all pages.&#x20;
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/dist/css/webflow-html.min.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/nocode/webflow-html.min.js"></script>
```
{% endcode %}

### STEP 2 - Apply the attributes for the limits you want applied <a href="#step-2---apply-the-attributes-for-the-limits-you-want-applied" id="step-2---apply-the-attributes-for-the-limits-you-want-applied"></a>

See above for details.

\


{% embed url="https://wfu.sygnal.com/docs/webflow-html/limit-items-by-breakpoint/" %}
