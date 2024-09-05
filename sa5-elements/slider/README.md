---
description: Interact with Webflow's Slider Element
---

# Slider Element ❺

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to work with the Webflow slider element.

* Switch slides programmatically- first, next, prev, and last, or go to a specific slide number
* Get the current slide number
* Get notified when the slide changes
* Get notified when the user tries to change the slide, and choose whether to allow it
  * _Useful for slider-based multi-step forms_&#x20;

## Demonstration

Check the slider demonstrations here-&#x20;

{% embed url="https://webflow-smart-elements.webflow.io/slider" %}
Demo
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Use Cases <a href="#usage-notes" id="usage-notes"></a>

Enhance navigation;&#x20;

* Link a button or other element to your tab element, to trigger navigation to the first, last, next, or previous tab. These elements can be anywhere on your page, including within the tab element, such as a Next button. You can have as many of them as you like.&#x20;
* Programmatically navigate the tabs element using JavaScript.&#x20;
* Receive callback alerts when tabs change, including auto-changes, and perform other custom script actions.&#x20;
* Multi-step forms, control when the user can advance to the next step&#x20;

## Features <a href="#prepare-your-collection-list" id="prepare-your-collection-list"></a>

SA5 Slider is primarily API-based, see the left nav for the API docs.&#x20;

|                                       | Attributes | Javascript API                                                 |
| ------------------------------------- | ---------- | -------------------------------------------------------------- |
| Identify the slider                   | wfu-slider | <p>name</p><p>Can be instantiated on any slider directly. </p> |
| Go to slide at index ( 0-based )      |            | currentIndex                                                   |
| Go to slide number ( 1-based )        |            | currentNum                                                     |
| Go to first slide                     |            | goToFirst                                                      |
| Go to last slide                      |            | goToLast                                                       |
| Go to prev slide                      |            | goToPrev                                                       |
| Go to next slide                      |            | goToNext                                                       |
| **EVENTS**                            |            |                                                                |
| Slide changed                         |            | slideChanged event.                                            |
| User wishes to advance to next slide  |            | slideNextRequest event                                         |
| User wished to navigate to prev slide |            | slidePrevRequest event                                         |



## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

1. First, **add the library** as detailed in [Quick Start](../quick-start.md).
2. Apply the custom attributes to the elements you want to affect
3. Use the API & Callbacks to control the element from your custom code

See above for details.

* Setup your Webflow slider element however you like
* Setup other "control" elements that will affect it, such as buttons, etc ( optional ).&#x20;

{% hint style="info" %}
To control the Webflow native slider, SA5 uses the slider's navigation elements such as the bottom slide page dots. It's important that they are physically part of the slider, even if you make them invisible with display: none.  Do not mark navigation elements as visibility: hidden or SA5 will be unable to interact with your slider.&#x20;
{% endhint %}

### `wfu-slider` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-slider` custom attribute to the a Slider element. Give it a unique **name** to identify that element uniquely, e.g. `slider1`.&#x20;

This makes the slider element accessible in code.&#x20;







