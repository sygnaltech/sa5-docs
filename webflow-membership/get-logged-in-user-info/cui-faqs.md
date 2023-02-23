# CUI FAQs

> ### Can CUI be used to restrict the display of "user-linked" CMS items to a specific user?&#x20;

Yes, you can, with some limitations. CUI's role here is in helping you to identify the currently logged-in user. The additional pieces you'd require are-

1. A means to connect specific CMS items to specific Users. You'd need a CMS field to store the associated User's alt-id, or another unique identifier such as their email. You can do this manually, or Logic can do this for you when creating new CMS records from a form trigger.&#x20;
2. A custom script to filter your collection list accordingly. Sygnal Attributes has an advanced filtering capability that might help with this, or you can write your own filter / sort routine.

Note though two important caveats;

{% hint style="danger" %}
**Data Security cannot be ensured.** CUI phase 3 is built entirely using client-side scripting, so there is no way to fully secure a user's linked data from access by other users. Do not use this approach for sensitive information of any kind. Note that you can use Webflow's access-group gating to protect your collection page and collection lists from people outside of that access-group, but you cannot completely secure an individual's linked CMS data from other users in that same access-group.&#x20;
{% endhint %}

{% hint style="warning" %}
**This approach does not scale well.** This approach works well for small data sets and low user counts. Since Webflow's collection lists do not support dynamic filtering, you need to load all of the user-linked data for every user, to find the current user's items. Among other things, this means working around Webflow's 100-item collection list limits.

_There are some design techniques to mitigate this,_ [_contact us_](mailto:webflow@sygnal.com) _if you'd like to consult on design & programming approaches that can support this._
{% endhint %}
