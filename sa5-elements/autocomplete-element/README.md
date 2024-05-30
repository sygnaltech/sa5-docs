---
description: A CMS-capable dropdown UI that makes it easier to pick from longer lists.
---

# Autocomplete Element ❺

Autocomplete, or predictive input, is a popular UX pattern that helps users navigate lists of options. In general it consists of two parts;

* A text input, for the user to type partially-matching text in
* A list, which appears and filters to display only items that partially-match the specified text.
  * Matching is typically anywhere in the string, and case-insensitive.

## Use Cases

The most common use cases for an autocomplete UX include;

### Navigation

* Quick find the item you want in a product/service list, and navigate to that page.

### Form input

* Quick-select an a form input which encourages ( but not requires ) specific values
  * e.g. Common message topics for the support department
* Quick-select an a form input which requires specific values&#x20;
  * e.g. Choose from a list of countries

## Usage Notes

{% hint style="info" %}
**VIDEO TUTORIAL** \
Here's a full walkthrough of a basic build, from a blank page, to help you understand your design options and how the attributes are applied.
{% endhint %}

{% embed url="https://www.loom.com/share/423e136f9d1a457394dfe5a7397eaf76" %}

### Dropdown Element

I want this dropdown element to be an SA5 autocomplete element.&#x20;

Place this custom attribute on the Dropdown element itself.

`wfu-autocomplete` = ( no value needed )

### Input Element

You'll place a form an input element within the dropdown's toggle element so that it is always visible.&#x20;

Identify it with the following element-&#x20;

`wfu-autocomplete-input` = ( no value needed )&#x20;

Within the list, you'll place the elements you want to appear. This can include a collection list, or several.&#x20;

### List Item Elements

Place this directly on the list items you want to be filtered.&#x20;

{% hint style="info" %}
In the case of a collection list, place it on the Collection List Item element directly ( the innermost of the 3 element collection list structure ).&#x20;
{% endhint %}

{% hint style="warning" %}
FUTURE. attributes applied to the parent of the list items ( the dropdown list itself ) can be used as a fallback default.&#x20;
{% endhint %}

`wfu-autocomplete-item` identifies the items that you want filtered as the user types text.

{% hint style="info" %}
Do not use this attribute on list items that should not be filtered, for example a Site Search item. &#x20;
{% endhint %}

`wfu-autocomplete-item-layout` defined the layout the item should use when made visible.&#x20;

* `block` ( default )
* `flex`
* `grid`
* etc.&#x20;

### Controlling the Matching Process

Matching can be controlled;

`wfu-autocomplete-item-match-type`= ( match string, typically from CMS )&#x20;

is performed as;&#x20;

* `default`. ( default ) specific match text ( default )&#x20;

Future

* inner text ( any )&#x20;
* FUTURE - specific inner text, sub-tagged&#x20;
* FUTURE - Exact match. MUST match exactly ( no partial entry ), and updates the main input. Prevent validation or even clear the field if no exact match is made. Used for some strict form entry use cases&#x20;

Here you'll identify the matching string

`wfu-autocomplete-item-match`= ( match string, typically bound to a CMS field )&#x20;

`wfu-autocomplete-matching-rule`

* Default - anywhere in the string, all lowercase
* Start of string only, case-insensitive
* Regex, specific string?&#x20;
* Custom - use a callback function?&#x20;

\`wfu-autocomplete-matching-rule-config

* Regex
* Callback function?



### Controlling the Item's Click Action

When a match item is clicked, you can control its action by adding this attribute to the item.

`wfu-autocomplete-item-action` = ( action type )

Action type is one of;

* `navigate` ( default ). Does nothing and allows the item's own link to navigate
* `search`. Initiates a site search using Webflow's native search feature

Future;&#x20;

* `custom`.&#x20;

`wfu-autocomplete-item-action-config` = ( varies )

On `custom`, this specifies the callback function to run.&#x20;

{% hint style="info" %}
FUTURE. Default item-level settings can be inherited from the dropdown's element directly.
{% endhint %}

## Tips & Best Practices&#x20;

### Have more than 100 CMS items to match?

If the number is reasonable, say < 200 or < 300, you can place several consecutive collection lists, setup identically.  Do not enable pagination, instead use the from and to ranges, e.g. 1 to 100, 101 to 200, 201 to 300.&#x20;

### Site Search Item ( optional )

Within the list, you can add an item which will take the user's entered text and initiate a full site search. Take advantage of this for a more comprehensive UX experience.

* Add a static item to your dropdown list, at the start or at the end
* Style it differently so that it stands out
* Use attr `wfu-autocomplete-item-action` = `search`
* Do not use `wfu-autocomplete-item`

{% hint style="info" %}
To use this, you must have Webflow's site-search configured.
{% endhint %}

## Styling

### The Dropdown Element&#x20;

* If this is in your header and can overlap a nav, you want a higher z-index.  Set this directly on the Dropdown Element, e.g. `z-index: 9999`.&#x20;

### The Dropdown Toggle

* Style how you like
* Change to display block rather than inline-block
* Pull the label out, for optimal alignment with the dropdown carat&#x20;
* Optionally, move the dropdown's toggle icon inside of the form, just after the text input field&#x20;

### The Dropdown List

* Give it a max height of e.g. `60vh`.&#x20;
* Set it to `overflow-y: auto`, using custom properties at the bottom of the style panel.&#x20;
* Top and bottom padding e.g. `10px`.&#x20;
* Can contain;
  * Static items, like Dropdown Links or Link Blocks&#x20;
  * Collection lists
  * Multiple collection lists

### The Dropdown List Items&#x20;

* Add a hover effect for styling&#x20;
* Can be any arrangement of elements you want within a link block or DIV
* Can be variable heights, including wrapped text&#x20;
* Can include icons
* [https://icons.relume.io/](https://icons.relume.io/)

## Technical Notes

Notes;

* Designed to be self-contained, everything in an SA5 autocomplete element exists as content and child elements within the dropdown element itself.&#x20;
  * This makes it easy to reference elements, and allows you to easily have several autocomplete elements on the same page.
* Designed to leverage Webflow's native dropdown element, so that it will close when you click outside of it.&#x20;
* Designed to utilize CMS data when appropriate, via collection lists.&#x20;
* Designed to integrate with site search if you also have that available.&#x20;
* Designed to support complex list item styling and layouts &#x20;

Future;

* Possible sorting&#x20;
* Possible ranking, e.g.&#x20;
  * start-of string matches get a stronger signal than middle-of-string
  * case-match v. non-case-match?&#x20;
* Direct integration with search results&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.&#x20;







