---
description: SA5 Memberships Quick Start
---

# Quick Start

{% hint style="success" %}
All of SA5's Membership features are now consolidated into a single library, so you only need one library include.&#x20;
{% endhint %}

## How to Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Add this script to the **site wide** custom code **before HEAD** area of your site.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Memberships --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.32/dist/css/webflow-membership.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.32/dist/nocode/webflow-membership.js"></script>
```
{% endcode %}

Once you've added the library, both the User Info and the Advanced Log-In & Sign-Up Flow features are available to use.

## User Info Quick Start

**User info** works automatically behind the scenes, and gathers data _when a User first loggs in_.&#x20;

{% hint style="warning" %}
Users who are already logged in will need to log out, and log in again in order for the library to collect their data.&#x20;
{% endhint %}

To access User Info, you can use the data-binding feature on element, such as a form field. Add a custom attribute of `wfu-bind` with the [DSD](https://attr.sygnal.com/webflow-membership/logged-in-user-info#accessing-user-information) you want to the element you want data-bound.&#x20;

For example, this custom attribute setting on an INPUT element will data-bind the user's email;

`wfu-bind` = `$user.email`

{% hint style="info" %}
See SA5's full list of **data source descriptors** for [User Info](https://attr.sygnal.com/webflow-membership/logged-in-user-info#accessing-user-information) here.&#x20;
{% endhint %}

If you want to use the user's info in custom code, use the [callback option](https://attr.sygnal.com/webflow-membership/logged-in-user-info#step-3-optional-add-custom-code-to-use-user-info-specially), and you get the full [user object](https://attr.sygnal.com/webflow-membership/logged-in-user-info/the-user-object).

### Log-In & Sign-Up Flow Quick Start

**We use the same library above for this module.**

However it requires configuration which is done through a configuration callback.

See here for the code to [configure log-in & sign-up flow](https://attr.sygnal.com/webflow-membership/advanced-log-in-and-sign-up-flow#step-1---add-the-library).&#x20;











