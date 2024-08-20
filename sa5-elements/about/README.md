---
description: About the SA5 Elements Library
---

# 🔍 About SA5's Elements Lib

{% hint style="success" %}
**SA5 Elements** is a new library ( Aug 2023 ) that centralizes all of our Smart Webflow Elements, and other custom elements we've created. &#x20;
{% endhint %}

Currently this lib focuses on;

1. Providing JS API's for Webflow's existing elements, where it's useful. Change tabs, navigate the slider, disable buttons, etc.&#x20;
2. Capturing key events that you can respond to in custom code, like a slide or tab change- whether it was done by a user, or automatically ( auto-slides ), or by script.&#x20;
3. Adding functionality where it's missing, such as Lightbox captions from the CMS.&#x20;
4. Adding new elements, such as the Accordion, where it's useful&#x20;

## Deck Elements

We’re evolving a standardized “deck” interface for elements which share a deck-style UI. We define that as card-style UX where generally only one card is visible or “primary” at a time;

* Tabs elements
* Slider elements
* Accordion elements ( custom )
* Tinder-style decks ( custom )&#x20;

All of these share the same base API for next, prev, first, etc.\
This way the element can be changed out without needing to rewrite your code.

{% hint style="info" %}
See the [Deck Controller](../deck-controller-element.md) for easy nocode navigation of Tabs and Slider elements.
{% endhint %}

## Future

We're considering the possibility of variant UX's that are based on existing elements. For example;

* Steppers ( or Progress Steps ) designed specifically for wizard style multi-step forms. Would likely be based on Tabs, or our Accordion.&#x20;
* Card stacks, which are swiped. Based on carousel, but with a different visual UX more like a tinder deck, with events for yes, no, favorite, and a down swipe, and possibly UX for card info or a tap to flip effect.&#x20;

