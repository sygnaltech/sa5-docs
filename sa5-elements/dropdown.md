---
description: Interact with Webflow's Dropdown Element
---

# Dropdown Element ❺

## Goals  <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

* Make the dropdown element programmatically accessible to scripts, for open, close, toggle, query, item manipulation, and more
* Add certain attribute-based common functionality as behavior modifications
  * Auto open on page load&#x20;

Future;

* Possibly replace the dropdown to allow for custom behaviors, like "sticky" behavior
  * Where the dropdown can only be opened/closed on script&#x20;
  * Or specific behaviors like clicking the toggle&#x20;
* Item manipulation
  * Script-add / edit / delete items
  * Re-sort options
  * Keep WF dropdown working as normal&#x20;

Data acquisition;&#x20;

* Designated data source
* Filter state
* Sort state

Possible;

* Support selected item?
* Support multiple selected items?&#x20;
* Support text entry, combobox&#x20;
* Support quick selection filtering of available items e.g. countries&#x20;

## Features <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Current features are simple;

### Attributes

* Auto open on page load

[https://discourse.webflow.com/t/how-to-get-dropdown-open-on-page-load-automatically/158399/16](https://discourse.webflow.com/t/how-to-get-dropdown-open-on-page-load-automatically/158399/16)

wfu-dropdown-init = open | closed



### API

For developers, there is now an ability to manipulate a Webflow native dropdown through custom code, including;

* open
* close
* toggle
* query state

{% hint style="info" %}
It's important to note that the Webflow dropdown behavior is to auto-close when anything outside of the dropdown is clicked. This means for example that if you create a button, and have the button toggle the dropdown, that;

* The act of clicking the button will close the dropdown
* The SA5 code triggered by the button will then detect it's closed and toggle it to open

Make sure to consider the effect of UX click interactions in your code design.&#x20;
{% endhint %}

## Demonstration <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

{% embed url="https://webflow-smart-elements.webflow.io/dropdown" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

### wfu-dropdown <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

REQUIRED. Identifies this dropdown element as one that should be managed by SA5.

> Place this attribute on the dropdown element directly ( not the toggle element ).&#x20;

### wfu-dropdown-init = (action)

OPTIONAL. On page load, initialize the dropdown state to-

* `open`
* `closed` ( default )

> Place this attribute on the dropdown element directly ( not the toggle element )

### API

BETA. See the cloneable.&#x20;

## Notes

[https://discourse.webflow.com/t/how-to-get-dropdown-open-on-page-load-automatically/158399/16](https://discourse.webflow.com/t/how-to-get-dropdown-open-on-page-load-automatically/158399/16)

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.













