---
description: Hide or show any element based on login state
---

# Conditional Element Display

{% hint style="info" %}
As of mid Dec 2022, Webflow has added an initial version of login-state element gating, however there are some incompatability issues with components. This solution will remain available while those issues are being worked out.
{% endhint %}

## Overview

This feature allows you to hide/show elements based on the logged-in / logged-out state of the current user.

You can currently;

* Show elements only when logged-in
* Show elements only when logged-out

{% hint style="danger" %}
**SECURITY NOTE:** This library only affects the visibility of the target elements, not their existence. Do not use this for secure information, as it cannot prevent users from accessing that content if they view source or disable scripts.
{% endhint %}

## Future Plans

As of Jan-2023 here's the general feature map for Webflow's Membership access gating. Where known, Webflow's current or planned direction is shown.&#x20;

Notes are given where SA is considering development.&#x20;

|                      | Login/Logout                                                   | Access-Group                                       | User-Specific                                      |
| -------------------- | -------------------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| Static Pages         | Webflow-native                                                 | Webflow-native                                     | Webflow, but only for the /access-group page       |
| CMS Collection Pages | Webflow-native                                                 | Webflow-native                                     | ( no use case )                                    |
| Elements             | <p>Webflow ( unstable, secure )<br>SA ( stable, insecure )</p> | Webflow under development, suggested 1Q23          | ( no use case )                                    |
| CMS Collection Items | <p>( no use case )<br>Covered by -></p>                        | <p>NEEDED<br>Webflow - unknown<br>SA - planned</p> | <p>NEEDED<br>Webflow - unknown<br>SA - planned</p> |

* Element gating
  * Add access-group-level gating
* Collection Item gating
  * Add access-group-level gating
  * Add User-level gating&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### `wfu-show-logged-in` attribute <a href="#wfu-show-logged-in-attribute" id="wfu-show-logged-in-attribute"></a>

Add the `wfu-show-logged-in` custom attribute (no value needed) when you want an element to only appear to logged-in users.

### `wfu-hide-logged-in` attribute <a href="#wfu-hide-logged-in-attribute" id="wfu-hide-logged-in-attribute"></a>

Add the `wfu-hide-logged-in` custom attribute (no value needed) when you want an element to only appear to NON-logged-in users.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/dist/css/webflow-membership.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/src/nocode/webflow-membership.js"></script>
```
{% endcode %}

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

## Additional Resources

{% embed url="https://wfu.sygnal.com/docs/webflow-membership/conditional-element-display/" %}
See original docs.
{% endembed %}
