---
description: Lazy Load... anything!
---

# Lazy Load

A frequent request among Webflow designers is the ability to lazy load embeds like Calendly, or Google Maps, so that _no loading occurs_ until the user scrolls down to that portion of the page.&#x20;

The idea is to maximze page speed on the initial load for optimal user experience and SEO.&#x20;

SA5 solves this by pulling your tagged elements out of the flow of the generated document object model ( DOM ), while ensuring that they are fully editable and stylable in the Webflow Designer.&#x20;

Then, when you scroll to that position of the page, we re-constitute them and they become fully functional.&#x20;

## Goals&#x20;

* Prevent an Embed or a group of elements from loading in the published page until they are scrolled into view
* Ensure that those elements are fully accessible in the Webflow Designer at design time&#x20;

## Usage Notes

Design and style your elements as normal in the designer- SA5's Lazy Load can be easily configured on top of that.&#x20;

### Best Practices &#x20;

Lazy loading is triggered when elements scroll into view.  That means for it to be of value, you want to configure it on elements that are below-the-fold.&#x20;

Lazy loading works best when all of the code and HTML is together in a single embed chunk, in the body of your page. This is commonly the case for embeds like

* Google Map embeds
* Calendly embeds
* YouTube embeds&#x20;

{% hint style="warning" %}
If you have CSS outside of the lazy loaded content, it will not be lazy loaded ( but will work fine once the element is lazy loaded.&#x20;

If you have scripts outside of the lazy loaded content, they may have initialization issues since they will likely perform initialization on page load- and your lazy loaded elements have not been loaded yet.&#x20;
{% endhint %}

## Getting Started <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Configure the Embed or Elements for Lazy Loading <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

* First, create your Embed or other element set the way you want it to work&#x20;
* Wrap that embed in a custom element
  * Right click, wrap in DIV
  * Right click the DIV, change to Custom Element&#x20;
* Set the custom element's tag to `template`&#x20;
* Add a custom attribute to the custom element of `wfu-lazyload`, no value

Repeat STEP 2 for any other element groups on the page that you want lazy loaded. &#x20;

## Techncial Notes&#x20;

In HTML5, a `<template>` element contains is interpreted so that that its contents become a document fragment. It is not processed as part of the DOM and is effectively invisible- much like an HTML `<!— comment -->` is.&#x20;

When you use SA5's HTML library and add the `wfu-lazyload` attribute directly to the `<template>` element, we do some magic with an intersection observer. &#x20;

When the element is scrolled into view, this triggers SA5 to reconstitute that element from the template, and replace it. &#x20;





















