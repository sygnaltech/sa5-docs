---
description: Add a Smart Search to Your 404 Pages.
---

# 404 Search ❺

Did you delete a blog article, or rename the slug and forget to redirect it?&#x20;

404's happen- but they don't need to be the end of the road.&#x20;

Help your visitors get where their going by automatically populating Webflow's search component with the URL path keywords they were originally trying to reach?

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Goals

* Smart routing and redirect for special paths
* Smart search feature, populate from url&#x20;
* Logging

[https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics](https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics)

[https://developers.google.com/search/docs/crawling-indexing/http-network-errors#http-status-codes](https://developers.google.com/search/docs/crawling-indexing/http-network-errors#http-status-codes)

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

{% hint style="info" %}
This feature is using WFU's v5 new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;

You can use both the v4 and v5 libraries simultaneously to get the full feature set during migration.
{% endhint %}

Add this to the **before HEAD** custom code area of your **404 page** only.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | 404 -->
<script defer
src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.34/dist/nocode/webflow-404.js"
></script> 
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;

### STEP 2 - Add Custom Attributes

Add a [Webflow Search](https://university.webflow.com/lesson/site-search) element, and on the input field add a custom attribute of `[wfu-404-search]`. No value is needed.

