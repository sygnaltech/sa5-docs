---
description: Great for capturing referral info
---

# Track Query String Params

## Overview

Track when a page is accessed with a specific query string parameter, and store that value for later.&#x20;

_Very useful for affiliate tracking._

## Implementing

Place this in the /BODY custom code area of the page you're expecting the querystring on; or in your site-wide custom code if any page could receive it.&#x20;

{% code overflow="wrap" %}
```html
  <script>
  $(function() {
  
    // Check the URL to see if we have any referral info to track 
    if (location.search != "") {
      console.log("querystring found.");
      const urlParams = new URLSearchParams(location.search);
    
      if(urlParams.has('referrer')) {
        tracker.track("referrer", urlParams.get("referrer")); 
      }
    
    }
  });
  </script>
```
{% endcode %}

To access the referrer code, you can just retrieve it where you need it;

```javascript
window.tracker.getItem(`referrer`)
```







