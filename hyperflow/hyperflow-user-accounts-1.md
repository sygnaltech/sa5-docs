---
description: Supercharge Webflow User Accounts
---

# Hyperflow User Accounts

## Overview

ffads



<table><thead><tr><th></th><th data-hidden>+ Hyperflow</th><th data-hidden>Webflow User Accounts</th><th data-hidden>+ SA5 User Info</th></tr></thead><tbody><tr><td>GGdGGGteG</td><td>fds</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>FUTURE PLANS</td><td></td><td></td><td></td></tr><tr><td>Access-group-gated Elements</td><td></td><td></td><td></td></tr></tbody></table>



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
