---
description: In Webflow Memberships, get information about the current user
---

# Logged-in User Info

{% hint style="info" %}
This is phase one of a developing feature. Currently it provides access to the logged-in User's **email address** only.
{% endhint %}

## Overview

One of the most sought-after capabilities in Webflow Memberships BETA is the ability to access information about the logged in user.

Use cases include;

* Auto-fill the logged-in user's email in a form email field, so they don't have to type it every time.
* Have a unique identifier for the user, for integrating into external systems via logic, script, or automation.

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Drop in the script below. User information loads automatically, and asynchronously.

If a user is logged in, your callback JS function will be called, and you can do what you want with the user's email address.&#x20;

## Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Add this script to the custom code BODY of your site.

{% code overflow="wrap" %}
```html
<script type="module">
import { WfuUserInfo, WfuUser } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.1/src/modules/webflow-membership.js'; 

$(function() {
  var membership = new WfuUserInfo({
    userInfoUpdatedCallback: myCallback
  }).init(); 
});  

async function myCallback(user) {
  $("#email").text(user.email);   
} 
</script>
```
{% endcode %}

Note the 3 parts here;

1. The library import
2. The library setup and configuration
   * Whch includes your callback function name
3. Your callback function, which does something with that user info

In the example above. the callback function named  `myCallback` is called when the user info is available. It's passed an object, which contains the user's email as `user.email`.

You can use this to, for example, display the user's email. In this example the element with the ID of `email` will be updated to the text of the email.

If you wanted the user's email to be put in a form field, you could instead ID that form field as `email`, and use;

```javascript
$("input#email").val(user.email);
```
