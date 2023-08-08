---
description: Data Source Types
---

# Data Source Types

{% hint style="warning" %}
**DOCUMENTATION IN-PROGRESS.** Use this as notes.&#x20;
{% endhint %}

## User Info

If you are using **Webflow Memberships** and **SA5's User Info library**, then SA5 constructs a User Info object whenever a user is currently logged in.

The details of that object can be data-bound.&#x20;

$user.name

$user.email

[user-info-data-source.md](user-info-data-source.md "mention")



If you have custom user fields, these will also appear

, they a



Descriptors beginning with $user &#x20;

{% hint style="success" %}
**Shortcut.** `@` can be used as a shortcut in place of `$user.`, for example `@name` is equivalent to `$user.name`&#x20;
{% endhint %}



wfu-bind = $user.data.link-field

\{{ $user.data.link-field \}}&#x20;

{% hint style="success" %}
This functionality is available when you are using the User Info library.
{% endhint %}

## Query

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



