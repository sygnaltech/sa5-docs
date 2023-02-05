# Custom User Fields

## User Custom Fields

Webflow Memberships allows for custom fields as part of a User's account. These custom fields can be managed through;

* The Designer user manager
* The API
* During Sign Up, if you add those fields to the UI
* On the User Account screen, if you add those fields to the UI

CUI PHASE 3 provides access to these fields both through Sygnal Attributes data-binding and directly through JavaScript. All fields will be part of the `WfuUser` object, as a map under the `data` element.

{% hint style="warning" %}
In order for CUI to access these fields, they MUST be defined on your User Account page. You can hide them if you like, but they must exist.&#x20;
{% endhint %}

Custom fields are named using Webflow's generated internal field names for each. Typically this process is the same as slug-generation, e.g. a field named `Home Address` would be slugged and internally named as `home-address`.&#x20;

{% hint style="info" %}
The Webflow CMS and User data storage systems generate internal field names based on the generated slug, however there are situations where the slug and the internal field name will mismatch. For example, if you rename your slug field, Webflow will keep the original name as its internal field name.&#x20;
{% endhint %}

{% hint style="success" %}
e.g. `Full Name` would be accessible in the user object as `user.data["full-name"]`
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
