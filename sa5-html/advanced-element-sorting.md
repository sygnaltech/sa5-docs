---
description: Sort Webflow's collection list items any way you like
---

# Advanced Element Sorting ❺

## Overview

Webflow's collection lists offer a native sort functionality, however it has a number of limitations;&#x20;

* The inability to sort on **Ref** fields
* The inability to sort on **Option** fields
* The inability to sort nested collection list items
* The inability to sort content in fields within an item
* Random sorting works well, but only changes the order every 12 hours&#x20;

This attribute allows to do all of these;

* Sort by ref & option field types
* Sort by text, date, numbers, or even semvers
* Sort ascending, descending or randomly ( on every page refresh )

## Demonstrations

{% embed url="https://webflow-smart-elements.webflow.io/collection-lists" %}
Demonstration site
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

### Additional demos

{% embed url="https://sort-by-option-or-ref.webflow.io/" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/sort-by-option-or-ref" %}
Cloneable
{% endembed %}

{% embed url="https://www.sygnal.com/lessons/sorting-by-option-field" %}
Tutorial
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Sorting is configured on two sets of elements- the **parent** element, which contains the list of things you are sorting, and the **item** elements, which are the elements being sorted.&#x20;

In the case of a Collection List, the parent is the Collection List element ( not the Collection List Wrapper ), and the item is the Collection List Item element. These are the bottom two purple elements you see in a collection list element hierarchy.

If you are not sorting a collection list, any parent-item set can be configured for sorting. &#x20;

### `wfu-sort` attribute <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

Place this attribute on the **parent** element, to indicate it will be sorted. No value is needed.&#x20;

### `wfu-sort-dir` attribute <a href="#wfu-sort-dir-attribute" id="wfu-sort-dir-attribute"></a>

Sort direction defaults to ascending. If you want to specify the direction, add this attribute with a value of;

* `asc` for ascending
* `desc` for descending
* `random` for random ( on every page refresh )

Place this attribute on the **parent** element.

### `wfu-sort-type` attribute <a href="#wfu-sort-type-attribute" id="wfu-sort-type-attribute"></a>

Sort type always defaults to string-based sorting ( an alphanumeric sort ). If you want to specify the data type of the field being sorted, add this attribute with a value of;

* `string` to sort as strings
* `number` to parse sort as numbers
* `date` to parse and sort as dates
* `semver` to parse and sort as [semantic versions](https://semver.org/) \*\*

Defaults to `string` when unspecified or unrecognized.

Place this attribute on the **parent** element.

{% hint style="info" %}
Note that this library does not currently have any localization configurations, so sorting in non-English locales may not work as expected.&#x20;
{% endhint %}

{% hint style="info" %}
`semver` sorting is a simplified numeric-only implementation of the sort rules. It is not designed to handle alphanumerics, such as pre-release identifiers.
{% endhint %}

### `wfu-sort-key` attribute <a href="#creating-your-sort-key" id="creating-your-sort-key"></a>

The value to sort by is known as the **sort key**, and is specified as the value of the `wfu-sort-key` attribute. This gives you complete control over the field that is being used for sorting, and you can use dynamic or static content.&#x20;

Place this attribute on the **item** element.

{% hint style="success" %}
The most common way to set the value of this field is to pull the content directly from your associated CMS item. To do that, use Webflow's custom attribute CMS binding feature to insert whatever field you want to use as the sort key for that item.&#x20;
{% endhint %}

## Future <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Future features we're considering...

* Secondary and tertiary sorting, where additional sorting rules are applied when two items are considered sort-equivalent.
* Script-defined sorting, where the rules override what the attributes define.&#x20;
* Custom sorting rules, handled by a callback. &#x20;
* Script-triggered re-sorting, triggerable by script.&#x20;
  * Used for e.g. a dropdown of multiple sort configs. &#x20;
* Memory of past sort settings&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply `wfu-sort` and configuration attributes to the elements you want to filter <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

### STEP 3 - \[ OPTIONAL ] Change the default sort type ( _string_ ) and order ( _ascending_ ), using the `wfu-sort-dir` and `wfu-sort-type` attributes.

See above for details.

### STEP 4 - Use the `wfu-sort-key` to define your item sort key

See above for details.

