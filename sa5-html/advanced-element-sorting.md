---
description: Sort Webflow's collection list items any way you like
---

# Advanced Element Sorting ❺

Webflow's collection lists offer a native sort functionality, however it has a number of limitations;&#x20;

* Alphabetic sorting is unicode-based and sorts uppercase and lowercase letters as separate ranges&#x20;
  * Apple, Banana, aardvark...&#x20;
* No ability to sort on **Ref** fields or **Option** fields
* No ability to sort nested collection list items
* No locale-aware sorting ability for Localized sites&#x20;
* No ability to sort content in fields within an item in a de-normalized field structure
  * e.g. fields like "Faq 1", "Faq 1 description", "Faq 2", "Faq 2 description" &#x20;
* Random sorting only changes the order every 12 hours&#x20;

## Goals&#x20;

**SA5 Sort** allows you to naturally and flexibly sort any grouping of elements in your page, to support all of these scenarios.&#x20;

1. Sort any elements, in any part of your page&#x20;
2. Sort intelligently by data type - text, date, numbers, or even semver version numbers&#x20;
3. Sort ascending, descending or randomly, on every page refresh &#x20;
4. Sort automatically by page locale ( for localized sites ) or browser locale&#x20;

## Demonstrations &#x20;

|                                                                                 | Demo                                                                                                                     | Cloneable                                                                                                                              |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| Collection List Sorting                                                         | [https://webflow-smart-elements.webflow.io/collection-lists](https://webflow-smart-elements.webflow.io/collection-lists) | [https://webflow.com/made-in-webflow/website/webflow-tabs-hacks](https://webflow.com/made-in-webflow/website/webflow-tabs-hacks)       |
| [Sort by Option or Ref](https://www.sygnal.com/lessons/sorting-by-option-field) | [https://sort-by-option-or-ref.webflow.io/](https://sort-by-option-or-ref.webflow.io/)                                   | [https://webflow.com/made-in-webflow/website/sort-by-option-or-ref](https://webflow.com/made-in-webflow/website/sort-by-option-or-ref) |
| Locale-specific sorting                                                         | [https://sa5-html.webflow.io/demo/sa5-advanced-sorting](https://sa5-html.webflow.io/demo/sa5-advanced-sorting)           | [https://webflow.com/made-in-webflow/website/sa5-html](https://webflow.com/made-in-webflow/website/sa5-html)                           |

## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

1. First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;
2. Apply `wfu-sort` and configuration attributes to the elements you want to filter
3. **Optional.**  Change the default sort type ( _string_ ) and order ( _ascending_ ), using the `wfu-sort-dir` and `wfu-sort-type` attributes.
4. **Optional.**  Use the `wfu-sort-key` to define your item sort key

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Sorting is configured on two sets of elements- the **parent** element, which contains the list of things you are sorting, and the **item** elements, which are the elements being sorted.&#x20;

In the case of a Collection List, the parent is the Collection List element ( not the Collection List Wrapper ), and the item is the Collection List Item element. These are the bottom two purple elements you see in a collection list element hierarchy.

If you are not sorting a collection list, any parent-item set can be configured for sorting. &#x20;

### `wfu-sort` = ( no value )  <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

**Required.** No value is needed.&#x20;

{% hint style="info" %}
Place this attribute on the **parent** element, whose children will be sorted.&#x20;

For a _collection list_, this should be on the Collection List ( middle ) element directly, not the Collection List Wrapper.&#x20;
{% endhint %}

### `wfu-sort-dir` = ( direction ) <a href="#wfu-sort-dir-attribute" id="wfu-sort-dir-attribute"></a>

**Optional.**  Sort direction defaults to ascending. If you want to specify the direction, add this attribute with a value of;

* `asc` for ascending ( default )&#x20;
* `desc` for descending
* `random` for random ( on every page refresh )

{% hint style="info" %}
Place this attribute on the element with `wfu-sort`.&#x20;
{% endhint %}

### `wfu-sort-type` = ( type ) <a href="#wfu-sort-type-attribute" id="wfu-sort-type-attribute"></a>

**Optional.**  Sort type always defaults to string-based sorting ( an alphanumeric sort ). If you want to specify the data type of the field being sorted, add this attribute with a value of;

* `string` to sort as strings ( default )&#x20;
* `number` to parse sort as numbers
* `date` to parse and sort as dates
* `semver` to parse and sort as [semantic versions](https://semver.org/) ( e.g. 2.0.108.4 )&#x20;

{% hint style="info" %}
Place this attribute on the element with `wfu-sort`.&#x20;
{% endhint %}

### `wfu-sort-locale` = ( _setting_ )  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

**Optional.**  Allows you to apply locale-specific sorting to a list.

{% hint style="warning" %}
**EXPERIMENTAL** \
Currently implemented on ascending string sorting only.&#x20;
{% endhint %}

_Setting_ is one of;&#x20;

* `none` ( default ) - No locale-specific sorting applied
* `auto` - Locale is determined from the HTML lang attribute, which is automatically set in Webflow Localized sites&#x20;
* ( language / locale code ) - You can specify a specific language code like `en` or locale code like `en-US`&#x20;

{% hint style="info" %}
Place this attribute on the element with `wfu-sort`.&#x20;
{% endhint %}

### `wfu-sort-key` = ( sort key value ) <a href="#creating-your-sort-key" id="creating-your-sort-key"></a>

**Required.** The value to sort by is known as the **sort key**, and is specified as the value of the `wfu-sort-key` attribute. This gives you complete control over the field that is being used for sorting.&#x20;

{% hint style="info" %}
Place this attribute on the **item** element.&#x20;

In a collection list, this would the Collection List Item, which is the 3rd, innermost part of Webflow's collection list element.&#x20;
{% endhint %}

{% hint style="success" %}
The most common way to set the value of this field is to pull the content directly from your associated CMS item. To do that, use Webflow's custom attribute CMS binding feature to insert whatever field you want to use as the sort key for that item.&#x20;
{% endhint %}

{% hint style="danger" %}
At this time, Webflow's ECommerce collections do not support binding fields to custom attributes.&#x20;
{% endhint %}

## Future <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Future features we're considering...

* Secondary and tertiary sorting, where additional sorting rules are applied when two items are considered sort-equivalent.
* Script-defined sorting, where the rules override what the attributes define.&#x20;
* Custom sorting rules, handled by a callback. &#x20;
* Script-triggered re-sorting, triggerable by script.&#x20;
  * Used for e.g. a dropdown of multiple sort configs. &#x20;
* Memory of past sort settings&#x20;
* Option to re-init IX2&#x20;
* Support for ECommerce, which does not support attribute bindings&#x20;



