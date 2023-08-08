---
description: Configure How Your Placeholders Look Before Data-Binding
---

# Preloaders

{% hint style="warning" %}
EXPERIMENTING: Not yet part of SA5 release code.&#x20;
{% endhint %}

Preloaders refer to the display of elements prior to data-binding. Once data-binding is complete, the preloader state / elements are removed and the data-bound element(s) are shown.&#x20;

Scenarios;

* We want the element to appear as we've created it in the designer&#x20;
* We don't want to the element to appear
* We don't want the element to appear, however we want it to take up space&#x20;
* We want to show some kind of loading animation where the element would be &#x20;
* We want to show a completely different set of elements as a placeholder&#x20;

## Types of Preloaders

With **tenative** attributes and setup;&#x20;

### wfu-preload = none

Or, no preload attribute.&#x20;

Just show the element as is. Good when you have placeholder text, for example.&#x20;

### wfu-preload = hidden

The element is not visible, as though it did not exist.

### wfu-preload = invisible

The element is not visible, but takes up the space the element normally would in the designer.

## Future

{% hint style="info" %}
FUTURE: Everything here and below is Under Development
{% endhint %}

### wfu-preload = animated

The element is visible, but 100% masked. &#x20;

Sizing approach? Masking approach? Text is blacked out?&#x20;

#### wfu-preload-anim-style = ANIMATION STYLE NAME

Support a few different types of preloader animations&#x20;

#### wfu-preload-anim-class = CLASS-NAME

CLASS styling, e.g. colors and gradients?

Copy element from page&#x20;

### wfu-preload = custom

wfu-preloader-custom = NAME

## Custom Preloaders

Reference and clone.&#x20;

### wfu-preloader = NAME

A unique name for a custom preloader, where it will be found and cloned from. &#x20;

Non-cloning possibilities-&#x20;

* Child of databound element?
* Adjacent element&#x20;
* Referenced by position relationship to bound element&#x20;







