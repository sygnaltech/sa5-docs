---
description: About the SA5 Cache Library
---

# 🔍 About SA5's Cache Lib

This this lib is a tool for JavaScript devs to cache data for quick local access.

It provides;

* Key-value caching, where the value is any object&#x20;
* Cookies & webStorage support&#x20;
  * Expiry settings for cookies&#x20;
* A cache controller, to manage and retrieve items&#x20;

The architecture is designed to simplify access;

* Instantiate a cache controller
* Add an item, which represents a named object
  * Give it a name
  * Defined where and how it is stored
  * Give it a function that can construct the object for storage

Any time you need that data, simply request it from the cache controller. If the object is not available, it will call your function to create it, and then cache the results.

### Cache In-Validation Support

SA5 Cache supports a controller-level token, which allows you to invalidate client side caches when application changes are deployed that involve e.g. object structure changes.&#x20;

Future- complete this and add the clear cache.&#x20;

## Use Cases&#x20;

* Get JSON, CSV, RSS from an endpoint, as rarely as possible&#x20;
* Store any data you want, between user-sessions&#x20;

## Future

* Caching tied to User accounts
* Intelligent expiry determination, from the server&#x20;
