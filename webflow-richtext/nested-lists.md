---
description: Add nested lists to Webflow's rich text elements
---

# Nested Lists ❺

* Easily indicate nesting depth by prefixing list items with `>`’s.
* Supports both ordered ( OL ) and unordered ( UL ) lists.&#x20;
* Compatible with editor mode.&#x20;
* Additionally prefix items with `+` or `-` for special PRO and CON lists
* Themes support - `default`, `modern`, `fun`

## Nested List Markup Syntax

To indent list items, simply prefix the list items with `>` to indicate the depth. We recommend you do not skip levels.

{% tabs %}
{% tab title="Markup example" %}
In the editor, this will look like;

* Top level
* \> Indented one level
* \>> Indented two levels
* \>> Also indented two levels
* \> Indented one level
{% endtab %}

{% tab title="Published example" %}
In the published site, this will render as;

* Top level
  * Indented one level
    * Indented two levels
    * Also indented two levels
  * Indented one level
{% endtab %}
{% endtabs %}

### PROs & CONs

To specially identify an item as a PRO or a CON, prefix it with a + or a - just after any indentation markers. The appearance, coloring and icon used will depend on the theme.&#x20;

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

## Usage Notes&#x20;

<details>

<summary>I want the lists in this rich text element to be nested</summary>

Add this custom attribute to your rich text element;

```html
wfu-lists=nested
```

</details>

<details>

<summary>I want a different theme for my lists</summary>

Apply the `wfu-list-theme` custom attribute to the **rich text element**.

* `default` ( applied automatically when none is specified )
* `modern`
* `fun`

</details>

## Getting Started

{% hint style="success" %}
**100% NOCODE**\
All aspects of this feature are attributes-based for your convenience.&#x20;
{% endhint %}

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply the custom attributes you want <a href="#step-2---apply-wfu-listsnested-to-desired-elements" id="step-2---apply-wfu-listsnested-to-desired-elements"></a>

See above.&#x20;







\
