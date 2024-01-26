---
description: How to get Webflow's UserID for the currently logged in user.
---

# Webflow's UserID

Webflow does not expose the UserID in an accessible way. This is a core limitation as it means you cannot capture information relating to the current user, and connect it to the user through Webflow's API - a key component of application builds.

## Custom Data Workaround

If you use an automation platform like Make or Zapier, one possibility is to;

* Create a custom user data field called user-id
* Build an automation on the new-user-created Webflow API webhook
* When this happens, grab the UserID, and then turn around and update your custom user data field on the same user record
* Use SA5 Custom User Fields setup to access that data&#x20;

{% hint style="success" %}
Unlike CMS Item ID's Webflow's UserID's _do not change_ even on a backup restore.
{% endhint %}

## Hyperflow

Sygnal has developed a new framework called Hyperflow which fully replaces the SA5 User Info library with a server-side solution that;

* Requires zero site setup&#x20;
* Instantly retrieves the current user info with no delay
* Can access the full user record
  * Name & Email
  * UserID
  * Access Groups
  * Custom User Fields
  * Utility Settings
* Can use User data to do;
  * Personalization
  * App Builds&#x20;
  * Paywalls&#x20;
