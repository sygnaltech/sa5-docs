---
description: >-
  Automatically suppress your Webflow modals, popups & more after the user
  closes them for a specified number of days.
---

# Custom Form Select ❺🧪

Finsweet developed a creative solution to select styling, which uses a dropdown element as a stylable proxy.&#x20;

However;

* It has no published API, which makes it unsuitable for resetting in situations such as a progressive filtering UX.&#x20;
* The select is physically within the dropdown, which means it's not possible to selectively choose whether you want the select or the dropdown to show, at different responsive  breakpoints.&#x20;

## Use Cases&#x20;

* Progressive filtering
* Responsive switching between dropdowns ( desktop ), and native selects ( mobile )

## Usage Notes

### Add the SA5 Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../sa5-modals/quick-start.md).&#x20;



{% hint style="info" %}
Docs not yet written.&#x20;
{% endhint %}





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

