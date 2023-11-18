---
description: Webflow Modals, Popups & more
---

# Webflow Modals & Popups ❺🧪

This feature enables you to easily "close" and suppress UI elements so that they will not appear for a specified number of days, even on page reload.&#x20;

It's primarily used for;

* Alert banners
* Notices
* Modals & pop-ups

But can be used for any elements that you want to suppress.

## Demonstration <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

{% embed url="https://pop-up-modal-cc97fc.webflow.io/" %}

## Use Cases&#x20;

* Suppress an interactions-based modal popup
* Suppress a CTA or other banner&#x20;

## Usage Notes

This library simplifies modal design into two parts-

1. The modal element itself, which can be any popup, DIV, or other element
2. Close button element(s). These must be positioned _within_ the modal element as descendants.&#x20;

To implement this, build your modals or CTAs however you like.&#x20;

The close functionality will be an element with a special custom attribute on it. When closed, SA5 will _remove_ the element from the DOM, and suppress it for as long as you've requested. &#x20;

### I want this element to represent my suppressable content

To the outermost element you want to suppress;

* Add a custom attribute of `wfu-modal` = ( name ). Give it any custom name you like. That name will be used in the suppression tracking so you can e.g. have the same modal on every page, and suppress it site-wide.
* Add a custom attribute of `wfu-modal-trigger` = `load`.&#x20;
* Add the suppression duration you want, using `wfu-modal-suppress-days` = ( days ). If unspecified, defaults to about 1 year.&#x20;

### I want this element to be the close button

To the close element(s) within the modal;

* Add an attribute of `wfu-modal-close` = `true`
* Add an attribute of `wfu-modal-close-type` = `auto`

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Add the custom attributes as above

See _notes_ above. &#x20;

