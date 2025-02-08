---
description: Display CMS-Managed Captions in Webflow’s Lightboxes
---

# CMS & Lightbox + Captions

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to display your image alt-text as a caption inside of Webflow’s lightboxes.&#x20;

{% hint style="info" %}
Works with CMS-stored images, including multi-image fields. It does not support captioning video, due some complexities matching captions to the currently displayed video.
{% endhint %}

{% hint style="danger" %}
**2024-Aug-28 - Note**\
There is presently a glitch in Webflow where _CMS multi-image_ fields will publish an empty `alt=""` attribute even when they have valid alt text defined. This will prevent captions from appearing in the third lightbox scenario above.&#x20;

_Webflow's team is aware of this and working on a fix._&#x20;
{% endhint %}

### About Alt Text in Webflow

SA5 generates the captions from your image alt-text. Your goal is to create that alt text the way you want, and publish it so that it exists correctly in your HTML, e.g. `<img alt="Sunset photo">`&#x20;

In Webflow there are _three_ different ways to define and manage alt-text, depending on where your images are stored in Webflow.&#x20;

1. Images stored in the **project Assets** panel can have their alt text directly specified in the assets panel.  This is then automatically generated when you use that image on your pages.&#x20;
2. Images stored in a **CMS image field** do not have this capability, however you can create a separate text field to contain your caption, and then bind that text field to your image's Alt Text property on the canvas.&#x20;
3. Images stored in a **CMS multi-image field** DO have the ability to define alt text directly with the image, and this will publish as the `alt="..."` property in your pages.&#x20;

## Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/cms-lightbox-captions" %}
Cloneable demo site.
{% endembed %}

## Getting Started <a href="#usage-notes" id="usage-notes"></a>

1. **Add the library** as detailed in [Quick Start](../../quick-start.md).
2. Add the required attributes below
3. Publish and test your site&#x20;

{% hint style="info" %}
To correct setup your lightboxes and bind alt-text to your images, refer to the clonable
{% endhint %}

## Required Attributes

### `wfu-lightbox-captions` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-lightbox-captions` custom attribute ( no value needed ) to the Lightbox Link, which is the _outermost_ part of your lightbox element.&#x20;

_That's it!_&#x20;

The CMS field you've bound to Alt Text will be displayed as the caption in lightbox view.

## Styling Captions

Lightbox captions are generated as follows;

{% code overflow="wrap" %}
```html
<figcaption class="w-lightbox-caption">The Excaliburs are ready to rumble</figcaption>
```
{% endcode %}

To style these, add an embed with custom CSS in your page;

{% hint style="info" %}
You can CSS-style any aspect of the caption bar.  Here we show text and background coloring only;&#x20;
{% endhint %}

```html
<style>
figcaption.w-lightbox-caption {
  color: white;
  background-color: teal; 
}
</style>
```

<figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.





