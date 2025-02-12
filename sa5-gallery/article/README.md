---
description: >-
  Automatically suppress your Webflow modals, popups & more after the user
  closes them for a specified number of days.
---

# Gallery ❺🧪

Finsweet developed a creative solution to select styling, which uses a dropdown element as a stylable proxy.&#x20;

However;

* It has no published API, which makes it unsuitable for resetting in situations such as a progressive filtering UX.&#x20;
* The select is physically within the dropdown, which means it's not possible to selectively choose whether you want the select or the dropdown to show, at different responsive  breakpoints.&#x20;



## Usage Notes

### STEP 1 - Add the SA5 Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).&#x20;

### STEP 2 - Add the SA5 Attributes&#x20;

All attributes should be added to the Collection List element, which is the center

### STEP 3 - Configure your Collection List layout&#x20;

The Collection List element must be set to grid.  &#x20;





## Attributes

All attributes should be added to the Collection List element, which is the center element in Webflow's 3-element collection list construction.&#x20;

### `wfu-gallery` = ( no value )

**Required.** &#x20;

### `wfu-gallery-layout` = ( layout engine )

**Required.**  Choose the layout engine you want to utilize;&#x20;

* `simple-collage`&#x20;

Here are some quick samples of the layout options; &#x20;

{% tabs %}
{% tab title="simple-collage" %}
<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

### `wfu-preload` = `hidden`&#x20;

**Optional.**  This avoids flicker by ensuring that the gallery is not shown until the layout is complete.&#x20;

_Learn more about_ [_SA5's preloading options_](../../overview/preloaders.md)_._ &#x20;

## Future

Automatic 12-column setting&#x20;

Responsive rules

Configuration block for layout parameters&#x20;







### &#x20;<a href="#step-1---add-the-library" id="step-1---add-the-library"></a>













### I want this element to represent my suppressible content

To the outermost element you want to suppress;

* Add a custom attribute of `wfu-modal` = ( name ). Give it any custom name you like. That name will be used in the suppression tracking so you can e.g. have the same modal on every page, and suppress it site-wide.
* Add a custom attribute of `wfu-modal-trigger` = `load`.&#x20;
* Add the suppression duration you want, using `wfu-modal-suppress-days` = ( days ). If unspecified, defaults to about 1 year.&#x20;

### I want this element to be the close button

To the close element(s) within the modal;

* Add an attribute of `wfu-modal-close` = `true`
* Add an attribute of `wfu-modal-close-type` = `auto`

## Questions? Feature Requests?

Visit the SA5 forum link at the top of this page.

