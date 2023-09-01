---
description: And what it contains
---

# The User object

As User data is loaded, your designated callback function is called, passing a User object that describes all of the data that has been collected so far.

{% hint style="info" %}
Your callback will be called multiple times, as the User data is assembled from multiple sources, asynchronously. With each call, the User object contains the data it has loaded so far, and flags to indicate which data has been loaded.
{% endhint %}

## User data loaded flags

For convenience, the User object contains metadata describing what has already been loaded. This is stored in the `user_data_loaded` sub-object, which contains 4 fields;

* `user_data_loaded.email` is true if the user's email address has been loaded
* `user_data_loaded.account_info` indicates whether basic account-info has been loaded, including the user's name and email-marketing preferences.&#x20;
* `user_data_loaded.custom_fields` is true if the user's custom fields have been loaded. These are any custom-defined fields you've defined in Webflow memberships.
* `user_data_loaded.access_groups` is true if the user's access groups have been loaded ( not yet supported ).

To use that in your callback, just check for the kind of data you're needing, before you attempt to use it. This is how to determine if e.g. `user.name` is blank, or just not loaded yet. &#x20;

## User Account Info

Includes;

* `user.name` is the User's name
* `user.email` is the User's email
* `user.accept_communications` indicates whether the user wants marketing communications
* `user.user_id_alt` is an Alternate user-unique ID that can be used for certain external integrations

Note, that Webflow's own UserID is not yet available using a client-side-only approach. If you need Webflow's UserID in order to make APi calls, you'll need some external processes, which we can [help you](https://www.sygnal.com/webflow) setup.&#x20;

## User Custom Fields

`user.data["your-field-internal-slug"]`

Important, when you first create a custom user field in Webflow, it creates a slug that can be used to uniquely identify that field. If you ever change that slug, that change will not affect the internal slug that Webflow represents the field with. This is likely due to the way Webflow has setup its internal CMS datastore.&#x20;

## User Access Groups

{% hint style="info" %}
Not yet supported ( expected Q1 )&#x20;
{% endhint %}

## User Meta Data

{% hint style="info" %}
Not yet supported, this is something we're working on.&#x20;
{% endhint %}

In this feature, you'll be able to store and retrieve arbitrary User-specific data to create a more personalized experience. This is separate from Webflow's custom fields, and can contain things like full JSON objects.&#x20;





