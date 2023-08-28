---
description: Expand Webflow's login/logout button to a surrounding container
---

# Expand Login Button ❺

## Overview <a href="#expand-the-login-button-with-a-container" id="expand-the-login-button-with-a-container"></a>

In Webflow's Memberships BETA \[ Jan-2023 ] the login / logout button offers limited styling and sizing options. This presents a problem if you want to position it in your nav menu alongside other items, or display an adjacent icon.

This attribute allows the surrounding container to extend the login/logout element's area.

## Use Cases

* Make your login button include an icon, or additional text
* Create a larger area
* Wrap it in a menu style container

## Demonstration

See the main [Sygnal website](https://www.sygnal.com) for an example ( top right ).

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### Create a DIV, with the `wfu-login-button` attribute <a href="#create-a-div-with-the-wfu-login-button-attribute" id="create-a-div-with-the-wfu-login-button-attribute"></a>

* Add the `wfu-login-button` custom attribute (no value needed) to identify the clickable “expanded login button” element.
* Include whatever else you want in that button DIV
* Style it however you like

### Place the Webflow Log-In / Log-Out element inside of it <a href="#place-the-webflow-log-in--log-out-button-inside-of-it" id="place-the-webflow-log-in--log-out-button-inside-of-it"></a>

This is important, it’s the inner element that the expanded button will perform the log-in / log-out action through.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this code to the **site-wide** **before-HEAD** area of your site.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Memberships --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.18/dist/css/webflow-membership.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.18/dist/nocode/webflow-membership.min.js"></script>
<script>
```
{% endcode %}

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.



\
