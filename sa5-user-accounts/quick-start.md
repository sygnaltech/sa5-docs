---
description: >-
  How to Easily Add SA5's User Info & Advanced Routing Enhancements to Your
  Webflow Memberships Site
---

# 🚀 Quick Start | SA5 User Accounts

## How to Add the Library  <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

{% hint style="warning" %}
**IMPORTANT** \
We've made some enhancements to SA5 Core in v5.5.0. \
If you are already using other SA5 Libs, please make certain to upgrade them to at least v5.5.0 as well to ensure cross-compatibility.&#x20;
{% endhint %}

[Add this script](../overview/how-to-add-custom-code.md) to the **site wide** custom code **HEAD** area of your site.&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | User Accounts --> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/css/webflow-membership.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/nocode/webflow-membership.js"></script>
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['getMembershipConfig', 
  (config) => {
    // Apply any configuration settings here
    // such as access groups 
    return config;
  }]);
</script>
```
{% endcode %}

Once you've added the library, both the [User Info](../webflow-membership/get-logged-in-user-info/) and the [Advanced Log-In & Sign-Up Flow](advanced-log-in-and-sign-up-flow.md) features are available to use.

## Current User Info Quick Start

{% hint style="success" %}
The **User Info** library can be considered as 3 feature sets.&#x20;

1. Basic user info like name, email, and opt-in is automatically accessible once the library is installed.&#x20;
2. [Custom user fields](logged-in-user-info/custom-user-fields.md) requires _special setup_ on your `/access-group` page. Make sure to read that section if you want to access that data.
3. [Access groups](logged-in-user-info/access-groups/) also requires a special setup. Make sure to read those pages if you want access to your access group data.&#x20;
{% endhint %}

**User info** works automatically behind the scenes, and gathers data _when a User first logs in_.&#x20;

To access User Info, you can use the [data-binding feature](../webflow-membership/get-logged-in-user-info/) on an element, such as a form field. Add a custom attribute of `wfu-bind` with the [DSD](https://attr.sygnal.com/webflow-membership/logged-in-user-info#accessing-user-information) you want to the element you want data-bound.&#x20;

For example, this custom attribute setting on an INPUT element will data-bind the user's email;

`wfu-bind` = `$user.email`

{% hint style="info" %}
See SA5's full list of **data source descriptors** for [User Info](https://attr.sygnal.com/webflow-membership/logged-in-user-info#accessing-user-information) here.&#x20;
{% endhint %}

If you want to use the user's info in custom code, use the [callback option](https://attr.sygnal.com/webflow-membership/logged-in-user-info#step-3-optional-add-custom-code-to-use-user-info-specially), and you get the full [user object](https://attr.sygnal.com/webflow-membership/logged-in-user-info/the-user-object).

{% hint style="warning" %}
Users who are already logged in will need to log out, and log in again in order for the library to refresh their data.&#x20;
{% endhint %}

## Log-In & Sign-Up Flow Quick Start

**We use the same library above for this module.**

However it requires configuration which is done through a configuration callback.

See here for the code to [configure log-in & sign-up flow](https://attr.sygnal.com/webflow-membership/advanced-log-in-and-sign-up-flow#step-1---add-the-library).&#x20;

Add the custom attributes for the features you need, described in each feature separately. &#x20;

## SA5 Library Developers

For SA5 library developers, use the extended syntax to support [Sygnal DevProxy](https://engine.sygnal.com/devproxy).&#x20;

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Memberships --> 
<link rel="stylesheet" 
  href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/css/webflow-membership.css"
  dev-href="http://127.0.0.1:4000/dist/css/webflow-membership.css"
  devproxy-group="sa5"
  > 
<script defer 
  src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.6.0/dist/nocode/webflow-membership.js" 
  dev-src="http://127.0.0.1:4000/dist/nocode/webflow-membership.js"
  devproxy-group="sa5"
  ></script>
```
{% endcode %}







