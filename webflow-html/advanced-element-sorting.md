---
description: Sort Webflow's collection list items any way you like
---

# Advanced Element Sorting

## Overview

Webflow's collection lists have a few limitations on the native sort functionality;&#x20;

* The inability to sort on **Ref** fields
* The inability to sort on **Option** fields
* The inability to sort nested collection list items
* Random sorting works well, but only changes the order every 12 hours&#x20;

This attribute allows to do all of these;

* Sort by ref & option field types
* Sort by text, date, numbers, or even semvers
* Sort ascending, descending or randomly ( on every page refresh )

## Demonstrations

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

### `wfu-sort` attribute <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

Place on any Collection List directly ( not the Collection List Wrapper ). No value is needed.

### `wfu-sort-dir` attribute <a href="#wfu-sort-dir-attribute" id="wfu-sort-dir-attribute"></a>

Sort direction defaults to ascending. If you want to specify the direction, add this attribute with a value of;

* `asc` for ascending
* `desc` for descending
* `random` for random ( on every page refresh )

### `wfu-sort-type` attribute <a href="#wfu-sort-type-attribute" id="wfu-sort-type-attribute"></a>

The field type always defaults to sorting as a string. If you want to specify the data type of the field being sorted, add this attribute with a value of;

* `string` to sort as strings
* `number` to parse sort as numbers
* `date` to parse and sort as dates
* `semver` to parse and sort as [semantic versions](https://semver.org/) \*\*

Defaults to `string` when unspecified or unrecognized.

\*\* Note that semver sorting is a numeric-only implementation of the sort rules. It is not designed to handle alphanumerics in pre-release identifiers.

### Creating your Sort Key <a href="#creating-your-sort-key" id="creating-your-sort-key"></a>

The sort field is controlled by specifying a Sort Key. This gives you complete control over the field that is being used for sorting.&#x20;

Create an HTML Embed inside of your Collection List Item, with this code;

```html
<data wfu-sort-key=""></data>
```

As the attribute value for `wfu-sort-key`, insert the field that you want to sort by, using Webflow’s ‘**+ Add Field** at the top-right of the HTML Embed Code Editor window.&#x20;

{% hint style="info" %}
Remember, Sygnal Attributes will always treat your value as a **string** for sort purposes, unless you  specify otherwise. If you want sorting to occur as a number, date, or semver, make sure to specify that attribute.
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

### STEP 2 - Apply `wfu-sort` and configuration attributes to the elements you want to filter <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

### STEP 3 - \[ OPTIONAL ] Change the default sort type ( _string_ ) and order ( _ascending_ ), using the `wfu-sort-dir` and `wfu-sort-type` attributes.

See above for details.

### STEP 4 - Define your sort key

See above for details.

