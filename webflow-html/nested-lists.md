---
description: Add nested lists to Webflow's rich text elements
---

# Nested Lists ❺

* Easily indicate nesting depth by prefixing list items with `>`’s.
* Supports both ordered ( OL ) and unordered ( UL ) lists.&#x20;
* Compatible with editor mode.&#x20;

{% hint style="info" %}
With SA5, we've made some structural changes in "empty next" situations, to enforce semantically valid HTML5. The design of these features is being revisited;
{% endhint %}

* Jump up and down nested depths as much as you want. You can go from level 1 to level 4 to level 2, and the code will generate the missing levels properly.
* Also supports `+` and `-` prefixing for special PRO and CON lists.&#x20;

{% hint style="warning" %}
On special item styling such as the **PRO** and **CON** special styling, note that if you have styled list items specially you may experience styling conflicts.
{% endhint %}

## Demonstration <a href="#demo---nested-lists" id="demo---nested-lists"></a>

See here for a demonstration of nested lists and the markup we use;

{% embed url="https://webflow-smart-elements.webflow.io/rich-text" %}

## Usage Notes

### I want the lists in this rich text element to be nested. <a href="#step-2---apply-wfu-listsnested-to-desired-elements" id="step-2---apply-wfu-listsnested-to-desired-elements"></a>

Add this custom attribute to your RTE or list element;

```html
wfu-lists=nested
```

_Positioning is important_, make sure you’re placing this custom attribute on the correct element.

## Future

Themes

Pros & cons

## Getting Started ( NOCODE )

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.6/dist/css/webflow-html.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.6/dist/nocode/webflow-html.js"></script>
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

### STEP 2 - Apply `wfu-lists=nested` to Desired Elements <a href="#step-2---apply-wfu-listsnested-to-desired-elements" id="step-2---apply-wfu-listsnested-to-desired-elements"></a>

Add this custom attribute to your RTE or list element;

```html
wfu-lists=nested
```

_Positioning is important_, make sure you’re placing this custom attribute on the correct element.

* To nest a _standalone_ list element, place it directly on the top level element in the list structure.
* To nest lists within a Rich Text element, place it directly on the Rich Text element itself.

In both cases, these elements are most easily selected using the left-side element nav panel in the designer.



\
