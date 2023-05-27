---
description: Important rules on when the User object is created and destroyed
---

# The User object Lifecycle

The WFU User Info object is expensive to build, as it requires gathering user data from a number of different sources in your Webflow site - some of which are very slow to respond to queries.

To minimize the impact of this, the User object is created once per "usage session", and cached for maximum performance.

At the same time, we do not want to persist personal user data on the system unnecessarily between sessions, so the User object is destroyed when it is no longer needed.&#x20;

## User object Lifecycle

The User object is **created**...

1. When you log in
2. When you access the site, and already have a valid login session

The User object is **destroyed**...

1. When you log out
2. When you close the browser tab

## Developer Tip

If you make significant changes that will impact the content of your User object, for example adding a new custom User Data field, or modifying your Access Groups, you will want to recreate the User object to load that new data.

Simply tell Users to log out and log in again to access their new content, or to close their browser tabs and re-open them.&#x20;

{% hint style="info" %}
During development, it is equally important for you to force the User object to recreate when you e.g. add a new Custom User Data field to the User Account page.
{% endhint %}



