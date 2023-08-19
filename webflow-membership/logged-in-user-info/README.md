---
description: Get the details of the currently logged-in user In Webflow Memberships
---

# Logged-In User Info ❺

{% hint style="info" %}
Questions? Comments? Suggestions? Join the new [Sygnal Attributes group](https://www.facebook.com/groups/sygnal) on Facebook.
{% endhint %}

{% hint style="success" %}
This is phase three of a developing feature. Currently it provides access to the logged-in User's **name**, **email address, custom user fields** and a user-unique **alternate ID**.
{% endhint %}

## What's New in v5?

* All internal upgraded to TypeScript, and integrated into our SA5 libraries
* Added support for accessing user info from the User Account page itself
* Added dynamic updates. Save updated User Account info and the User Info object is rebuilt &#x20;
* Simpler setup and configuration. Data-binding is enabled by default. &#x20;

## Overview

_NOTE: because User Info is a complex module in Sygnal Attributes, documentation is split in to several pages. Make sure to note the sub-pages in the left nav, below this one._&#x20;

One of the most sought-after capabilities in **Webflow Memberships BETA** is the ability to access information about the _currently logged in user_.

Use cases include;

* Personalize your site by displaying the user's name&#x20;
* Auto-fill the logged-in user's email in a form email field, so they don't have to type it every time.
* Have a unique identifier for the user, for integrating into external systems via logic, script, or automation.

Features;

* Get the current user's email
* Get the current user's name ( _released in v4.4_ )
* Get a unique, User-specific alternate ID which can be used for system integrations&#x20;
* Get [custom user fields](custom-user-fields.md) ( _released in v4.5_ )
* Get access groups ( _coming soon_ )
* Heavily optimized, with a multi-layered, asynchronous load approach to assembling the user data. &#x20;

Limitations;&#x20;

* ~~Changes to user information, e.g. changing the user's name on the Account Info page won't be reflected in the user object until the next login~~&#x20;
* Currently this library depends on the User Account screen in order to access user data and compose the user object. You can do what you want with your User Account page however those user fields must exist in the page ( even hidden ) in order for this library to work.  &#x20;
* For custom user fields, the File field type is unsupported for now&#x20;
* Currently the Webflow UserID is not easily available. See here for [solutions](getting-webflows-userid.md), if you need it for external system integrations with Webflow's API.&#x20;
* Read-only. The library is designed to read user data, but not to update it.&#x20;

## Demonstration

Here's a new cloneable, specific for SA5-

{% embed url="https://webflow.com/made-in-webflow/website/current-user-info" %}

## Accessing User Information

When a user is logged in, the User Info is constructed and the object contains this information;

* `name` - The user's name, as they've specified in account info
* `email` - The user's email address
* `name_short` - A pseudonym, composed from the email's name@ portion
* `name_short_clean` - The name\_short pseudonym, without the @
* `name_short_tcase` - The name\_short\_clean pseudonym, title cased
* `user_id_alt` - A unique ID for the User. This is _not_ the Webflow Membership's ID, and cannot be used with Webflow's API - but is equally usable for 3rd party system integration and tracking.
* `data` - A map of the user's custom fields. These are named using Webflow's internal data field names, which is based on your individual user field slugs.

Any of these can be accessed directly from the User object, which is provided in the callback function as soon as it is available.

### Data Binding

You can automatically data-bind user information to any element you like, using custom attributes.&#x20;

Simply use the `wfu-bind` custom attribute, with `$user.` and the value you want.

For example;

* To data-bind the User's email address to an input field, add the custom attribute;\
  `wfu-bind = $user.email`
* To data-bind the User's name to a text field, add the custom attribute;\
  `wfu-bind = $user.name`
* To data-bind a custom user field, named City ( slug `city` ), add the custom attribute;\
  `wfu-bind = $user.data.city`

{% hint style="info" %}
The `$user` convention is used _only_ in the `wfu-bind` custom attribute. If you want to access the user object in _JavaScript_, see the next section.&#x20;
{% endhint %}

### Accessing the User object in JavaScript <a href="#usage-notes" id="usage-notes"></a>

If you want to access the user object in code, you can do this most easily in the callback function, where the user object is already passed. Here you know the user object has been initialized and contains data, so it's the best place to access it.

{% code overflow="wrap" %}
```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['userInfoChanged', 
  (user) => {
    console.log("USER INFO CHANGED", user); 
  }]); 
</script> 
```
{% endcode %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Drop in the script below. User information loads automatically, and asynchronously.

If a user is logged in, any data-bound fields will be populated automatically. Your callback JS function will be also called, and you can do what you want with the user's available info in script.&#x20;

{% hint style="danger" %}
**IMPORTANT:** This library depends on Webflow's User Account  page ( at`/user-account` ) as the mechanism to access and load User data.&#x20;

All basic user info fields MUST exist, including Name, Email, and the Opt-in checkbox. These fields may be hidden, but they MUST exist in the page. Custom User Data fields must also exist if you want them, see [Custom User Fields](custom-user-fields.md) for details.&#x20;

_If you have removed any fields or need to add custom fields, you can add these in using the right side designer menu when the form is selected on the User Account page._&#x20;
{% endhint %}

## Data Security

{% hint style="success" %}
**We protect user data.**\
We consider _all_ user data to be _sensitive_ and it's important to treat it carefully.&#x20;
{% endhint %}

Even basic contact information should never be kept in the browser cache longer than necessary. To maximize security, we build the user information object on first request, and then dispose of it as soon as the browser tab is closed.&#x20;

In our testing, this gives the best user data security, while maximizing your site's performance- both of which are primary concerns for us and our clients.&#x20;

_Questions?_ Let us know - **attr@sygnal.com**.&#x20;

### Personally Identifiable Information ( PII )

In Webflow Memberships, the only unique, persistent identifier we have access to client-side is the user's email address, which can not be changed.&#x20;

However as this absolutely qualifies as PII, we do not want to use this as an identifier for integrating with other external systems.&#x20;

To provide for this, we manufacture an Alt User ID as a one-way hash of the user's email. Use this when you need to "attach" data in an external system.&#x20;

## Future <a href="#getting-started-locode" id="getting-started-locode"></a>

* Callback on login
  * Login on external system, retrieve data
* Callback on first login
  * Setup account on external system
* Inactivity logout timer settings&#x20;
* Login activity logging&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

{% hint style="danger" %}
**IMPORTANT:** If you are upgrading from SA4, it's important to note that the code is now completely different and much simpler.&#x20;

* It's now in the site-wide before HEAD rather than the before BODY code area
* You no longer include the data-binding library
* You do not need to initialize the data-binding library
* The script is no longer `type=module`, and it needs `defer`&#x20;

Don't blindly copy and paste URLs, you're much better to copy the code block here, and replace the old one directly. If you are using the custom callback feature, it is redesign as well, see STEP 3 for that new code.&#x20;
{% endhint %}

### STEP 1 - Add the Configuration Code <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Use the `wfu-bind` attribute to automatically load data into DOM elements&#x20;

SA5's Data-Binding feature can access logged-in user info as well, and you can easily data-bind it to text elements, titles, spans, form INPUT elements, and more. You can use this to, for example, automatically populate a form field with the logged-in User's email address.

See above for details.&#x20;

### STEP 3 - ( OPTIONAL ) Add custom code to use User Info specially

Place this also in the **before HEAD** of your site, just after the library code above. If it's page-specific, you can instead place it on the **before HEAD** of specific pages if you like.&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Memberships | User Info Changed Event -->
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['userInfoChanged', 
  (user) => {
    console.log("USER INFO CHANGED", user); 
  }]); 
</script> 
```
{% endcode %}

{% hint style="warning" %}
You should be able to have multiple instances of this code block, for example site-wide, and page specific, at the same time - however this has not been production tested. Test it carefully if you want to experiment with this approach.&#x20;
{% endhint %}

