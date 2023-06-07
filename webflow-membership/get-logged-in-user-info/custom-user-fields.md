---
description: How to setup and access Webflow's Custom User Data fields from WFU
---

# Custom User Fields

## User Custom Fields

Webflow Memberships allows for [custom fields](https://university.webflow.com/lesson/user-pages-overview#custom-fields) as part of a User's account. These custom fields can be managed through;

* Through the Designer user manager
* Through the Webflow API
* During Sign Up, if you add those fields to the UI
* On the User Account screen, if you add those fields to the UI

We provide access to these fields both through Sygnal Attributes data-binding and directly through JavaScript. All fields are part of the `WfuUser` object, as a map under the `data` element.

## Important Setup Notes

_Very important things_ you need to know when setting this up...&#x20;

{% hint style="info" %}
Any Custom User Fields that you want to access MUST exist on your [User Account page](https://university.webflow.com/lesson/user-pages-overview#user-account-page). To add them, you can simply add those fields to the page from the right-side configurator.
{% endhint %}

{% hint style="info" %}
After adding these Custom User Fields and setting up WFU's User Info lib properly, your users MUST log out and then log back in again in order for the newly-accessible custom user field data to load. See the [User object Lifecycle](the-user-object-lifecycle.md) for details on how user data loads.&#x20;
{% endhint %}

{% hint style="info" %}
If you do not want your users to see these fields on the User Account screen, you can wrap them in a DIV and hide them using `display: none` on the style tab. Do _not_ try to hide them using Webflow's new visibility feature on the _settings_ tab, as Webflow will not render the elements at all, and the data will not be accessible to WFU for loading.
{% endhint %}

## Access Custom User Fields

Custom fields are named using Webflow's generated internal field names for each. Typically this process is the same as slug-generation, e.g. a field named `Home Address` would be slugged and internally named as `home-address`.&#x20;

{% hint style="success" %}
e.g. `Full Name` would _typically_ be accessible in the user object as `user.data["full-name"]`
{% endhint %}

{% hint style="info" %}
The Webflow CMS and User data storage systems generate internal field names based on the generated slug, however there are situations where the slug and the internal field name will mismatch. For example, if you rename your slug field, Webflow will keep the original name as its internal field name.&#x20;
{% endhint %}

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

## Tools for user custom fields

{% hint style="info" %}
We're working on instructions and/or tools to assist you in identifying Webflow's custom user-field names, which can get confusing if you rename them.&#x20;
{% endhint %}
