---
description: Used to redirect a custom map of URLs
---

# Hyperflow Site Redirector

## Use Cases

* You've rebuilt and _rebranded_ your site on an entirely new platform. Both the URLs _and_ **domain name** have changed.&#x20;
* You've split part of your site out into a new site, and you need clean redirection for all of those pages&#x20;
* You want to keep your SEO and backlinks, so redirecting individual pages map-style is valuable

## Technical Notes

* Redirects are all 301 redirects&#x20;
* Implemented as a worker
* Typical worker route is e.g. `*mysite.com/*` to map everything, but this is not mandatory&#x20;
* Map is stored as a JSON object in the worker's KV store
* Has a fallback for unmatched items&#x20;

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

## Configuration Notes

Configuration is stored in the KV store, under a site identifier key, which is the naked domain, e.g. `mysite.com`.&#x20;

Value includes a fallback URL for anything unknown, and a list of redirects.&#x20;

```json
{
"fallback": "https://www.mysite.com/", 
"redirects": {
    "/": "https://www.mysite.com/",
    "/privacy": "https://www.mysite.com/privacy-policy/",
    "/team/mike": "https://www.mysite.com/mike/",
    ...
  }
}
```

Within the redirects;

* Key must be unique, and is path-only.
* Value must be a full URL to redirect to;
  * You can use the same destination multiple times
  * You can redirect to any URL, thus splitting a site among multiple destinations

## Future

* Tracking stats?
* Google analytics trigger?&#x20;
* Special path handling e.g. /robots.txt and /sitemap.xml&#x20;

