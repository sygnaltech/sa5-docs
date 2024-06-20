---
description: Add cool animated numeric countups to your site with just an attribute.
---

# CountUp Animated Numbers

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This library provides a NOCODE way to add animated number countups in Webflow.

## Credits

This is just a wrapper library that adds nocode abilities using two top-notch existing libraries;

* Countup - [https://github.com/inorganik/CountUp.js](https://github.com/inorganik/CountUp.js)
* Waypoints - [http://imakewebthings.com/waypoints/guides/getting-started/](http://imakewebthings.com/waypoints/guides/getting-started/)

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

There are two basic use-cases.&#x20;

### Self-triggering countups

Place the custom attribute `wfu-countup` on any text element that contains a numeric value, and the library will automatically begin a count up from 0 just as that item scrolls into view.&#x20;

### Group-triggered countups

In certain cases, you'll have a series of items that you want to all start and finish together.&#x20;

To do that,&#x20;

* Apply the custom attribute `wfu-countup` on any number-containing text element, and assign it a group name e.g. `group1`
* Then, on an element or container that begins slightly higher on the page, place a custom attribute of `wfu-countup-trigger` = `group1` using the same name.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

This library does not require configuration, so we've taken a NOCODE approach to its design.

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Add this JS reference to the BODY of your site or page.\
This is the base configuration.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.4.0/src/nocode/webflow-countup.min.js"></script>

```
{% endcode %}

### STEP 2 - Apply the custom attributes and code pieces based on your configuration needs <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above, and the feature-specific sub pages for details.
