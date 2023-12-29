---
description: How to setup and access Webflow's Custom User Data fields from WFU
---

# Custom User Fields

## What are Custom Fields?

Webflow Memberships allows for [custom fields](https://university.webflow.com/lesson/user-pages-overview#custom-fields) as part of a User's account. These custom fields can be managed through;

* Through the Designer user manager
* Through the Webflow API
* During Sign Up, if you add those fields to the UI
* On the User Account `/user-account` screen, if you add those fields to the UI

We provide access to these fields both through Sygnal Attributes data-binding and directly through JavaScript. All fields are part of the `Sa5User` object, as a map under the `data` element.

## Important Setup Notes

_Very important things_ you need to know when setting this up...&#x20;

{% hint style="info" %}
Any Custom User Fields that you want to access MUST exist on your [User Account page](https://university.webflow.com/lesson/user-pages-overview#user-account-page). To add them, you can simply add those fields to the page from the right-side configurator.
{% endhint %}

{% hint style="info" %}
After adding these Custom User Fields and setting up WFU's User Info lib properly, your users MUST log out and then log back in again in order for the newly-accessible custom user field data to load. See the [User object Lifecycle](the-user-object/the-user-object-lifecycle.md) for details on how user data loads.&#x20;
{% endhint %}

{% hint style="info" %}
If you do not want your users to see these fields on the User Account screen, you can wrap them in a DIV and hide them using `display: none` on the style tab. Do _not_ try to hide them using Webflow's new visibility hidden feature on the _settings_ tab, as Webflow will not render the elements at all, and the data will not be accessible to WFU for loading.
{% endhint %}

## How to Access Custom User Fields

The SA5 user object creates an array of custom fields under `user.data`.&#x20;

### Accessing via Data-Binding

You can use SA5's data-binding features with a custom attribute of `wfu-bind` and a value of `$user.data.FIELD-NAME` where the field name is your custom field name.&#x20;

e.g. `$user.data.birthdate`

### Accessing via Script

You can access your custom fields directly in script on the user object, e.g.;

```html
<!-- Sygnal Attributes 5 | Memberships | User Info Changed Event -->
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['userInfoChanged', 
  (user) => {
    // Check to verify the custom field data is loaded
    if(user.user_data_loaded.custom_fields) {
    
        // Do something with your data 
        console.log(user.data["full-name"]);

    	return;
    }
  }]); 
</script>
```

### How Custom User Fields are Named

Custom fields are named using Webflow's generated internal field names for each. Typically this process is the same as slug-generation, e.g. a custom user field named `Home Address` would be slugged and internally named as `home-address`.&#x20;

However, there are exceptions to this rule, described below. If you're not certain, it's best to view your `/user-account` page in browser devtools, and identify the field name that Webflow has assigned to your custom user fields. &#x20;

{% hint style="warning" %}
The Webflow CMS and User data storage systems generate internal field names based on the generated slug, however there are situations where the slug and the internal field name will mismatch. For example, if you rename your slug field, Webflow will keep the original name as its internal field name.&#x20;
{% endhint %}

## What Custom Field Types are Supported by SA5?

As of Feb-2023, these are Webflow's current field types, and our current plans;&#x20;

| Field Type  | Notes                                      | Planned Support                                                                                                          |
| ----------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| Plain Text  | max 256 chars                              | <mark style="color:green;">Yes.</mark>                                                                                   |
| Email       |                                            | <mark style="color:green;">Yes.</mark>                                                                                   |
| Link        |                                            | <mark style="color:green;">Yes.</mark>                                                                                   |
| Number      | Can be defined with a min, max, and step   | <mark style="color:green;">Yes.</mark> Delivered as a string, so that a blank value is identifiable as "" rather than 0. |
| Option      | Pre-defined options that you choose        | <mark style="color:green;">Yes.</mark> Delivered as the option value.                                                    |
| Switch      | Boolean                                    | <mark style="color:green;">Yes.</mark>                                                                                   |
| File        | An uploaded file, such as a profile photo  | <mark style="color:red;">Not in v3.</mark> Looking into how to retrieve the uploaded filename in the future.             |

