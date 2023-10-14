---
description: Interact with Webflow's Slider Element
---

# Slider Element ❺

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to work with the Webflow slider element.

* Switch slides programmatically- first, next, prev, and last, or go to a specific slide number
* Get the current slide number
* Get notified when the slide changes

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

## Setup <a href="#prepare-your-collection-list" id="prepare-your-collection-list"></a>

* Setup your Webflow slider element however you like
* Setup other "control" elements that will affect it, such as buttons, etc ( optional ).&#x20;

### `wfu-slider` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-slider` custom attribute to the a Slider element. Give it a unique **name** to identify that element uniquely, e.g. `slider1`.&#x20;

This makes the slider element accessible in code.

## JavaScript API

### Receiving Slide Changed Events

To receive events from tab changes setup an SA5 callback with the `slideChanged` event. When called, it will contain the slider object, and the index of the new slide ( 0-based ).&#x20;

If you have multiple sliders marked with \[wfu-slider], you can assign a unique name, and access it through `slider.name`, as in this example;&#x20;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['slideChanged', 
  (slider, index) => {
    
    console.log("SLIDE CHANGED", slider.name, slider, index); 

    switch(slider.name) {
      case "demo1": // Demo 1 slide changed

        break;
      case "demo2": // Demo 2 slide changed

        break;
    }

  }]); 
</script>
```

### Manipulating the Slider <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Outside of callback events, you can also access the SA5 Slider object by constructing one;

```javascript
const slider = new sa5.WebflowSlider(
    $("[wfu-slider=demo1]")[0]
); 
```

Once you have this, you can call its methods and properties;

Properties;

* `name` property returns the `[wfu-slider]` name, if one was set.
* `currentIndex` gets or sets the 0-based index of the current slide ( i.e. 5 slides would be numbered 0, 1, 2, 3, 4 ).
* `currentNum` gets or sets the 1-based index of the current slide ( i.e. 5 slides would be numbered 1, 2, 3, 4, 5 ).&#x20;

Methods;&#x20;

* `goToFirst()` navigates to the first slide
* `goToLast()` navigates to the last slide
* `goToPrev()` navigates to the prev slide
* `goToNext()` navigates to the next slide

See [Slider Code Examples](slider-code-examples.md) for more.&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start-or-sa5-elements.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

### STEP 3 - ( OPTIONAL ) Use the API & Callbacks to control the element from your custom code

See above for details.





