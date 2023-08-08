---
description: Techniques & Approaches
---

# Getting Webflow's UserID

Webflow's **UserID** is not accessible through any of the client-side techniques we use to build the SA5 User Info object. According to Webflow's Memberships project manager, this won't be added any time soon.&#x20;

**Why would you want it?**

If you have any external systems that will be integrating with the API, they need the UserID in order to make calls to the Memberships API.&#x20;

Also, if Webflow ever adds the ability to change a user's email address then the UserID becomes the only persistent User identifier. &#x20;

## Solutions

The only viable solution we've found is to trigger off of a new account create webhook, and then store it.&#x20;

If you store it in a custom User Data field, then you will be able to access it using SA5 User Info.&#x20;

{% hint style="success" %}
Fortunately, unlike CMS ID's, the UserID seems to persist across site backup-restores, so you can be confident your UserID is reliably persistent. &#x20;
{% endhint %}

## Technical Notes

Aka. other things we've tried...

For the technically minded among you, here are some things we've tried...&#x20;

### Webflow.js

The Webflow.js library is undocumented, but is the main client-side interface to the Memberships system. So far, we've been unable to find any means to access the UserID there.&#x20;

We've even gone so far as to search all of browser memory for the current UserID with no matches, so it appears the UserID is never known client-side even to Webflow.&#x20;

### Cookie

The UserID does exist in the `wf_sid` cookie once a user is logged in, it's wrapped in a JSON token which can be decoded and parsed without any special cryptographic keys.&#x20;

However this cookie is an `http-only` cookie which means that javascript in the browser cannot access the cookie.&#x20;

### Webflow API lookup

Using the user's email, we could theoretically look up the user record and obtain the ID, however this does not work client side;&#x20;

* The Webflow API is CORS-blocked, such that it cannot be accessed from client side scripts.&#x20;
* The User API does not have a 'lookup by email' function. &#x20;

### Proxy

We've done some experiments with a proxy to determine whether a request can be passed through the proxy and then access the http-only cookie serverside. However this runs into a host of issues regarding the cookies, domain names, same-origin headers.&#x20;

It's even difficult to perform the login through a proxy, much less make that work with a separately domained live site. &#x20;
