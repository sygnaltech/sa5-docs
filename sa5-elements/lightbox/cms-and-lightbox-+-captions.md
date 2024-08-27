---
description: Display CMS-Managed Captions in Webflow’s Lightboxes
---

# CMS & Lightbox + Captions ❺

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to display your image alt-text as a caption inside of Webflow’s lightboxes.&#x20;

{% hint style="info" %}
Works with CMS-stored images, thumbnails, and captions. Does not support captioning video, due some complexities matching captions to the currently displayed video.
{% endhint %}

### About Alt Text in Webflow

SA5 generates the captions from your image alt-text. Your goal is to create that alt text the way you want, and publish it so that it exists correctly in your HTML, e.g. `<img alt="Sunset photo">`&#x20;

In Webflow there are _three_ different ways to define and manage alt-text, depending on where your images are stored in Webflow.&#x20;

1. Images stored in the **project Assets** panel can have their alt text directly specified in the assets panel.  This is then automatically generated when you use that image on your pages.&#x20;
2. Images stored in a **CMS image field** do not have this capability, however you can create a separate text field to contain your caption, and then bind that text field to your image's Alt Text property on the canvas.&#x20;
3. Images stored in a **CMS multi-image field** DO have the ability to define alt text directly with the image, and this will publish as the `alt="..."` property in your pages.&#x20;

{% hint style="danger" %}
**2024-Aug-28 BUG**\
We were just alerted to a bug in Webflow where _CMS multi-image_ fields will publish an empty `alt=""` attribute even when they have valid alt text defined. This will prevent captions from appearing in the third lightbox scenario above, until it's repaired.&#x20;
{% endhint %}

## Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/cms-lightbox-captions" %}
Cloneable demo site.
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### Prepare your CMS <a href="#prepare-your-cms" id="prepare-your-cms"></a>

* Include a photo in your collection items
* Include a plain text, single-line caption

### Prepare your Collection List <a href="#prepare-your-collection-list" id="prepare-your-collection-list"></a>

* Setup your Collection List
* Add your Lightbox Element
* Data bind it, as usual, to the thumb and main images you want
  * Also set Alt Text to the plain text caption you want

### `wfu-lightbox-captions` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-lightbox-captions` custom attribute (no value needed) to the Lightbox Link, which is the _outermost_ lightbox element.

_That's it!_&#x20;

The CMS field you've bound to Alt Text will be displayed as the caption in lightbox view.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.





