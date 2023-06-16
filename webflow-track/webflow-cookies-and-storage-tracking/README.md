---
description: >-
  Track referrals, user info and more to improve your site's user experience
  (UX)
---

# Webflow Cookies & Storage tracking

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Tracking and storage mechanisms like Cookes & Web Storage are central part of what makes the Internet work today. But all of these things require code to access.

This library makes it easier by;

* Abstracting cookies & web storage, so you can switch painlessly
* Providing a simple script API for those who want to add basic logic functionality in their Webflow site scripts
* Providing NO CODE connections for features like conditional visibility&#x20;

## Demonstration <a href="#usage-notes" id="usage-notes"></a>

{% embed url="https://user-tracking.webflow.io/" %}
Webflow Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Generally, the tracker will be "installed" to the window object, so that it is globally-accessible. In the code examples here, you can see that in the `a` convention.  &#x20;

### Track something

To track a general event, such as when the user visited a page or clicked a button, you can just give it a memorable name, and track it;

```javascript
window.tracker.track("my-item");
```

Now, the label `my-item` is tracked, and will affect things like conditional visibility of elements that are connected to it. See below.

If you want to track a specific piece of information with that label, you can add it as well. This underlies the mechanisms for tracking query string params and checkbox states, which you'll see in the subsections.  &#x20;

```javascript
window.tracker.track("my-item", "data");
```

### Un-Track something

To remove something from tracking;

```javascript
window.tracker.untrack("my-item");
```

### Conditional Visibility <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Sygnal Attributes has a NOCODE conditional visibility feature in the tracking library as well.&#x20;

If you want an element to be visible only when a the label `my-item` is tracked, add this custom attribute to that element;

```html
wfu-show-tracked="my-item"
```

Likewise, if you want an element to be hidden when a particular label is tracked, add this custom attribute to that element;

```html
wfu-hide-tracked="my-item"
```

## Getting Started ( LOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

This library has configuration options, so we've taken a LOCODE approach to its design.

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/dist/css/webflow-track.min.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.\
This is the base configuration.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/modules/webflow-track.min.js"></script>

<script type="module">

import { WfuTracker } from 
  'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/modules/webflow-track.min.js';

// On page load 
$(function() {
    
  // Create the tracker type you want
  // 'cookies' is default. 'localStorage' and 'sessionStorage' are options 
  window.tracker = new WfuTracker({
    "method": "cookies", 
  });
  
  // Update the UI to reflect current tracking state
  // especially controls, and conditional visibility 
  updateTracked();
  
});

// Refresh UI to show what is being tracked
// with the current tracker type 
function updateTracked() {

  // Show anything marked to show on tracked state
  $("[wfu-show-tracked]").each(function () {
    if(window.tracker.isTracked($(this).attr("wfu-show-tracked")))
      $(this).show();
    else
      $(this).hide();
  });
  
  // Hide anything marked to hide on tracked state
  $("[wfu-hide-tracked]").each(function () {
    if(!window.tracker.isTracked($(this).attr("wfu-hide-tracked")))
      $(this).show();
    else
      $(this).hide();
  });
    
  // PLACE ADDITIONAL CODE HERE
  // When directed to in the feature-specific instructions
    
}

</script>
```
{% endcode %}

### STEP 2 - Apply the custom attributes and code pieces based on your configuration needs <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above, and the feature-specific sub pages for details.
