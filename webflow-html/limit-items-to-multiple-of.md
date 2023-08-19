---
description: Limit a list to a multiple of X items
---

# Limit Items to Multiple-of ❺

## Use Cases

* Layout your collection lists in grids and show the maximum number of items available while limiting the items to an even multiple.

## Demonstration

{% embed url="https://webflow-smart-elements.webflow.io/collection-lists" %}
Demonstration site
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneables
{% endembed %}

{% embed url="https://codepen.io/memetican/pen/VwBEEeL/dd18f85cbd0e7cf9d0387b20b8d50899" %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### `wfu-limit-multiple` attribute <a href="#wfu-limit-items-attribute" id="wfu-limit-items-attribute"></a>

Place on any Collection List directly ( not the Collection List Wrapper ).

Specify the multiple of items you want to show, e.g. 2, 3, 4, 5. The list will be limited to a multiple of the number you specify.

{% hint style="info" %}
If your list has fewer items than your multiple, you will get zero.
{% endhint %}

### `wfu-limit-multiple-min` attribute <a href="#wfu-limit-items-attribute" id="wfu-limit-items-attribute"></a>

OPTIONAL.

If you want to make certain a minimum number of items appears, you can also apply this attribute to specify that minimum number.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply the attributes for the limits you want applied <a href="#step-2---apply-the-attributes-for-the-limits-you-want-applied" id="step-2---apply-the-attributes-for-the-limits-you-want-applied"></a>

See above for details.

\
