---
description: Add structured data to your Webflow site, easily
---

# JSON-LD

{% hint style="danger" %}
**EXPERIMENTAL ALPHA** ⑤

DO NOT USE this in production code, as it may be removed. We'll see if this approach works. Testing with Google is in progress.&#x20;

**STATUS**

Testing Google response to our script generated JSON-LD.&#x20;
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

**A great website is a wonderful thing, but it's useless if no one can find it.**&#x20;

In the SEO game, structured data is a powerful tool, but there is no direct support for generating it in Webflow.&#x20;

Here we want to make that easier;

* Generate structured JSON data reliably, with zero concerns about malformed JSON
* Generate valid JSON-LD without needing to know the exact syntax, convert dates, or know constants
* Handle arrays and sub-structures with the same level of ease
* Do this all _dynamically_ so that it can be accomplished with CMS data as well.&#x20;

Working on;

* Automatic timespan conversions to ISO-8601 durations&#x20;
* Automatic date conversions to ISO-8601 dates&#x20;
* &#x20;? decode HTML from Webflow embedded fields \
  `window.sa5.decodeHTML()`&#x20;
