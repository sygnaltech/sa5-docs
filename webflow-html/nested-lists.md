---
description: Add nested lists to Webflow's rich text elements
---

# Nested Lists ❺

* Easily indicate nesting depth by prefixing list items with `>`’s.
* Supports both ordered ( OL ) and unordered ( UL ) lists.&#x20;
* Compatible with editor mode.&#x20;
* Additionally prefix items with `+` or `-` for special PRO and CON lists
* Themes support - `default`, `modern`, `fun`

## Important Change Notes <a href="#demo---nested-lists" id="demo---nested-lists"></a>

{% hint style="warning" %}
With SA5, we've made some structural changes, to enforce semantically valid HTML5 even when list levels are skipped, e.g. level 1 to level 3. This creates strange layout complications due to the fact that there is an empty LI element to contain each nested list properly. We recommend you avoid skipping levels.&#x20;
{% endhint %}

## Demonstration <a href="#demo---nested-lists" id="demo---nested-lists"></a>

See here for a demonstration of nested lists and the markup we use;

{% embed url="https://webflow-smart-elements.webflow.io/rich-text" %}
Demonstration Page
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Usage Notes

### I want the lists in this rich text element to be nested. <a href="#step-2---apply-wfu-listsnested-to-desired-elements" id="step-2---apply-wfu-listsnested-to-desired-elements"></a>

Add this custom attribute to your RTE or list element;

```html
wfu-lists=nested
```

_Positioning is important_, make sure you’re placing this custom attribute on the correct element.

### I want this list item to be indented

Simply prefix the list items with > to indicate the depth. We recommend you do not skip levels.

### I want this list item to be a PRO or CON item

Prefix with a + for a PRO, or a - for a CON.&#x20;

### I want a different theme for my lists.

Apply the wfu-list-theme custom attribute to the list.

* `default` ( applied automatically when none is specified )
* `modern`
* `fun`

## Getting Started ( NOCODE )

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.7/dist/css/webflow-html.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.7/dist/nocode/webflow-html.js"></script>
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
