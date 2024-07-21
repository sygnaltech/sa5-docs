---
description: Create dynamic layouts in your Webflow-hosted site
---

# Layout ❺

Webflow is great at designing static pages but its CMS layouts come with inherent structural limitations that can be difficult to work around.

* 100 collection items limit in a list
* 5 nested collection items in a nested list
* "closed" lists, i.e. no built in support for inserting static content in with your dynamic content
* no CMS support for UX's like tabs&#x20;

SA5 Layout was designed to make complex layouts much easier by allowing elements to be moved automatically _after_ the page has loaded, and we do this with a very versatile item / slot tagging approach.&#x20;

**In the broadest sense tag any container element ( e.g. a DIV ) as a slot, and tag any elements as items to be put into that slot, and SA5's Layout engine will reorganize your entire page according to those rules.**&#x20;

{% hint style="success" %}
**SA5 Layout** is a _very_ flexible library. Because it has such a wide range of use cases, it can be difficult to understand its massive range of applications. Spend some time in the docs and demos and feel free to ask questions in the forum.&#x20;
{% endhint %}

## Use Cases

* Combine collection lists, even from different collection sources
* Handle complex layout requirements that would typically require a large number of collection lists
  * e.g. events into a 31-slot month calendar view&#x20;
* Overcome nested-item limits in collection lists
* Push static elements into a collection list&#x20;
* Group elements on your page under grouping headings&#x20;
  * e.g. a glossary of terms and A-Z groupings&#x20;
* Build hierarchical site navigations

CMS-bound tabs;&#x20;

* Create tabs dynamically from a collection list
* Create dynamic, nested tab arrangements
  * e.g. country level tabs containing city level tabs, from CMS data&#x20;

## Demonstration

{% embed url="https://sa5-layout.webflow.io" %}
Demos
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/sa5-layout" %}
Cloneable
{% endembed %}

## Usage Notes - Configuring a Layout Container

{% hint style="info" %}
A layout container is container element
{% endhint %}

### I want this container element to be a target container for layout operations&#x20;

`wfu-layout` = ( layout container name )&#x20;

**layout container name** can be any unique arbitrary string to identify that container. It can also be bound to a collection list slug for more dynamic, powerful layouts. &#x20;

### I want to restrict layouts to a namespace ( advanced )&#x20;

**Optional.** This is used to namespace container names and avoid conflicts when there is a possibility of duplication.  Recommended when `wfu-layout` is bound to a CMS slug.&#x20;

`wfu-layout-ns` = ( layout container namespace )

{% hint style="info" %}
For complex nested layouts, the wfu-layout is often bound to a CMS item slug and in a complex page layout there is a possibility of naming conflicts. To prevent conflicts, you can also define a namespace.&#x20;

When a layout container has a namespace specified, it will only accept layout items which match _both_ the container name and the namespace attributes.&#x20;
{% endhint %}

### Use a specific layout handler

**Optional.** Allows you to use specialized handlers, which e.g. create tabs&#x20;

`wfu-layout-handler` = ( handler type )

* `auto` ( default ) - select the appropriate handler for the element, based on the element you've applied the layout attribute to.&#x20;
* `default` - do not use a handler, this is the case for standard DIV layouts&#x20;
* `tabs` - must be placed on a tabs outer element &#x20;
* `slider` - must be placed on a slider outer element

### Initialize the container

**Optional.** If desired, you can specify how the container is initialized before loading.&#x20;

`wfu-layout-init` = ( setting )

* `none` ( default ) - do nothing&#x20;
* `clear` - clear the contents / tabs / slides before layout&#x20;

{% hint style="info" %}
The primary reason for this is that in the designer, you may want to use placeholder content inside of your container just to facilitate layout and design work.  That content may not be relevant to the published page, so you can have it cleared automatically if you prefer.&#x20;
{% endhint %}

### Prior to loading the layout, I want the container to appear as...&#x20;

`wfu-preload`&#x20;

* `visible` ( default ) - keep the element visible&#x20;
* `hidden` - completely hidden from view
* `invisible` - takes up space but otherwise not visible&#x20;

## Usage Notes - Configuring a Layout Item

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

## Release Notes <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Post-beta, we've changed `wfu-layout-zone` to `wfu-layout-ns`

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../sa5-html/quick-start.md).&#x20;

### STEP 2 - Apply the custom attributes as desired <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.



