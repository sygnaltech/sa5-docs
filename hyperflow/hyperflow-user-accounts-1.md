---
description: Supercharge Webflow User Accounts
---

# Hyperflow User Accounts

## Overview

Webflow's User Accounts is a very limited system.&#x20;

* No ability to connect it to external billing platforms.&#x20;
* No ability to dynamically migrate live user accounts from another platform.
* No access-group ga
* Stale data, based on user account settings&#x20;
* No ability to immediately revoke access&#x20;
* No ability to change email address&#x20;

### Why use Webflow?

If we're going to extend Webflow's User Accounts infrastructure substantially, why bother using Webflow User Accounts at all? &#x20;

It's certainly possible to replace the authentication, user data storage, admin, API, etc, however Webflow already provides;

* A designer-integrated admin capability
* A basic set of screens and processes for sign-up, log-in, and account management
* An integrated model for \[ page level ] access-group gating
* An API for accessing all of the User data&#x20;
* A subscription billing mechanism, as an option&#x20;

All built into the Webflow platform as part of the base subscription. We can use those parts and fix;

* User data access within the site, for personalization
* Element-level gating by access-group&#x20;
* Improved security&#x20;
* Mechanics like partial-content previews&#x20;
* Possibly improved billing options, and integrations with other systems for the access-group determination.&#x20;

### Access User Info in Site

Access to user info is crucial to your ability to deliver a personalized experience.&#x20;

<table><thead><tr><th></th><th>+ Hyperflow</th><th>+ SA5 User Info</th><th>Webflow User Accounts</th><th data-hidden>+ Hyperflow</th><th data-hidden>Webflow User Accounts</th><th data-hidden>+ SA5 User Info</th></tr></thead><tbody><tr><td>UserID</td><td>Yes, current</td><td>No</td><td>No</td><td></td><td></td><td></td></tr><tr><td>Name</td><td>Yes, current</td><td>Yes, as of last login</td><td>No</td><td></td><td></td><td></td></tr><tr><td>Email</td><td>Yes, current</td><td>Yes, as of last login</td><td>No</td><td></td><td></td><td></td></tr><tr><td>Custom User Data</td><td>Yes, current</td><td>Yes, as of last login</td><td>No</td><td></td><td></td><td></td></tr><tr><td>Account is active right now? *</td><td>Yes, current</td><td>No</td><td>No. Whether the account is active or exists is only tested at login.</td><td></td><td></td><td></td></tr><tr><td>Access Groups</td><td>Yes, current</td><td>Yes, as of last login</td><td>No, but page-level gating can utilize Access Groups to gate content</td><td></td><td></td><td></td></tr></tbody></table>



### Platform Capabilities



<table><thead><tr><th></th><th>+ Hyperflow</th><th>+ SA5 User Info</th><th>Webflow User Accounts</th><th data-hidden>+ Hyperflow</th><th data-hidden>Webflow User Accounts</th><th data-hidden>+ SA5 User Info</th></tr></thead><tbody><tr><td>Access-group-gated Elements</td><td>Trivial, and secure</td><td>Possible, but access groups are from last login, and uses custom code. Also not secure as the elements are removed by client-side script.</td><td>No</td><td></td><td></td><td></td></tr><tr><td>Change a User's access groups immediately, e.g. over the phone</td><td>Yes</td><td>Partial. User would have to log out, and back in again.</td><td>Partial. User would have to log out, and back in again.</td><td></td><td></td><td></td></tr><tr><td>Have access group changes take effect immediately.</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr><tr><td>Immediate lock-out</td><td>Yes</td><td>No</td><td>No</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>



{% hint style="info" %}
In Webflow, the login token and access groups are issued at the point of login. Once login is complete, that token lasts for about 3 days, and may even be auto-refreshed as the user visits.&#x20;

The impact of this is essential to understand;

* Adding or revoking access groups does not take effect until the next login
* Deleting the account does not prevent access, or automatically log the user out
* &#x20;A subscription expiry does not necessarily(?) revoke access&#x20;
{% endhint %}

## Future

* Custom user data storage
* 3rd party integrations
  * e.g. Mailchimp list sync
* Likes & favorites
* Variable refresh models
  * On-demand refresh for sensitive access updates
  * Timed refresh
    * Page-specific rules?&#x20;
      * META data
* Auto-logout&#x20;
*

Possible;

* Voting and asset-based likes tracking
* CMS field updates&#x20;
* External subscription options via Stripe&#x20;
  * Easy ability establish and cancel subscriptions
  * Easy ability to change subscriptions \[ and pro-rate ]
  * Immediate awareness of what subscription is active, and tie to access groups&#x20;
  * Platforms
    * Stripe
    * BMAC
    * Patreon
* Change email address process;
  * Create a new invite, and verify it
  * Migrate existing account data
    * Including billing
  * Remove old account&#x20;
* Dynamic access groups
  * Certain access groups can be assigned through external systems like Stripe & BMAC.&#x20;
    * Or synced by API &#x20;



## Notes

* Obtain Webflow UserID
* Main sync copy in KV store of each User record
* Retrieve the current record on request

Two modes;

* Retrieve as an endpoint
* Retrieve automatically into the page as an SA5 user object
* SA5 User Info lib would pick that up automatically and use it instead of the typical retrievals&#x20;

Isolate by site?&#x20;

subdomain v. subdir &#x20;

\*sygnal.com/\_hf/users/user\_account\_added



## Stored Data

```
{
   "id":"63bd3d6897494b2c3cfa95c4",
   "invitedOn":null,
   "createdOn":"2023-01-10T10:43:12.936Z",
   "lastUpdated":"2023-12-28T07:47:27.893Z",
   "isEmailVerified":true,
   "lastLogin":"2023-12-27T23:29:33.668Z",
   "data":{
      "country":"NZ",
      "city":"Auckland",
      "webflow-micro-consulting":true,
      "webflow-mc-account":"https://docs.google.com/spreadsheets/d/1oEw1pRr0z0OtE8ie6dRlNz_ra9yyVCx_g-TluINdL_8/edit#gid=0",
      "wmc-map-url":"https://www.mindomo.com/mindmap/1570d4e846d64268826d8d26fd919898",
      "bio":"Standard <input type=\"text\"> form fields are designed for single-line text input and do not support multi-line text. To allow for multi-line text input, you should use a <textarea> element, which is specifically designed for this purpose.  However, if for",
      "name":"Michael",
      "email":"mike@sygnal.com",
      "accept-communications":false,
      "accept-privacy":true
   },
   "status":"verified",
   "accessGroups":[
      {
         "slug":"client",
         "type":"admin"
      },
      {
         "slug":"admin",
         "type":"admin"
      }
   ]
}
```







Sygnal

"59b8d49f7fdf9700017d780f",

```typescript
/_hf/users/user_account_added
/_hf/users/user_account_updated
/_hf/users/user_account_deleted
/_hf/users/current_user
```

## Setup

1. Install the Worker&#x20;
2. Setup the KV Store
3. Setup your domain Worker Routes

e.g. `*sygnal.com/_hf/users/*` -> `webflow-user-accounts`&#x20;

4. Get your Webflow SiteID&#x20;

e.g. `59b8d49f7fdf9700017d780f`

[https://developers.webflow.com/reference/list-sites](https://developers.webflow.com/reference/list-sites)

5. Create Webflow Webhooks

Can e setup within your site dashboard;

[https://webflow.com/dashboard/sites/sygnal/integrations](https://webflow.com/dashboard/sites/sygnal/integrations)

**TEST v2**&#x20;

**user\_account\_added**

```
https://www.sygnal.com/_hf/users/user_account_added
```

**user\_account\_updated**

```
https://www.sygnal.com/_hf/users/user_account_updated
```

**user\_account\_deleted**

```
https://www.sygnal.com/_hf/users/user_account_deleted
```

5.

## Sync Process

List Users

Update User on each, with no payload

```
https://www.sygnal.com/_hf/users/list_users
```

```
https://www.sygnal.com/_hf/users/update_user
```

## Config

[https://webflow.com/dashboard/sites/sygnal/integrations](https://webflow.com/dashboard/sites/sygnal/integrations)

Generate API token

User Accounts - Read-only



```
// Some code
{
message: "OAuthForbidden: You are missing the following scopes - 'users:read'",
code: "missing_scopes",
externalReference: null,
details: [ ]
}
```



```
KV CONFIG
sygnal.com:user-accounts
...
59b8d49f7fdf9700017d780f

{ "version": 1, "siteId": "...", "token": "..." }
```
