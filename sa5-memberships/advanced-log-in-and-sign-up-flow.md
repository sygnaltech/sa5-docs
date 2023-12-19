---
description: Redirect users anywhere you want, after login
---

# Advanced Log-In & Sign-Up Flow ❺

{% hint style="warning" %}
**LOCALIZATION** - If you are using Webflow's new localization features, there may be impacts with this library. Most notably, selecting an alternate locale, and then logging in likely will not detect and preserve that alternate locale. Let us know in the forum if you encounter any conflicts, we'd like to see sites operating with this configuration. &#x20;
{% endhint %}

{% hint style="info" %}
**UPDATE Jan-2023** - Webflow has enhanced the Login Redirect Fallback setting on login forms. See the [update video](advanced-log-in-and-sign-up-flow.md#important-update) below for details.
{% endhint %}

## Overview

The sign-up and log-in flow in Memberships BETA currently has a couple of limitations.&#x20;

As of Jan-2023, you can;

* Perform a [directed login](advanced-log-in-and-sign-up-flow.md#terminology), which redirects to the originally requested resource after login.
* Redirect an [undirected login](advanced-log-in-and-sign-up-flow.md#terminology) to any static page on your site, including utility pages like the **User Accounts** page.

There are a few things you _might_ want to do that you cannot do natively yet;

* Redirect an [undirected login](advanced-log-in-and-sign-up-flow.md#terminology) to a Collection Item page.&#x20;
* Redirect an [undirected login](advanced-log-in-and-sign-up-flow.md#terminology) to a page, including query string params.&#x20;
* Handle a user's [first login](advanced-log-in-and-sign-up-flow.md#terminology) after sign-up specially, by redirecting them to a New User page.

{% hint style="info" %}
**Directed login.** Occurs when a user attempts to access a gated page, and is not logged in. The login page is presented, and then after a successful login, the user is directed to the originally requested page.\
**Undirected login.** Refers to a direct login, where the user clicked the login button. After the login is completed, the user can be sent to a pre-determined page, by default the home page of the website. \
**First login.** Refers to the first successful login that a user performs after sign-up.
{% endhint %}

## Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/memberships-login-routing" %}
Demonstration & cloneable
{% endembed %}

## Important Update

**Jan-2023** - Webflow has enhanced the Login Redirect Fallback feature.

{% embed url="https://www.loom.com/share/385d052603ee4a44bf2f907b8ad7ef91" %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

This library is not attributes based, but rather has routing configuration options in its setup.

There are currently two configuration options;

* `routeAfterLogin` - specifies an optional path to redirect users after an explicit login.
  * Recognizes a special path of `.`, which means, return to the current page.
* `routeAfterFirstLogin` - specifies an optional path for the first time a user logs in.

## Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Add your Configuration Callback

Add this script right after the library in your _site-wide_ **before HEAD** custom code.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Memberships | Config -->
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['getMembershipRoutingConfig', 
  (config) => {
    config.routeAfterFirstLogin = '/u/new';
    config.routeAfterLogin = '/u/home';
    return config;
  }]); 
</script>
```
{% endcode %}

Configure the routing options to paths you prefer. In the example above, we've used `/u/new` and `/u/home`. Replace these with the URLs you want. If you do not want a special first-login route, you can remove that line.&#x20;

{% hint style="info" %}
These paths can be to secured pages (which require login), or un-secured. If they are to secured pages, make certain they are accessible to all users who login- this means auto-assigning an access group to newly registered users.  &#x20;
{% endhint %}

_See notes above._

