---
description: Control and navigate deck elements like Tabs and Sliders
---

# Deck Controller Element ❺

The Deck Controller provides simple no-code navigation capabilities using attributes that work across all deck-style elements, including SA5's [Tabs](tabs/) and [Sliders](slider/).&#x20;

## Attributes

{% hint style="info" %}
These attributes should be placed on a button, link, or other element which you want to click-trigger a specific deck navigation action.&#x20;
{% endhint %}

### `wfu-deck-action` = ( method ) <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

**Required.** I want my button or link to perform the following action on the targeted deck element.

Method is one of;

* `first` - select the first tab / slide
* `prev` - select the previous tab / slide
* `next` - select the next tab / slide
* `last` - select the last tab / slide
* `goto` - select the specified tab / slide

### `wfu-deck-target` = ( deck name )

**Optional.** Specifies the `wfu-tabs` or `wfu-slider` name you want your action to target.

If unspecified, it will look for the nearest parent tabs or slider element as the target.&#x20;

### `wfu-deck-action-item` = ( item number or name )  <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

**Required for the `goto` action only.** Specifies the tab / slide you want to navigate to.&#x20;

* a number - indicates the item number, 1, 2, 3...&#x20;
* a string - activates the tab / slide with the specified name&#x20;

## Changelog <a href="#getting-started-nocode" id="getting-started-nocode"></a>

**2024-Feb-04** - First release.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.&#x20;

{% hint style="info" %}
Deck Controller elements work together with SA5's Tabs or Sliders, so make sure to configure your Tabs or Sliders as well.&#x20;
{% endhint %}
