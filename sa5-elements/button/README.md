---
description: Interact with Webflow's Button Element
---

# Button Element

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to work with the Webflow button element.

* Enable / disable a button. Disabled buttons cannot be clicked.&#x20;
* Supports disabled-state styling through a special class you choose.&#x20;
* Buttons can load as disabled and be enabled later, or load as enabled and be disabled later.&#x20;

## Future

Currently designed to work specifically with Webflow's Button element.

* May support the Form Submit button later.&#x20;
* May support interactions-rebinding for the disabled state.&#x20;

## Demonstration

Check the button demonstration here-&#x20;

{% embed url="https://video-player-control.webflow.io/vimeo" %}
Demo
{% endembed %}

## Use Cases <a href="#usage-notes" id="usage-notes"></a>

* Load a button as disabled, and then enabled it once;
  * The user has completed certain tasks, to the satisfaction of your custom code
  * The user has watched a video to completion, or a certain %
  * A certain amount of time has passed

## Setup <a href="#prepare-your-collection-list" id="prepare-your-collection-list"></a>

* Setup your button element.

### `wfu-button` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-button` custom attribute to the Button element you want to control Give it a unique **name** to identify that element uniquely, e.g. `button1`.&#x20;

This makes the button element accessible in code.

{% hint style="info" %}
Make certain only one button on the page has the assigned name. The name is used to reference it, and in callback notifications.&#x20;
{% endhint %}

### `wfu-button-enabled` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Set to `true` or `false`, depending on the initial state you want.&#x20;

### `wfu-preload` attribute

**OPTIONAL.** Indicates the appearance before the button is initialized. Highly recommended if your initial state is disabled.&#x20;

* `hidden` hides the element until initialization is complete.&#x20;
* `invisible` maintains the space for the element, but the elent does nto appear until initialization is complete.

### `wfu-button-disabled-class` attribute

**OPTIONAL.** Allows you to specify a custom class that will be added to the button's class list when disabled, and removed when enabled. This will be in combination with whatever other classes you have already defined.

{% hint style="success" %}
The best practice here is to create it as a compound class, e.g. `is-disabled`, and then style the button the way you want it to appear in disabled state. Change the hover, change the colors, etc.
{% endhint %}

## JavaScript API

To access a button and manipulate it, simply create an instance using the name you've assigned.&#x20;

### Enable / disable button

Set the `enabled` property to `true` or `false`.&#x20;

```html
<script>
function enableButton() {

  // Create the Sa5 button, by name
  var btn = window.Sa5.Sa5Button.create("my-button");
  if (btn)
    btn.enabled = true; // Enable it 
  
}
</script>
```

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.





