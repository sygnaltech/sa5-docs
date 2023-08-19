---
description: Assign a numeric sequence to arbitrary elements in a group.
---

# Numeric Sequencing ❺

Allows you to apply a numeric sequence across a series of elements.

Numbering is always in a traditional 1, 2, 3… style of sequencing.&#x20;

{% hint style="info" %}
NOTE: This is primarily useful for sorting and filtering demos, because CSS has a numeric sequencing feature built in for live display.
{% endhint %}

## Demonstration

{% embed url="https://webflow-smart-elements.webflow.io/sequence" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### `wfu-seq-group` attribute <a href="#wfu-seq-group-attribute" id="wfu-seq-group-attribute"></a>

Place on any element. Give an arbitrary named group, for matching the items after, e.g. `articles`

### `wfu-seq` attribute <a href="#wfu-seq-attribute" id="wfu-seq-attribute"></a>

Place on any child element within that group. Give it the same group name as its parent.

### Notes <a href="#notes" id="notes"></a>

The HTML DOM is a large tree of element and sub-elements.

* You can use `wfu-seq-group` multiple times throughout your document.
* You can use the same group name on multiple `wfu-seq-group`’s, provided that those subtrees are independent. Do not use the same name if one group is nested within the other.
* You can have nested `wfu-seq-group`’s, as long as you use a different group name.

The purpose of these capabilities is to allow you to use numbering on a Webflow collection list that contains a nested list. You can give one numbering sequence to the parent list, and a numbering sequence to each of the child lists as well.

NOTE: Primarily I’d recommend this for demos, where you need to number items and then permute them. In most numbering situations, CSS numbering is generally a better alternative for general sequencing.

## Future <a href="#future" id="future"></a>

Depending on client needs and user requests, we may expand this to allow for control of;

* Starting number
* Step size
* Increasing or decreasing count
* Support for decimal values

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply configuration attributes to the elements you want to filter <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

\
