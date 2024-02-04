---
description: Control and navigate deck elements like Tabs and Sliders
---

# Deck Controller Element ❺🧪

The goal here is to provide simple no-code navigation capabilities using attributes that work across all deck-style elements, including Tabs and Sliders.&#x20;

## Attributes

{% hint style="info" %}
These attributes should be placed on a button, link, or other element which you want to click-trigger a specific deck navigation action.&#x20;
{% endhint %}

### `wfu-deck-action` = ( method ) <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

I want my button or link to perform the following action on the targeted deck element.

Method is one of;

* `first` - select the first tab / slide
* `prev` - select the previous tab / slide
* `next` - select the next tab / slide
* `last` - select the last tab / slide
* `goto` - select the specified tab / slide

### `wfu-deck-target` = ( deck name )

_Optional._ Specifies the `wfu-tabs` or `wfu-slider` name you want your action to target.

If unspecified, it will look for the nearest parent tabs or slider element as the target.&#x20;

### `wfu-deck-action-item` = ( item number or name )  <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

For the `goto` action only, specifies the tab / slide you want to navigate to.&#x20;

* a number - indicates the item number, 1, 2, 3...&#x20;
* a string - activates the tab / slide with the specified name
