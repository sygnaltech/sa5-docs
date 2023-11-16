---
description: Used to redirect a custom map of URLs
---

# Site Redirector

## Use Cases

* You've rebuilt and _rebranded_ your site on an entirely new platform. Both the URLs _and_ **domain name** have changed.&#x20;
* You want to keep your SEO and backlinks, so redirecting individual pages map-style is valuable

## Technical Notes

* Implemented as a worker
* Typical worker route is e.g. `*mysite.com/*` to map everything, but this is not mandatory&#x20;
* Map is stored as a JSON object in the worker's KV store
* Has a fallback for unmatched items&#x20;

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

