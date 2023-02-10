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

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### Setup the Cache

In your site or page level **/body** code,

```javascript
$(function() {
  const cache = new WfuCache({
    val: {
      updated: new WfuCacheItem({
        store: "sessionStorage", 
        name: "updated", 
        updateFnAsync: getUpdatedAsync   
      })
    }
  });
}); 
```

### Access your Data&#x20;

In certain cases, you'll have a series of items that you want to all start and finish together.&#x20;

```javascript
// Some code
$(function() {
  
  // Cache setup ( above ) 
  // ... 
  
  // Retrieve a desired value
  const u = cache.getAsync("myData")
    .then(x => {
    
      // Do something with your data
      console.log(x); 
      
    }); 
      
}); 
```

### Configure your Data Retrieval functions  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

```javascript
// Your asynchronous data-capture function 
async function getMyDataAsync() {

  // Get or create your data
  // ...
  
  return data; 
}
```



This library does not require configuration, so we've taken a NOCODE approach to its design.

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

See above, and the feature-specific sub pages for details.
