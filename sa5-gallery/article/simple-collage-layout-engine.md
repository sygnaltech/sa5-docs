---
description: Ideal for simple collage-style layouts
---

# Simple Collage Layout Engine

Ideal for-

* Any number of images
* Where the entire image set should fill a square, with no jagged edges
* Where it's ok to crop the edges of the images
* Where the focal point for most images is center&#x20;

## Examples  &#x20;

{% embed url="https://x-gallery-e9e055.webflow.io/home-2" %}

{% tabs %}
{% tab title="Example 1" %}
<figure><img src="../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Example 2" %}
<figure><img src="../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

## Notes&#x20;

* Adjusts colspan randomly against a 12 col grid&#x20;
* Ensures all rows fill 12 cols exactly
* Seeks to avoid dupliate adjacent row layouts&#x20;

## Configuration Options

None, currently.&#x20;

Future;

* Perhaps min and max items preferred per row
* Perhaps the colspan options, e.g. 3, 6, 9, 4, 8... &#x20;
* Hinting, on landscape, portrait, and square imagery&#x20;
* Hinting, on image focal point ( grid of 9, like top-left, center-middle )  &#x20;

<img src="../../.gitbook/assets/file.excalidraw (3).svg" alt="" class="gitbook-drawing">

## Designer Controls&#x20;

* Row height&#x20;
  * Set fixed, e.g. `400px`
  * or, as function of width so it scales, e.g. `30vw`&#x20;
  * This is usually set on the card or image itself&#x20;
* Set images to 100% width, Fit: Cover &#x20;

## Internal Notes

[https://x-gallery-e9e055.design.webflow.com/?pageId=6795f0a055de576f76b34b1b\&workflow=canvas\&mode=edit](https://x-gallery-e9e055.design.webflow.com/?pageId=6795f0a055de576f76b34b1b\&workflow=canvas\&mode=edit)

