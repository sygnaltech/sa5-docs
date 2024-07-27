---
description: SA5 Slider Code Examples
---

# Lightbox JS API

{% hint style="warning" %}
**BETA.** This API may change in future releases.
{% endhint %}

## Reset Webflow Lightboxes <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

When you dynamically create or modify Webflow's lightbox elements, you'll need to reset them.&#x20;

{% code overflow="wrap" %}
```javascript
window.sa5.Sa5Lightbox.resetLightbox(); 
```
{% endcode %}

## Create a new Lightbox

Creating a new lightbox requires;

* Containing element. In this example, `container` references a containing element such as a DIV.&#x20;
* Thumbnail image
* Group name

Provide an image URL and a group name.&#x20;

{% code overflow="wrap" %}
```javascript
window.sa5.Sa5Lightbox.createNew(
  container, 
  `https://picsum.photos/id/238/1000/1000`, 
  "group"
  ); 
```
{% endcode %}

By default, the thumbnail image is used as the lightbox media as well.

## Future

* Wrap an existing element in a lightbox
* Add multiple media
  * Video support
* Automatic lightbox resettings
* Support for CMS captions and groups&#x20;
* Events
  * Open / close / swipe



