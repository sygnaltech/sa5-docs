---
description: Purge the proxy cache, when your Webflow site is republished
---

# Hyperflow Purge Cache

Purges the global Cloudflare cache for a site.  This works with our caching-proxy configuration and is intended to be automatically triggered by Webflow's site publish Webhook.&#x20;

## R\&D&#x20;

* Individual CMS item publication and cache purging
* Plus Webflow.js etc.&#x20;

## Configuration

Learn more about [Hyperflow configuration](../about/configure.md) here.

### KV Store

Service Name: `purge-cache`&#x20;

```json
{
  "version": 1, 
  "zoneId": "28fb418cb8b59d549384f34fe0decd07" 
}
```

### Secrets

Requires a Cloudflare API key, which has purge cache permissions on the desired zone;&#x20;

Account > Workers & Pages > cloudflare-clear-cache > Settings > Variables

Add CLOUDFLARE\_API\_TOKEN (value) Encrypted&#x20;

## Deployment

### Worker Routes

Variable.&#x20;

We recommend a route like;

* `*DOMAIN/_purge`
* `*DOMAIN/_hf/purge-cache`
* `*hf.DOMAIN/purge-cache`

### Webflow API Webhook

Get your SiteID

[https://developers.webflow.com/reference/list-sites](https://developers.webflow.com/reference/list-sites)

Create your Webhook

[https://developers.webflow.com/reference/create-webhook](https://developers.webflow.com/reference/create-webhook)

* site\_id = your site ID, above
* triggerType: `site_publish` - Sends a [site\_publish](https://developers.webflow.com/reference/create-webhook#site\_publish) event
* url - your URL

## Future

[https://developers.cloudflare.com/workers/learning/how-the-cache-works/](https://developers.cloudflare.com/workers/learning/how-the-cache-works/)

[https://developers.cloudflare.com/workers/examples/cache-api/](https://developers.cloudflare.com/workers/examples/cache-api/)

[https://blog.cloudflare.com/introducing-the-workers-cache-api-giving-you-control-over-how-your-content-is-cached/](https://blog.cloudflare.com/introducing-the-workers-cache-api-giving-you-control-over-how-your-content-is-cached/)



