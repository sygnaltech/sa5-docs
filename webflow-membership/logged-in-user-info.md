---
description: In Webflow Memberships, get information about the current user
---

# Logged-in User Info

{% hint style="info" %}
This is phase one of a developing feature. Currently it provides access to the logged-in User's **email address** and a user-unique **alternate ID** only.
{% endhint %}

## Overview

One of the most sought-after capabilities in Webflow Memberships BETA is the ability to access information about the logged in user.

Use cases include;

* Auto-fill the logged-in user's email in a form email field, so they don't have to type it every time.
* Have a unique identifier for the user, for integrating into external systems via logic, script, or automation.

## Demonstration

{% embed url="https://webflow.com/made-in-webflow/website/get-membership-user-info" %}
Webflow cloneable demonstration
{% endembed %}

## User Information

When a user is logged in, the UserInfo object contains this information;

* `email` - The user's email address
* `name_short` - A pseudonym, composed from the email's name@ portion
* `name_short_clean` - The name\_short pseudonym, without the @
* `name_short_tcase` - The name\_short\_clean pseudonym, title cased
* `user_id_alt` - A unique ID for the User. This is _not_ the Webflow Membership's ID, and cannot be used with Webflow's API - but is equally usable for 3rd party system integration and tracking.

Any of these can be accessed directly from the User object, which is provided in the callback function as soon as it is available.

## Accessing User Information

### Data Binding

You can automatically data-bind user information to any element you like, using custom attributes.&#x20;

Simply use the `wfu-bind` custom attribute, with `$user.` and the value you want.

For example;

* To data-bind the User's email address to an input field, add the custom attribute;\
  wfu-bind = $user.email
* To data-bind the User's pseudonym to a text field, add the custom attribute;\
  `wfu-bind = $user.name_short`

{% hint style="info" %}
The $user convention is used _only_ in the `wfu-bind` custom attribute. If you want to access the user object in _JavaScript_, see the next section.&#x20;
{% endhint %}

## Accessing the User object in JavaScript <a href="#usage-notes" id="usage-notes"></a>

If you want to access the user object in code, you can do this most easily in the callback function, where the user object is already passed. Here you know the user object has been initialized and contains data, so it's the best place to access it.

{% code overflow="wrap" %}
```javascript
async function myCallback(user) {
  alert(user.email); // Show the current user's email
} 
```
{% endcode %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Drop in the script below. User information loads automatically, and asynchronously.

If a user is logged in, your callback JS function will be called, and you can do what you want with the user's available info.&#x20;

## Data Security

{% hint style="success" %}
**We protect user data.**\
****We consider _all_ user data to be _sensitive_ and it's important to treat it carefully.&#x20;
{% endhint %}

Even basic contact information should never be kept in the browser cache longer than necessary. To maximize security, we build the user information object on first request, and then dispose of it as soon as the browser tab is closed.&#x20;

In our testing, this gives the best user data security, while maximizing your site's performance- both of which are primary concerns for us and our clients.&#x20;

_Questions?_ Let us know - web@sygnal.com.&#x20;

## Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

{% hint style="warning" %}
Note that the library builds the User object at the point of login. If you install the library, and are already logged in, it will not have your User information. Make certain to log out, and then log back in to capture your user info correctly.
{% endhint %}

### STEP 1 - Add the Configuration Code <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Add this script to the custom code BODY of your site.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attr | User Info -->
<script type="module">
import { WfuUserInfo, WfuUser } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.2/src/modules/webflow-membership.js'; 
import { WfuDataBinder } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.2/src/modules/webflow-databind.min.js'; 

$(function() {
  var membership = new WfuUserInfo({
    userInfoUpdatedCallback: myCallback
  }).init(); 
});  

async function myCallback(user) {
  // Automatic data-binding using attributes
  var dataBinder = new WfuDataBinder().bind(); 
} 
</script>
```
{% endcode %}

Note the 3 parts here;

1. The library imports
2. The library setup and configuration, which happens on DOM ready&#x20;
   * Which includes your callback function name
3. Your callback function, which data binds that user info

### STEP 2 - Use the `data-bind` attribute to automatically load data into DOM elements&#x20;

The Sygnal Attributes DataBinder can automatically make use of logged-in user info as well, and data-bind it to DOM elements.

You can use this to, for example, automatically populate a form field with the logged-in User's email address.

See above for details.&#x20;

