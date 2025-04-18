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

## Use Cases

* Build a week-calendar view, where items are grouped by weekday ( using only one collection list )&#x20;
* Build a month-calendar view, where items are grouped by date ( using only one collection list ) &#x20;
* A-Z bar, with glossary items organized under each group heading ( using only one collection list ).  Currently requires each item to be "tagged" for the group it will be placed in, which can be easily stored in a separate CMS field.&#x20;
* Dynamic tab generation, from a collection list&#x20;
* Complex, CMS-based nested tab generation

Future;&#x20;

* Dynamic slide generation, from a collection list&#x20;
* "Grouped" items, with max-count&#x20;
* A-Z bar, with glossary items automatically organized into those groupings based on the first letter
  * May not support localization, if translated terms start with e.g. an A-umlaut. In localized sites the manual grouping may be more effective here.   &#x20;

## Goals

* Flexible rearrangement of the page
* Support for specific use cases above&#x20;
* Ability to have placeholder content in a group that is only replaced when items are added ( this allows a no items default )&#x20;
  * e.g. A-Z glossary but "no terms yet" on empty groups &#x20;
* Ability to suppress an entire container in which no items are inserted.&#x20;
  * e.g. A-Z glossary but we don't want empty letters&#x20;
* Group item counts
  * Possibly supported even outside of the target group&#x20;

## How it Works&#x20;

**In the broadest sense tag any container element ( e.g. a DIV ) as a slot, and tag any elements as items to be put into that slot, and SA5's Layout engine will reorganize your entire page according to those rules.**&#x20;

_Here is a exceptionally simple example of how elements can be targeted to containers, and re-organized on page load.  The_ `wfu-layout-target` _attribute is used to match and identify the wfu_`-layout` _container, and the element is moved._

<img src="../../.gitbook/assets/file.excalidraw (2) (1) (1).svg" alt="" class="gitbook-drawing">

This technique can expanded in many ways;

* Use CMS custom attribute binding and slugs to dynamically define containers, for example country groupings, or product category groupings.&#x20;
* Use CMS custom attribute binding and slugs to dynamically define and target your items to those containers.&#x20;
* Use namespaces to avoid naming conflicts in complex layout builds.&#x20;
* Make a tabs element a layout container, and tabs will be automatically created.  &#x20;

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

### Future

`wfu-layout-priority` = ( number )&#x20;

Allows you to specify distribution priority.&#x20;

Multiple layouts with the same ID get progressively distributed.&#x20;

`wfu-layout-maxitems` = ( number )&#x20;

Allows you to specify a limit on the number of items to be added to this group.  When used in conjunction with priority, this allows for progressive distribution across a series of groups.&#x20;

`wfu-layout-rule` = ( rule name )

* `exact` ( default ) means an exact match on the wfu-layout name. &#x20;

String matching;&#x20;

* `startswith` means that the group is matched if the item's key starts with the specified string&#x20;
* `regex` means that the group is matched if the item's key matches a regex string&#x20;

Numeric matching, can be used when the item key is numeric&#x20;

* greaterthan greater or equal (
  * e.g. 1000 &#x20;
* lessthan less or equal ( use eval if you need strict less )&#x20;
  * e.g. 1000&#x20;
* range between x and y, including the range endpoints ( use eval if you need a different approach )&#x20;
  * e.g. 1000-2000
* eval matches an evaluation string&#x20;
  * e.g. 1000 < x <= 2000&#x20;



wfu-layout-range-min

wfu-layout-range-max&#x20;





wfu-layout-container

Place on a wrapper

Implementation note: during layout an attribute can be added to indicate that content was added, wfu-layout-state = content&#x20;

After layout, a cleanup process occurs.  We look for wfu-layout-container elements and if there are only wfu-layouts within it that have a wfu-layout-state = empty  ( match cvis ) then&#x20;





Does it make sense to use the key here as the range value ?&#x20;



`wfu-layout-rule-mode`&#x20;

* `caseinsensitive` ( default ) -&#x20;
* `casesensitive` -&#x20;

Range



## Usage Notes - Configuring a Layout Item

### Target the item

`wfu-layout-target` = ( layout container name )

Identifies the container this element should be moved to.&#x20;

### I want to restrict layouts to a namespace ( advanced )&#x20;

`wfu-layout-ns` ( optional ) = ( layout container namespace )

**Optional.** Recommended when `wfu-layout` is bound to a CMS slug. &#x20;

For complex nested layouts, the wfu-layout is often bound to a CMS item slug. To prevent conflicts, you can also create a namespace in the form of a zone.&#x20;

{% hint style="info" %}
When a layout item has a zone specified, it will only be moved to zones which match both the container name and the zone attributes.&#x20;
{% endhint %}

{% hint style="success" %}
**NAMESPACES**

In Webflow, `wfu-layout` is often easily used with CMS data-bound attributes and item slugs.  Since this can create multiple targets with the same name on a page, you can use `wfu-layout-ns` with an arbitrary identifier to isolate these areas and prevent namespace conflicts or overlaps.&#x20;
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../sa5-html/quick-start.md).&#x20;

### STEP 2 - Apply the custom attributes as desired <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.



