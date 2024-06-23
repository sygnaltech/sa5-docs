---
description: Data-binding Current User
---

# User Info Data Source

## User Info

If you are using **Webflow User Accounts** and [SA5's User Info library](user-info-data-source.md#user-info), then SA5 constructs a User Info object whenever a user is currently logged in.

The details of that object can be data-bound.&#x20;

* `$user.name`
* `$user.email`

[user-info-data-source.md](user-info-data-source.md "mention")

[Custom user fields](../../sa5-user-accounts/logged-in-user-info/custom-user-fields.md) can also be accessed, under `$user.data.your-field-name`.

You can use this in element data-binding, with the&#x20;

`{{ $user.data.your-field-name }}`&#x20;

{% hint style="success" %}
**Shortcut.** `@` can be used as a shortcut in place of `$user.`, for example `@name` is equivalent to `$user.name`&#x20;
{% endhint %}

## Examples

wfu-bind = $user.data.link-field

\{{ $user.data.link-field \}}&#x20;

{% hint style="success" %}
This functionality is available when you are using [SA5's User Info](../../webflow-membership/current-user-info/) library.
{% endhint %}















If you are using **Webflow Memberships** and **SA5's User Info library**, then SA5 constructs a User Info object whenever a user is logged in.

The details of that object can be data-bound. e.g.;

* `$user.name` - Gets the current user's name
* `@email` - Gets the current user's email

They can be used with `wfu-bind`, or within template macros within `wfu-bind-content`, e.g.

```
Hello {{ $user.name }}! Welcome to our site.  
```

## Available DSD's

Prefix any of these with `$user.` They can be used with wfu-bind, or within templates  wfu-bind-content.&#x20;

{% hint style="success" %}
**Shortcut.** `@` can be used as a shortcut in place of `$user.`, for example `@name` is equivalent to `$user.name`&#x20;
{% endhint %}

<table><thead><tr><th width="233">$user.</th><th></th></tr></thead><tbody><tr><td><code>name</code></td><td>The user's name, as they've specified in account info</td></tr><tr><td><code>email</code></td><td>The user's email address</td></tr><tr><td><code>name_short</code></td><td>A pseudonym, composed from the email's <code>name@</code> portion</td></tr><tr><td><code>name_short_clean</code></td><td>The name_short pseudonym, without the <code>@</code></td></tr><tr><td><code>name_short_tcase</code></td><td>The <code>name_short_clean</code> pseudonym, title cased</td></tr><tr><td><code>user_id_alt</code></td><td>A unique ID for the User. This is <em>not</em> the Webflow Membership's ID, and cannot be used with Webflow's API - but is equally usable for 3rd party system integration and tracking.</td></tr><tr><td><code>data.</code><strong><code>FIELD-NAME</code></strong></td><td><p>data contains a map of the user's custom fields. Specify the field you want in place of <strong>FIELD-NAME</strong>. </p><p>These are named using Webflow's internal data field names, which is based on your individual user field slugs.</p></td></tr></tbody></table>

## Demo

{% embed url="https://webflow.com/made-in-webflow/website/current-user-info" %}

