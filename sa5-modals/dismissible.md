---
description: >-
  Automatically suppress your Webflow modals, popups & more after the user
  closes them, for a specified number of days.
---

# Dismissible Elements

{% hint style="success" %}
This feature works alongside the our other modal capabilities but has been split off for more general usage in other contexts.  You can distinguish these attributes by the fact that they all begin with `wfu-dismiss` .&#x20;
{% endhint %}

This feature enables you to easily "close" and suppress UI elements so that they will not appear for a specified number of days, even on page reload.&#x20;

It's primarily used for;

* Alert banners
* Notices
* Interactions ( IX2 )-based modals & pop-ups&#x20;

But can be used for any elements that you want to suppress.&#x20;

## Demonstration <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

{% embed url="https://sa5-modals.webflow.io/dismissable" %}
Demo Page
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/sa5-modals" %}
Cloneable
{% endembed %}

## Use Cases&#x20;

* Suppress a notification banner &#x20;
* Suppress an interactions-based modal popup
* Suppress a CTA or special offer&#x20;

## Usage Notes

This library simplifies dismissable elements into two parts-

1. The dismissable element itself, which can be any popup, DIV, or other element
2. Close button element(s), such as a corner "X" or a "Close" button. These must be positioned _within_ the dismissable element as descendants.&#x20;

To implement this, design your elements, alerts, modals or CTAs however you like.&#x20;

The close functionality will be an element with a special custom attribute on it. When closed, SA5 will _remove_ the element from the DOM, and suppress it for as long as you've requested. &#x20;

## Getting Started

Once your elements are setup as described in Usage Notes, you can apply the attributes.&#x20;

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Identify your dismissable element <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

To the outermost element you want to suppress;

* Add a custom attribute of `wfu-dismiss` = ( name ). Give it any custom name you like. That name will be used in the suppression tracking so you can e.g. have the same modal on every page, and suppress it site-wide.
* Add a custom attribute of `wfu-dismiss-trigger` = `load`.&#x20;
* Add the suppression duration you want, using `wfu-dismiss-suppress-days` = ( days ). If unspecified, defaults to about 1 year.&#x20;

### STEP 3 - Identify your close button element <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

To the close element(s) _within the modal_;

* Add an attribute of `wfu-dismiss-close` = `true`
* Add an attribute of `wfu-dismiss-close-type` = `auto`

{% hint style="success" %}
Repeat this process for any number of elements you want.&#x20;

The name you specify is site-wide, so all elements with the same name will be suppressed. Use this to suppress an announcement banner-site wide, or even to suppress several variations of the same banner that might appear throughout the page.&#x20;
{% endhint %}

## Technical Notes

We're currently using a cookie for the suppression, so that it automatically expires.&#x20;

## Future

wfu-dismiss-action = open | close

wfu-dismiss-action-method = auto | interaction

wfu-dismiss-action-trigger = click | timer | scroll | exit

wfu-dismiss-action-trigger-ms = 10000

## Questions? Feature Requests?

Visit the SA5 forum link at the top of this page.

