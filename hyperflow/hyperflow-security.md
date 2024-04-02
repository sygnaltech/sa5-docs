---
description: Provide password or user-account protection to specific pages
---

# Hyperflow Security

{% hint style="info" %}
CONCEPTUAL PHASE
{% endhint %}

## Goals

Auth approaches;

* Password-based
  * Site-wide `/*`
  * Page-specific `/page1`&#x20;
  * Page-range group specific `/group/*`
* User-account-based
  * Webflow user accounts
  * Netlify Identity
  * Memberstack?&#x20;
  * Other&#x20;
* Access-group-based

Designer-managed login page





## Notes&#x20;

Password protection is a template-level setting, so if you want item-level passwords you’d need to build a custom solution based on your needs. There are two main factors;

* The level of security you need, i.e. is it just a simple marketing deterrent ( low security ), or do you need actual content protection ( medium security ), or content security with individual user-access grants that you can revoke ( higher security )?
* Whether you have one password that gives access to all of your secured pages, or whether there are individual passwords for each.

The low security approaches are basically to toss a password into a field in the CMS, and then when it exists, you display a full-screen dialog over top of your page content until the password is entered. It’s low security because your content is still there, and it can be thwarted with developer tools, and is dependent on JS being enabled in the browser.

Medium security approaches are to actually gate content access so that only those with the password can access it. This requires a reverse proxy, or else storing the content somewhere else and fetching it after authorization.

The higher security approaches involve individual user accounts and a registration process. Similar issues as the medium-level approach. You can use Webflow User Accounts but you’d need a reverse proxy infrastructure to gate individual CMS item pages.
