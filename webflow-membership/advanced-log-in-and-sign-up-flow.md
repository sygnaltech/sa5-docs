---
description: Redirect users anywhere you want, after login
---

# Advanced Log-In & Sign-Up Flow

{% hint style="warning" %}
**BETA** - While Memberships is in BETA, this library will track that BETA status.
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

## Terminology

{% hint style="info" %}
**Directed login.** Occurs when a user attempts to access a gated page, and is not logged in. The login page is presented, and then after a successful login, the user is directed to the originally requested page.\
**Undirected login.** Refers to a direct login, where the user clicked the login button. After the login is completed, the user can be sent to a pre-determined page, by default the home page of the website. \
**First login.** Refers to the first successful login that a user performs after sign-up.
{% endhint %}

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

Add this script to your _site-wide_ HEAD custom code.

{% code overflow="wrap" %}
```html
<!-- Membership routing -->
<script type="module">
import { WfuMembershipRouting } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.0/src/modules/webflow-membership-routing.min.js';
new WfuMembershipRouting({
    routeAfterLogin: "/u/home",
    routeAfterFirstLogin: "/u/new"
}).routeUser();
</script>
```
{% endcode %}

Configure the routing options to paths you prefer. These can be secured pages (which require login), or un-secured.

Note that if you use a secured page, you will want to make certain that all of the users you redirect there have the appropriate access group.

_See notes above._

## Additional Resources

{% embed url="https://wfu.sygnal.com/docs/webflow-membership/advanced-login-flow/" %}
