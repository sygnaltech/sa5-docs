---
description: Handle dynamic layouts in your Webflow-hosted site
---

# Layout ❺🧪

Features-

* Tag any DIV as a container element
* Tag any other elements to be moved into that DIV&#x20;

Future-&#x20;

* Zones&#x20;
* Copy v. Move &#x20;
* Control the sequence of operations?&#x20;
* Part control
* Position control
  * Sorting control?&#x20;
* Handlers
  * Tabs, slider&#x20;

Use cases-&#x20;

* Combine collection lists&#x20;
* Handle complex layout requirements that would typically require a large number of collection lists
  * e.g. a calendar view&#x20;
* Overcome nested-item limits in collection lists
* Push static elements into a collection list&#x20;

## Usage Notes

### I want this DIV / element to be the target container for layout operations&#x20;

`wfu-layout` = NAME

NAME can be any unique arbitrary string to identify that container. It can also be bound to a collection list slug for more dynamic, powerful layouts.

Future;&#x20;

`wfu-layout-priority` = NUMBER ( optional )

Control the sequence of layout operations.&#x20;

`wfu-layout-zone` = IDENTIFIER ( optional )&#x20;

If you have multiple such layouts, you'll be able to also identify a zone as a namespace to prevent slugs from conflicting.&#x20;

{% hint style="warning" %}
**FUTURE**

In Webflow, `wfu-layout` is often easily used with CMS data-bound attributes and item slugs.  Since this could create multiple targets with the same name on a page, you can use `wfu-layout-zone` with an arbitrary identifier to isolate these areas and prevent namespace conflicts or overlaps.&#x20;
{% endhint %}

### I want this element to be moved / copied into a layout container&#x20;

`wfu-layout-item-to` = CONTAINER-NAME&#x20;

Identifies an element to move into a new layout position&#x20;

## Future

Future under consideration;&#x20;

`wfu-layout-item-method` =&#x20;

* `move` (default) - move the item
* `copy` - copy the item

`wfu-layout-item-part` =&#x20;

* `element` (default) - move the element and its children
* `children` - move only the children of the element

`wfu-layout-item-position` =&#x20;

* `bottom` | `end` (default) - layout at the bottom of the container
* `top` | `start` - layout at the top of the container &#x20;

`wfu-layout-handler` (optional)

* (none) (default)
* tabs - must be placed on a tabs container&#x20;

`wfu-layout-init` (optional)

* (none) (default) - do nothing
* clear - clear the children&#x20;

wfu-layout-item-name (special) = TEXT-STRING&#x20;

* Used for e.g. tab name

