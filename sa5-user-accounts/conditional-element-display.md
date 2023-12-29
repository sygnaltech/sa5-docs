---
description: Hide or show any element in Webflow, based on login state
---

# Conditional Element Display ❺

{% hint style="info" %}
In Dec 2022, Webflow has added an initial version of login-state element gating, however there are some incompatibility issues with components, and certain utility pages. This solution will remain available while those issues are being worked out.
{% endhint %}

## Overview

This feature allows you to hide/show elements based on the logged-in / logged-out state of the current user.

You can currently;

* Show elements only when logged-in
* Show elements only when logged-out

{% hint style="danger" %}
**SECURITY NOTE:** This attributes-based approach only affects the _visibility_ of the target elements, _not their existence_. Do not use this for secure information, as it cannot prevent users from accessing that content if they view source or disable scripts.\
\
_Webflow's solution handles conditional visibility securely server-side, so you will want to utilize Webflow's native CV feature as soon as you are able to._
{% endhint %}

## Future Plans

As of Jan-2023 here's the general feature map for Webflow's Membership access gating. Where known, Webflow's current or planned direction is shown.&#x20;

Notes are given where the Sygnal Attributes ( SA ) project is considering development.&#x20;

<table><thead><tr><th width="171"> </th><th width="172">Login/Logout</th><th>Access-Group</th><th>User-Specific</th></tr></thead><tbody><tr><td>Static Pages</td><td>Webflow <br>( <mark style="color:green;">released</mark> )</td><td>Webflow<br>( <mark style="color:green;">released</mark> )</td><td>( <mark style="color:yellow;">no use case</mark> )<br>Excepting the /user-account page.</td></tr><tr><td>CMS Collection Pages ( <a data-footnote-ref href="#user-content-fn-1">all or none</a> )</td><td>Webflow<br>( <mark style="color:green;">released</mark> )</td><td>Webflow<br>( <mark style="color:green;">released</mark> )</td><td>( <mark style="color:yellow;">no use case</mark> )</td></tr><tr><td>Elements</td><td>Webflow<br>( <mark style="color:orange;">partial support</mark> )<br>SA ( stable, insecure )</td><td>Webflow<br>under development, planned 1Q23 </td><td>( <mark style="color:yellow;">no use case</mark> )</td></tr><tr><td>CMS Collection Items</td><td>( <mark style="color:yellow;">no use case</mark> )<br>Covered by -></td><td><a data-footnote-ref href="#user-content-fn-2"><mark style="color:red;">NEEDED</mark></a><br>Webflow - unknown<br>SA - planned 1Q23</td><td><a data-footnote-ref href="#user-content-fn-3"><mark style="color:red;">NEEDED</mark></a><br>Webflow - unknown<br>SA - considering</td></tr></tbody></table>

Current SA priorities;&#x20;

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

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.



[^1]: CMS CP gating refers to the page entirely, not gating of individual collection items.

[^2]: Needed to mix paid, free & levelled content such as courses, blog articles.&#x20;

[^3]: Needed for app-like capability, dashboards, invoice histories, order histories, client deliverables, and other user-specific content delivery.
