---
description: Here's what we're thinking...
---

# Using Access Groups for Routing ❺🧪

## Routing

{% hint style="info" %}
This is a bit of a beefier design change as we've just built a routing engine as part of the upcoming Detect lib. We'd want to separate that into its own module and likely move it into SA5 Core. As a result, we need to design this piece carefully.&#x20;
{% endhint %}

Use cases;&#x20;

* On entry into any page, e.g. `/my-page` redirect the user based on their presence / absence from an access group.&#x20;
* Modify URLs and button links depending on a user's presence / absence from an access group.&#x20;

### Zoning

This feature would probably benefit from some concept of zoning as a part of the routing architecture, so that you can broadly group pages and elements into an access zone. This would work in conjunction with Webflow's current access-group gating.&#x20;





