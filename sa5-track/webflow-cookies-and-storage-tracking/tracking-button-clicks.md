---
description: Track when a user clicks a specific button on your site
---

# Tracking Button Clicks

## Overview

Track when the user clicks a button, and use that to show/hide elements on other pages throughout your site.

## Implementing

Place this code inside the BODY custom code area of your page or site.

If the button is only on one page, it's best to put it on that page only, to prevent ID conflicts with elements on other pages.

If the button is on all pages, such as a nav or footer button, it's best to place it in the site-wide BODY custom code, under site settings.&#x20;

{% code overflow="wrap" %}
```html

<script>
// Handle button tracking 
$("#button").click(function() {
  window.tracker.track("button-clicked");
  updateTracked();
}); 
</script>
```
{% endcode %}
