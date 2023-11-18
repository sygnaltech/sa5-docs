---
description: Give every CMS item the SEO path it deserves
---

# Path Remapping

## Remapping

SEO specialists have long been frustrated by Webflow's inability to handle custom paths for each page, including CMS pages.&#x20;

Paths are an important indication of the semantic contact of a page, such as;

* `/recipes/dinner/main-course/venison`
* `/services/cosmetic/eyes/eyelashes`
* `/course/learning-javascript/getting-started/part-1`

Webflow cannot easily handle these without a lot of compromise and administrative complexity.&#x20;

{% hint style="success" %}
We'll just have none of that, _thank you_.
{% endhint %}

What is Remapping?

Sygnal uses the term remapping to describe a process by which we;

* Serve any page on your site, under any path that you decide
* Fix the canonical URL, accordingly
* Fix the sitemap, accordingly
* Redirect the actual page to your preferred path

Welcome to remapping. Isn't it awesome?&#x20;

Advantages;

* No special linking needed. Your natural Webflow CMS links work perfectly fine with Sygnal's remapping approach.&#x20;
* No SEO loss. Have your old pages already been indexed?  That's great!  Zero SEO loss.&#x20;
* No backlink traffic loss. They'll just get redirected, too.&#x20;

## Technical Configuration Notes

### Remapping Paths

All mapped paths are stored in the key-value store;&#x20;

{% hint style="info" %}
Keys are the base domain, with no protocol, and no `www.` prefix, e.g. `mydomain.com`
{% endhint %}

For example;

* Key: `sygnal.com/orig-path/`
* Value: `/dest-path/`&#x20;

### Automatically Remapping Paths

We also have situationally-specific strategies for remapping paths internally, using a special field in your CMS collection. This allows you to define the remapping path per-item more simply from the CMS itself, but require additional programming.&#x20;



