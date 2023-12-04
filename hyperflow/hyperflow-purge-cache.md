---
description: Sygnal's Purge Cache
---

# Hyperflow Purge Cache

Purges the global Cloudflare cache for a site.  This works with our caching-proxy configuration and is intended to be automatically triggered by Webflow's site publish Webhook.&#x20;

R\&D&#x20;

* Individual CMS item publication and cache purging
* Plus Webflow.js etc.&#x20;





## Configuration

Learn more about [Hyperflow configuration](about/configure.md) here.

Service Name: `purge-cache`&#x20;

```json
{
  "version": 1, 
  "zoneId": "28fb418cb8b59d549384f34fe0decd07" 
}
```

