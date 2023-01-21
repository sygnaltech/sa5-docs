---
description: Track when a user visits a specific URL on your site
---

# Tracking Page Visits

## Overview

You can track when someone visits a specific page on your site, and use that to affect other pages.&#x20;

Suppose a user clicks a special marketing link, and has landed on a special hidden landing page for that offer. You can track that they've been to that page, and then throughout your site, you can have some special reminders appear about the offer.&#x20;

Suppose a user completed sign-up to your great new class, and saw the thank you page. You can remember that and now, they're no longer bothered with ads and CTAs through your site telling them to enroll.&#x20;

## Implementing

{% hint style="info" %}
There are two ways to implement this; this is the one we currently recommend most.
{% endhint %}

On the special page you're tracking visits to, add this code to the page's BODY custom code area;&#x20;

{% code overflow="wrap" %}
```javascript
<script>
$(function() {
  window.tracker.track("my-page-visited"); 
});
</script>
```
{% endcode %}

When the page loads, it will simply track your specified label.

You can change `my-page-visited` to any unique label you like. We recommend using your page's slug as part of the label for easy identification.

For example, if your page is at `/about`, you might use `page-about` as your tracking label to make it easy to remember.

### Alternative Approach \[ DEPRECATED ]

This approach was originally recommended because it keeps your code central in your site-wide BODY, however it has some limitations.

Most importantly, password protected pages in Webflow are likely to register as being visited even if the user _does not log in_, due to the way Webflow handles that login screen. Webflow Membership pages login differently, and will work fine. &#x20;

{% code overflow="wrap" %}
```javascript
  // Check the URL for specific paths
  // that we want to track, e.g. a hidden marketing page URL 
  switch(window.location.pathname) {
    case "/special-offer": // Your Path goes here
      window.tracker.track("page-special-offer");
      break;
  }
```
{% endcode %}
