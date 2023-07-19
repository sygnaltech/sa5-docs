---
description: Interact with Webflow's Tabs Element
---

# Tabs Element



{% hint style="danger" %}
**COMING SOON**

Not yet released.
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to display a caption inside of Webflow’s lightboxes, which is automatically pulled from the CMS.

## Demonstration

## Use Cases <a href="#usage-notes" id="usage-notes"></a>

Enhance navigation;&#x20;

* Link a button or other element to your tab element, to trigger navigation to the first, last, next, or previous tab. These elements can be anywhere on your page, including within the tab element. You can have as many of them as you like.&#x20;
* Programmatically navigate the tabs element using JavaScript.&#x20;

Future; &#x20;

* Respond to custom code notifications on a tab change.
* Choose to allow or prevent tab changes.&#x20;

<mark style="color:orange;">Change to 1-based indexing.</mark>&#x20;

## Setup <a href="#prepare-your-collection-list" id="prepare-your-collection-list"></a>

* Setup your tabs element.
* Setup other "control" elements that will affect it ( optional ).&#x20;

### `wfu-tabs` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-tabs` custom attribute to the a Tab element. Give it a unique label to identify that tabs element uniquely, e.g. `tabs1`.&#x20;

This makes the tab element accessible in code, and selectable by the other tabs custom attributes.

* Register it in the list of elements&#x20;
* Error if it's not unique ( and avoid load )&#x20;

### `wfu-tabs-action` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

I want a button or link to change tabs by index or text label.

To any button or link, you can define an action;

* first - select the first tab
* prev - select the previous tab
* next - select the next tab
* last - select the last tab
* <mark style="color:orange;">goto - select the specified tab</mark>
* <mark style="color:orange;">goto ( name ) - matches first one only, starting from tab 1</mark>&#x20;

### `wfu-tabs-action-tab` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

For the goto action, specifies the tab you want to navigate to.&#x20;

* <mark style="color:orange;">number - indicates the tab index, 0, 1, 2...  ( index )</mark>
* <mark style="color:orange;">name - matches first one only, starting from tab 1</mark>&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/dist/css/webflow-elements.min.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/nocode/webflow-elements.min.js"></script>
```
{% endcode %}

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.





