---
description: Cache retrieved data for quick access.
---

# Data Caching ❺

{% hint style="warning" %}
This is an **advanced feature** which requires an understanding of JavaScript development.&#x20;
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Sites are better with dynamic data, but as Webflow does not provide for server-side development, that data often needs to come from outside sources and endpoints. How do you make that as efficient as possible?

You combine techniques like caching, asynchronous loading, callbacks, and lazy loading to request, store, and access that data.&#x20;

Sygnal's Caching library supports;

* Caching of retrieved user data in a webStorage-managed map.
* Lazy-loading. The data is not retrieved until it's first requested.
* Fully async execution. 100% entirely non-blocking.
* Defining your cached values, and the async functions that calculate or determine them.

Then when you request your value, the lib takes care of checking the cache first. If the value has not been calculated or retrieved, it calls your custom code calculation function to resolve it. &#x20;

## Use Cases

* Retrieve data from another page on your site
* Retrieve data from a page on another site
* Retrieve data from an API
* Perform a time-consuming calculation

## Limitations

Currently it is a simple session-level cache, meaning that the data will only be stored until the tab is closed. There is no configuration ability at present for specific cache timeouts.&#x20;

## Future Plans

* Multiple cached items with a single cache handler.&#x20;
* Cache choice and lifetime configuration, using sessionStorage, localStorage, or cookies
* Support for eager or lazy loading, by cached data item ( all will be asynchronous ).
* Triggering events on load, to allow other processes to happen&#x20;
* Handle retrieval failure cases.&#x20;

Possible support for specialized, source-aware and content-aware data adapters;

* Retrieving data from Google Docs, Sheets, or AirTable&#x20;
* Retrieving specific element content from another webpage
* JSON API calls&#x20;

We're also considering approaches on how the adapter configurations and data-binding could potentially support simple NO-CODE situations such as value-binding. &#x20;

## What's New in Cache v5? <a href="#usage-notes" id="usage-notes"></a>

* No more JS dependencies
* Async library loading initiates in the page head&#x20;
* Integrated debugging log&#x20;

## Usage Notes v5 <a href="#usage-notes" id="usage-notes"></a>

Setup involves three parts;

1. Setting up the cache, and defining your cached values
2. A custom function to calculate your defined values, which is called when the uncached data needs to be created.
3. Cache retrieval, which retrieves the data either from the cache (if available) for generates it (if needed)  &#x20;

Setup involves defining your cached values, and the async functions that calculate or determine them.

Then when you request your value, the lib takes care of checking the cache first. If the value has not been calculated or retrieved, it calls your custom code calculation function to resolve it. &#x20;

{% hint style="danger" %}
**ALPHA PRE-RELEASE.** Not advised for production use. Use v4 for production sites.&#x20;
{% endhint %}

### Setup the Cache

Place this code in your site or page level **/head** code,

{% code overflow="wrap" %}
```javascript
<!-- Sygnal Attributes 5 | Cache -->
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.1-alpha.2/dist/webflow-cache.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.1-alpha.2/dist/webflow-cache/webflow-cache-item.min.js"></script>

<script>
const init = () => { 

  const cache = new WfuCache({
    val: {
      myData: new WfuCacheItem({
        name: "myData", 
        store: "sessionStorage", 
        updateFnAsync: getMyDataAsync   
      })
    }
  });

}

document.addEventListener("DOMContentLoaded", init)
</script>

```
{% endcode %}

Define as many cached values as you want, giving them each a unique name. These are defined beneath `val`, as properties.&#x20;

### Access your Data&#x20;

When you need to retrieve that value, call `cache.getAsync()`. In the `.then()`, utilize your data. That code will be executed as soon as the data is available. This will be effectively immediate if the data is already cached. &#x20;

```javascript
// Retrieve a desired value
cache.getAsync("myData")
  .then(x => {
   
    // Do something with your data
    console.log("Retrieved", x); 
          
  }); 
```

### Configure your Data Retrieval functions  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

This is your custom code `async` function for determining the value, if it's not already in the cache.&#x20;

```javascript
// Your asynchronous data-capture function 
async function getMyDataAsync() {

  // Get or create your data 
  var data = "HERE'S MY DATA"; 
  
  return data; 
}
```



