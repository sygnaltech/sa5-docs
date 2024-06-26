---
description: >-
  Automatically show or hide your Webflow modals, popups & more after the user
  closes them for a specified number of days.
---

# Webflow Modals & Popups Auto-Open and Auto-Close

{% hint style="info" %}
CONCEPTUAL
{% endhint %}

Goals;

* Timed open, in ms
  * Auto unhide
  * Or, click trigger, for interaction
  * Respects suppression setting
* Triggered open, by scroll
* Triggered open, by exit intent&#x20;
* Timed close, in ms
  * Element removal
  * Or, click trigger, for interaction
  * ? Option to suppress



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

{% hint style="warning" %}
In Webflow, modals are commonly "closed" using an interaction. It may include fade-out, slide-out, or spin-off-screen effects. SA5 simply deletes the element outright, so those exit animations would not be seen, the modal will simply disappear.&#x20;
{% endhint %}

### Add the SA5 Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### I want this element to represent my suppressible content

To the outermost element you want to suppress;

* Add a custom attribute of `wfu-modal` = ( name ). Give it any custom name you like. That name will be used in the suppression tracking so you can e.g. have the same modal on every page, and suppress it site-wide.

{% hint style="info" %}
This name must be unique.
{% endhint %}



Multiple triggers ( scroll hover, exit, etc? )&#x20;



### wfu-modal-trigger = load | click | scroll | hover | exit | timer

Modal triggers display the modal element and fall into two categories - **automatic triggers** and **element triggers**.

**Automatic** triggers occur due to some system event, and are always configured on the modal element directly. These include;

* load triggers immediately on page load
* timer triggers fire after a specified delay
* scroll triggers fire at a % of page scrolled
* exit triggers fire on an exit intent&#x20;

**Element** triggers occur in relation to another element on the page, and are configured on that element;

* `click` triggers
* `hover` triggers
* `scroll-into-view` triggers

{% hint style="info" %}
Element triggers require an additional attribute of `wfu-modal-trigger-target` which specifies the **name** of the modal you are triggering ( as defined by `wfu-modal` )
{% endhint %}



### wfu-modal-trigger-config

OPTIONAL, except...&#x20;

* for timer, this is set to ms
* for scroll, this is set to % of scroll

### wfu-modal-trigger-target = ( name )

Used only with **element** triggers. Specifies the name of the modal you are triggering ( as defined by `wfu-modal` )

Indicates the target element, for triggers which are on a separate element

click, scroll





* Add a custom attribute of `wfu-modal-trigger` = `load`.&#x20;
* Add the suppression duration you want, using `wfu-modal-suppress-days` = ( days ). If unspecified, defaults to about 1 year.&#x20;

### I want this element to be the close button

To the close element(s) within the modal;

* Add an attribute of `wfu-modal-close` = `true`
* Add an attribute of `wfu-modal-close-type` = `auto`



wfu-modal-close-trigger = click | timer

wfu-modal-close-trigger-config = ms&#x20;

wfu-modal-close-trigger-target OPTIONAL = ( name )

Can be placed on any element

If placed on an element within the modal, an unspecified target will automatically target the current modal.&#x20;



wfu-modal-close-method = remove | hide&#x20;





## Questions? Feature Requests?

Visit the SA5 forum link at the top of this page.

