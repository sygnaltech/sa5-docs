---
description: Create dynamic layouts in your Webflow-hosted site
---

# Layout ❺🧪

{% hint style="info" %}
**BETA.** This library is released in BETA. Questions or problems should be directed to the forum, link above.
{% endhint %}

Webflow is great at creating static pages but the layouts come with inherent structural limitations that are sometimes difficult to work around.

SA5 Layout was designed to make complex layouts much easier by allowing elements to be moved after the page has loaded.&#x20;

{% hint style="success" %}
**SA5 Layout** is a _very_ flexible library. Because it has such a wide range of use cases, it can be difficult to understand its massive range of applications. Spend some time in the docs and demos and feel free to ask questions in the forum.&#x20;
{% endhint %}

## Use Cases

* Combine collection lists&#x20;
* Handle complex layout requirements that would typically require a large number of collection lists
  * e.g. a calendar view&#x20;
* Overcome nested-item limits in collection lists
* Push static elements into a collection list&#x20;
* Group elements on your page under grouping headings&#x20;
* Build hierarchical site navigations

CMS-bound tabs;&#x20;

* Create tabs dynamically from a collection list
* Create dynamic, nested tabs e.g. country level and a city level, from CMS data&#x20;

## Features&#x20;

* Tag any DIV as a named container element with a custom attribute
* Tag any other elements to be moved into that DIV on page load
* Use CMS-bound custom attributes to create CMS-driven groupings and layouts &#x20;

## Demonstration

{% embed url="https://cms-layouts.webflow.io/" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/cms-layouts" %}
Cloneable
{% endembed %}

## Usage - Layout Container

### I want this DIV / tabs element to be the target container for layout operations&#x20;

`wfu-layout` = ( layout container name )

**layout container name** can be any unique arbitrary string to identify that container. It can also be bound to a collection list slug for more dynamic, powerful layouts. &#x20;

### I want to restrict layouts to a zone ( advanced )&#x20;

`wfu-layout-zone` ( optional ) = ( layout container namespace )

**Optional.** Recommended when `wfu-layout` is bound to a CMS slug. &#x20;

For complex nested layouts, the wfu-layout is often bound to a CMS item slug. To prevent conflicts, you can also create a namespace in the form of a zone.&#x20;

{% hint style="info" %}
When a layout container has a zone specified, it will only accept layout items which match both the container name and the zone attributes.&#x20;
{% endhint %}

### I want to use the following layout handler

`wfu-layout-handler` (optional)

* `auto` (default) - select the appropriate handler for the element
* `default` - do not use a handler, this is the case for standard DIV layouts&#x20;
* `tabs` - must be placed on a tabs outer element &#x20;
* `slider` - must be placed on a slider outer element

### Initialize the container (optional)

`wfu-layout-init` (optional)

* `none` (default) - do nothing&#x20;
* `clear` - clear the contents / tabs / slides before layout&#x20;

### Prior to loading the layout, I want the container to appear as...&#x20;

`wfu-preload`&#x20;

* `visible` ( default ) - keep the element visible&#x20;
* `hidden` - completely hidden from view
* `invisible` - takes up space but otherwise not visible&#x20;

## Usage - Layout Item

### Target the item

`wfu-layout-target` = ( layout container name )

Identifies the container this element should be moved to.&#x20;

### I want to restrict layouts to a zone ( advanced )&#x20;

`wfu-layout-zone` ( optional ) = ( layout container namespace )

**Optional.** Recommended when `wfu-layout` is bound to a CMS slug. &#x20;

For complex nested layouts, the wfu-layout is often bound to a CMS item slug. To prevent conflicts, you can also create a namespace in the form of a zone.&#x20;

{% hint style="info" %}
When a layout item has a zone specified, it will only be moved to zones which match both the container name and the zone attributes.&#x20;
{% endhint %}

{% hint style="success" %}
**NAMESPACES**

In Webflow, `wfu-layout` is often easily used with CMS data-bound attributes and item slugs.  Since this can create multiple targets with the same name on a page, you can use `wfu-layout-zone` with an arbitrary identifier to isolate these areas and prevent namespace conflicts or overlaps.&#x20;
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../sa5-html/quick-start.md).&#x20;

### STEP 2 - Apply the custom attributes as desired <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.



