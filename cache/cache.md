---
description: Cache retrieved data for quick access.
---

# Cache Utility Lib

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Sites are better with dynamic data, but in Webflow, that data often needs to come from outside sources and endpoints. How do you make that as performant as possible?

Sygnal's Caching library supports;

* Caching of retrieved user data in a webStorage-managed map.
* Lazy-loading. The data is not retrieved until it's first requested.
* Fully async execution. 100% entirely non-blocking.

Currently it is a simple session-level cache, meaning that the data will only be stored until the tab is closed. There is no configuration ability at present for specific cache timeouts.&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Setup involves defining your cached values, and your async functions that calculate them.

Then when you request your value, the lib takes care of checking the cache first, and then if the value has not been calculated, it calls your custom code calculation function to resolve it. &#x20;

### Setup the Cache

Place this code in your site or page level **/body** code,

{% code overflow="wrap" %}
```javascript
import { WfuCache, WfuCacheItem } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/modules/webflow-cache.min.js'; 

$(function() {
  const cache = new WfuCache({
    val: {
      myData: new WfuCacheItem({
        store: "sessionStorage", 
        name: "myData", 
        updateFnAsync: getUpdatedAsync   
      })
    }
  });
}); 
```
{% endcode %}

Define as many cached values as you want, giving them each a unique name. These are defined beneath `val`, as properties.&#x20;

### Access your Data&#x20;

When you need to retrieve that value, call `cache.getAsync()`. In the `.then()`, you can use your data how you want as soon as it's available. &#x20;

```javascript
// Some code
$(function() {
  
  // Cache setup ( code example above ) 
  // ... 
  
  // Retrieve a desired value
  // in this example, we want the value on page load, asynchronously 
  cache.getAsync("myData")
    .then(x => {
    
      // Do something with your data
      console.log(x); 
      
    }); 
      
}); 
```

### Configure your Data Retrieval functions  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

This is your custom code `async` function for calculating the value, if it's not already in the cache.&#x20;

```javascript
// Your asynchronous data-capture function 
async function getMyDataAsync() {

  // Get or create your data
  // ...
  
  return data; 
}
```

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

See above, and the feature-specific sub pages for details.

