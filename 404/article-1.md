---
description: Add a Smart Search to Your 404 Pages.
---

# 404 Search ❺

**Whoops. Did you delete a blog article, or rename the slug and forget to redirect it?**&#x20;

_404's happen_ - but they don't need to be the end of the road. Help your visitors get where their going by automatically populating Webflow's search component with the URL path keywords they were originally trying to reach?

## Demonstration <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

This URL points to a Webflow site, for which the page does not exist;

```
https://www.coachmike.live/blog/anger-management-for-couples
```

Click the link to see the 404 lib auto-populate a Webflow site search input.&#x20;

{% embed url="https://www.coachmike.live/blog/anger-management-for-couples" %}

## Usage Notes <a href="#getting-started-nocode" id="getting-started-nocode"></a>

<details>

<summary>I want this Search input to auto-populate from the current path</summary>

Add a [Webflow Search](https://university.webflow.com/lesson/site-search) element, and on the input field add a custom attribute of `wfu-404-search`. No value is needed.

</details>

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start-or-sa5-404.md).&#x20;

### STEP 2 - Add `wfu-404-search` to your Search input

Add a [Webflow Search](https://university.webflow.com/lesson/site-search) element, and on the input field add a custom attribute of `wfu-404-search`. No value is needed.

