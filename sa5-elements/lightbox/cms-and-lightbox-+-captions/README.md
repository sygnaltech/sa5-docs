---
description: Display CMS-Managed Captions in Webflow’s Lightboxes
---

# CMS Lightbox + Captions

This feature allows you to extend the Webflow native lightbox with captions, which appear as a single line of text at the bottom of each image.&#x20;

<figure><img src="../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

## Important Limitations&#x20;

Webflow Lightboxes have specific programming design that SA5 is leveraging to generate captions.  As a result, the range of supported lightbox setups is very specific;&#x20;

{% hint style="success" %}
The configuration that SA5 Lightbox Captions supports requires;

* The lightbox must contain a **child thumbnail image**, whose `alt` text is defined. This element can be hidden from view, but must exist.&#x20;
* The lightbox media must specify a **single image**, or be bound to a **CMS Image field** ( not a mult&#x69;_-image field_ )&#x20;
{% endhint %}

{% hint style="danger" %}
Video media cannot be captioned..&#x20;
{% endhint %}

{% hint style="danger" %}
**Webflow Alt Text Bug Note**\
Since 2024-Aug-28, there is a bug in Webflow where _CMS multi-image_ fields will publish an empty `alt=""` attribute even when they have valid alt text defined on the images. This means that even when a collection list is bound to the multi-image field, and the lightboxes are bound directly to the individual images. alt text and captions still can not work.&#x20;

_Webflow's team is aware of this and has reported they are working on a fix._&#x20;

_**However as of 2025-Apr this bug still exists.**_&#x20;
{% endhint %}

Unsupported configurations;

* Captioning videos&#x20;
* Media bound to multi-image fields, or containing multiple images ( only the first image will caption )
* Lightboxes without a thumbnail image&#x20;
* Lightboxes in a collection list that is bound to items in a multi-image field.  It's poss

### About Alt Text in Webflow

SA5 Lightbox Captions work by locating the _thumbnail image's_ `alt` text, and then applying it to Webflow's internal lightbox JSON structures.  Due to the way lightboxes are programmed, this works only on the first image in an image set, and seems to require the thumbnail as a reference.&#x20;

Your goal is to create that alt text _on the thumbnail_ the way you want, and publish it so that it exists correctly in your HTML, e.g. `<img alt="Sunset photo">`&#x20;

In Webflow there are _three_ different ways to define and manage alt-text, depending on where your images are stored in Webflow.&#x20;

1. Images stored in the **project Assets** panel can have their alt text directly specified in the assets panel.  This is then automatically generated when you use that image on your pages.&#x20;
2. Images stored in a **CMS image field** do not have this capability, however you can create a separate text field to contain your caption, and then bind that text field to your image's Alt Text property on the canvas.&#x20;
3. Images stored in a **CMS multi-image field** DO have the ability to define alt text directly with the image, and this will publish as the `alt="..."` property in your pages.&#x20;

## About Webflow's Lightbox Configurations &#x20;

Webflow has a lot of different lightbox configurations which all work slightly differently in regards to how they link media.&#x20;

* Lightbox + Static Image.  No CMS involvement.  Media is set to a single static image.&#x20;
* Lightbox + Multiple Static Images.  No CMS involvement. Media has been assigned a series of static images.&#x20;
* Lightbox + CMS Image Field.  This configuration is common in a main collection list, but can also occur in a nested collection list that is bound to a Multi-Image Field.&#x20;
* Lightbox + CMS Multi-Image Field.  In this configuration, the Lightbox is _directly_ bound to the Multi-Image Field.&#x20;

These configuration differences can significantly impact the rendered HTML. &#x20;

| Configuration                                                                                                                        | SA5 Captions Supported? | Notes                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------- | -------------------------------------------------------------------------------------------------- |
| Lightbox + Static Image                                                                                                              | **Yes**                 |                                                                                                    |
| Lightbox + Multiple Static Images                                                                                                    | No                      |                                                                                                    |
| Lightbox + CMS Image Field ( both direct, and nested )                                                                               | **Yes**                 | The first image ( only ) will support captions.                                                    |
| Lightbox + CMS Multi-Image Field ( media directly bound )                                                                            | No                      | The first image ( only ) will support captions.                                                    |
| Lightbox + CMS Multi-Image Field ( collection list bound to multi-image field, lightbox bound to individual image within that list ) | No                      | See Webflow Bug notes above regarding CMS multi-image fields and alt text.                         |
| Lightbox + Video Media                                                                                                               | No                      |                                                                                                    |
| Lightbox w/ no thumbnail image                                                                                                       | No                      | Without the thumbnail image inside of the lightbox there is nowhere for you to bind the alt text.  |



## Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/cms-lightbox-captions" %}
Cloneable demo site.
{% endembed %}

## Getting Started <a href="#usage-notes" id="usage-notes"></a>

1. **Add the library** as detailed in [Quick Start](../../quick-start.md).
2. Add the required attributes below
3. Publish and test your site&#x20;

{% hint style="info" %}
To correctly setup your lightboxes and bind alt-text to your images, refer to the clonable.&#x20;
{% endhint %}

## Usage Notes&#x20;

### wfu-lightbox-captions = ( no value needed ) <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

**Required.**  Add the `wfu-lightbox-captions` custom attribute ( no value needed ) to the Lightbox Link, which is the _outermost_ part of your lightbox element.&#x20;

{% hint style="success" %}
By default, when you create a new lightbox element it includes an image element child which acts as a thumbnail.  Currently, we use this element to represent your main image, and the alt text on that thumbnail is used as the caption text. &#x20;

While this image element is essentail for SA5 Lightbox Captions to function, it does not need to be visible to users.  If you want a different lightbox trigger such as plain text or an SVG, you can simply style the image element as display: none. &#x20;
{% endhint %}

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

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.





