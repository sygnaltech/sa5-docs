---
description: Help us BETA test!
---

# BETA testing

{% hint style="info" %}
**2023-Aug-05**

Are you using SA5's User Info module? Help us improve the framework by sharing your use cases, feature requests, or any questions or problems you encounter.

\-> [Join the Discourse group now](https://sygnal-attr.discourse.group/).
{% endhint %}

## Testing Assistance Needed

Our team is busy building. If you're using this module, please share any issues you encounter, or any testing you're able to complete.

### Browser testing

The SA5 BETA has been determined stable with no identified bugs on Chrome, but has not been tested on other mainstream browsers, in particular;

* Safari
* Edge
* Firefox

### Test with 1st Login on Admin-initiated User Invites

SA5 BETA includes some new capabilities to reliably construct the User Info object during Webflow's sign-up onboarding process during the _auto-login_ that Webflow performs when the email verification link is clicked.&#x20;

_This has been tested well with new member self-sign-ups._&#x20;

It has not been tested with site-owner-initiated invites, however, which has a slightly different onboarding flow. We've designed for this, but been unable to test this scenario as Webflow has recently taken the user-invite functionality offline ( we assume for retooling ).&#x20;

## Known Issues

{% hint style="success" %}
No issues identified yet.
{% endhint %}

## Testing Process

Verify user object is created successfully on every login, even with repeated login-logouts of different users in the same system.&#x20;

Verify data binding picks up the information immediately.&#x20;

General responsiveness should be good. The user object updates recurringly as it updates with new information about the user, so you should ideally get initial information quickly \[ email ] and then additional information \[ name, etc ] as loading continues.

Verify user object creates successfully during onboarding during first login. When the email verification link is clicked, Webflow does an automatic login for the user that bypasses the normal login flow. In V2, the user object should still create properly here. &#x20;

