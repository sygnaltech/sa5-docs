---
description: >-
  Automatically suppress your Webflow modals, popups & more after the user
  closes them for a specified number of days.
---

# Dismissible Elements

{% hint style="danger" %}
Important, the attributes on this feature are likely to change as we complete development on the new modals feature.  We'll retain the "dismiss-only" feature, but it may change names to e.g. `wfu-dismiss` &#x20;
{% endhint %}



This feature enables you to easily "close" and suppress UI elements so that they will not appear for a specified number of days, even on page reload.&#x20;

It's primarily used for;

* Alert banners
* Notices
* Interactions ( IX2 )-based modals & pop-ups&#x20;

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

{% hint style="warning" %}
In Webflow, modals are commonly "closed" using an interaction. It may include fade-out, slide-out, or spin-off-screen effects. SA5 simply deletes the element outright, so those exit animations would not be seen, the modal will simply disappear.&#x20;
{% endhint %}

### Add the SA5 Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### I want this element to represent my suppressible content

To the outermost element you want to suppress;

* Add a custom attribute of `wfu-modal` = ( name ). Give it any custom name you like. That name will be used in the suppression tracking so you can e.g. have the same modal on every page, and suppress it site-wide.
* Add a custom attribute of `wfu-modal-trigger` = `load`.&#x20;
* Add the suppression duration you want, using `wfu-modal-suppress-days` = ( days ). If unspecified, defaults to about 1 year.&#x20;

### I want this element to be the close button

To the close element(s) within the modal;

* Add an attribute of `wfu-modal-close` = `true`
* Add an attribute of `wfu-modal-close-type` = `auto`

## Considering

wfu-modal-action = open | close

wfu-modal-action-method = auto | interaction

wfu-modal-action-trigger = click | timer | scroll | exit

wfu-modal-action-trigger-ms = 10000

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

This library uses attributes only, so we've taken a NOCODE approach to its design.

{% hint style="info" %}
First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;
{% endhint %}

### Apply the custom attributes based on your configuration needs <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

See above, and the feature-specific sub pages for details.

## Questions? Feature Requests?

Visit the SA5 forum link at the top of this page.

