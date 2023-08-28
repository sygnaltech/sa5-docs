---
description: Data Source Types
---

# Data Source Types 📝

{% hint style="warning" %}
**DOCUMENTATION IN-PROGRESS.** Use this as notes.&#x20;
{% endhint %}

## User Info

If you are using **Webflow Memberships** and [SA5's User Info library](data-sources.md#user-info), then SA5 constructs a User Info object whenever a user is currently logged in.

The details of that object can be data-bound.&#x20;

* `$user.name`
* `$user.email`

[user-info-data-source.md](user-info-data-source.md "mention")

[Custom user fields](../../sa5-memberships/logged-in-user-info/custom-user-fields.md) can also be accessed, under `$user.data.your-field-name`.

You can use this in element data-binding, with the&#x20;

\{{ $user.data.your-field-name \}}&#x20;

Descriptors beginning with $user &#x20;

{% hint style="success" %}
**Shortcut.** `@` can be used as a shortcut in place of `$user.`, for example `@name` is equivalent to `$user.name`&#x20;
{% endhint %}



wfu-bind = $user.data.link-field

\{{ $user.data.link-field \}}&#x20;

{% hint style="success" %}
This functionality is available when you are using the User Info library.
{% endhint %}

## Query String

$query

{% hint style="success" %}
**Shortcut.** `?` can be used as a shortcut in place of `$query.`, for example `?name` is equivalent to `$query.name`&#x20;
{% endhint %}

## Database

$db prefix indicates a data source type of Database.&#x20;

Database descriptors follow&#x20;

{% hint style="success" %}
**Shortcut.** `+` can be used as a shortcut in place of `$db.`, for example `+name` is equivalent to `$db.name`  &#x20;
{% endhint %}





Or within





How Data binding works

Tagging \[wfu-bind]

\[wfu-bind-content]

&#x20;



