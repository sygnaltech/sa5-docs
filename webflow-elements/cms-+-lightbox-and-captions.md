---
description: Display CMS-Managed Captions in Webflow’s Lightboxes
---

# CMS & Lightbox + Captions

## Overivew <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to display a caption inside of Webflow’s lightboxes, which is automatically pulled from the CMS.

{% hint style="info" %}
Works with CMS-stored images, thumbnails, and captions. Does not support captioning video, due some complexities matching captions to the currently displayed video.
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

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/dist/css/webflow-elements.css">
```

Add this JS reference to the BODY of your site or page.

```
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/src/nocode/webflow-elements.js"></script>
```

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

## Resources

{% embed url="https://wfu.sygnal.com/docs/webflow-elements/cms-lightbox-captions/" %}
Legacy docs
{% endembed %}



