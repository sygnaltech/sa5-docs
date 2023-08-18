---
description: Interact with Webflow's Tabs Element
---

# Tabs Element ❺

{% hint style="success" %}
**2023-Aug-19** - Added `tabChanged` callback event. Tabs has also been moved into the elements library, and is using our standarized "deck" interface which means the methods and properties here should align with similar deck-type elements such as the Slider.&#x20;
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This feature allows you to work with the Webflow tabs element.

* Switch tabs programmatically- first, next, prev, and last, or go to a specific tab index
* Get the current tab index
* Receive JavaScript events when the tab is changed, even if it is changed by code&#x20;

## Demonstration

Check the tabs demonstrations here-&#x20;

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}

## Use Cases <a href="#usage-notes" id="usage-notes"></a>

Enhance navigation;&#x20;

* Link a button or other element to your tab element, to trigger navigation to the first, last, next, or previous tab. These elements can be anywhere on your page, including within the tab element. You can have as many of them as you like.&#x20;
* Programmatically navigate the tabs element using JavaScript.&#x20;

Future; &#x20;

* Respond to custom code notifications on a tab change.
* Choose to allow or prevent tab changes.&#x20;

## Setup <a href="#prepare-your-collection-list" id="prepare-your-collection-list"></a>

* Setup your tabs element.
* Setup other "control" elements that will affect it ( optional ).&#x20;

### `wfu-tabs` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-tabs` custom attribute to the a Tab element. Give it a unique label to identify that tabs element uniquely, e.g. `tabs1`.&#x20;

This makes the tab element accessible in code, and selectable by the other tabs custom attributes.

* Register it in the list of elements&#x20;
* Error if it's not unique ( and avoid load )&#x20;

wfu-tab-default attribute

Add the wfu-tab-default custom attribute to a specific tab directly. This tab will be automatically selected on page load.

## Future

{% hint style="danger" %}
These are under consideration for implementation, and not yet implemented.&#x20;
{% endhint %}

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

## JavaScript API

### Events

To receive events from tab changes setup an SA5 callback with the `tabChanged` event. When called, it will contain the tabs object, and the index of the new tab ( 0-based ).&#x20;

If you have multiple tabs elements marked with \[wfu-tabs], you can assign a unique name, and access it through `tabs.name`, as in this example;&#x20;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['tabChanged', 
  (tabs, index) => {
    
    console.log("TAB CHANGED", tabs.name, slider, index); 

    switch(tabs.name) {
      case "demo1": // Demo 1 tabs changed

        break;
      case "demo2": // Demo 2 tabs changed

        break;
    }

  }]); 
</script>
```

### Element Control <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Outside of callback events, you can also access the SA5 Tabs object by constructing one;

```javascript
const tabs = new sa5.WebflowTabs(
    $("[wfu-tabs=demo1]")[0]
); 
```

Once you have this, you can call its methods and properties;

Properties;

* name property returns the `[wfu-tabs]` name, if one was set.
* `currentIndex` returns the 0-based index of the current slide.
* `currentNum` returns the 1-based index.&#x20;

Methods;

* `goToFirst()` navigates to the first tab
* `goToLast()` navigates to the last tab
* `goToPrev()` navigates to the prev tab
* `goToNext()` navigates to the next tab

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

{% hint style="info" %}
This feature is using WFU's v5 new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;

You can use both the v4 and v5 libraries simultaneously to get the full feature set during migration.
{% endhint %}

Add this to the **before HEAD** custom code area of your site or page.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Elements -->
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.32/dist/nocode/webflow-elements.js"></script>
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

### STEP 3 - ( OPTIONAL ) Use the API & Callbacks to control the element from your custom code

See above for details.





