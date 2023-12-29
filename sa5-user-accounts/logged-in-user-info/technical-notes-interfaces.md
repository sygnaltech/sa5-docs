---
description: Interfaces to User Accounts Data & Functionality
---

# Technical Notes - Interfaces

**These are the common capabilities we ideally want to provide an interface for, in order to make Webflow's User Accounts capability useful in site builds.** &#x20;

{% hint style="info" %}
Primarily, these capabilities need to be accessible from client-side JavaScript, however there may be other interfaces built on top of that, such as custom attributes.&#x20;
{% endhint %}

* Getting login state
* Getting current user basic info ( name, email, etc. )
* Getting user ID
* Getting current user custom fields
* Getting current user access groups
* Getting current user Meta ( additional, external data )
* Performing a scripted login ( for external system SSO )
* Performing a scripted logout

## Interfaces We've Explored

### Webflow.js Notes

Internally Webflow refers to User Accounts module as `usys`

It's fully boxed in, so even basic things like detecting login state or performing a logout are not accessible from custom code to Webflow.js interfaces.&#x20;

{% hint style="danger" %}
Status: not usable for our needs, however a lot can be learned from the webflow.js on how to perform those tasks internally.&#x20;
{% endhint %}

### GraphQL Internal Interface&#x20;

The internal interchange for usys data primarily occurs through GraphQL against site-internal endpoints that are CSRF protected.&#x20;

In theory, it's likely possible to;

* Get the user data we need
* Update user data
* Perform basic login / logout operations

Through this interface however it's not documented, and you would need to abide by the CSRF security mechanism approach.&#x20;

`/.wf_graphql/usys/apollo`

`/.wf_graphql/csrf`

{% hint style="info" %}
Note that these interfaces appear to be somewhat slow as well, or high-latency. The User Accounts screen is a good example of this, it takes a good 2 to 3 seconds frequently for the user's data to appear.
{% endhint %}

## External Interfaces

Webflow's API is robust in its ability to get and update user data, however it has rate limit and CORS issues that make it unsuitable for a direct site integration. Typically you need to clone the member database and access it from there.&#x20;

## SA5's Approach

SA5 uses only publicly-accessibly mechanisms to do its work, which comes with complexity, potential fragility, and some performance cost.

_It's not ideal, and we're looking for better options._&#x20;

## Interface Comparison

Leaving webflow.js off the list.&#x20;

|                                                         | Manual, via UX                                                   | GraphQL  | External             |
| ------------------------------------------------------- | ---------------------------------------------------------------- | -------- | -------------------- |
| Getting login state                                     | cookie                                                           | Research | -                    |
| Getting current user basic info ( name, email, etc. )   | User Account page                                                | Research | API                  |
| Getting user ID                                         | -                                                                | Research | API                  |
| Getting current user custom fields                      | User Account page                                                | Research | API                  |
| Getting current user access groups                      | Custom setup + access testing                                    | Research | API                  |
| Getting current user Meta ( additional, external data ) | Custom script to an external data provider, using AltID          | Research | API to CMS bindings? |
| Performing a scripted login ( for external system SSO ) | Login screen, however this likely isn't realistic to make secure | Research | -                    |
| Performing a scripted logout                            | Using login/logout component                                     | Research | -                    |



