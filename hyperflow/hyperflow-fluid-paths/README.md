---
description: Give every page on your site the path it deserves
---

# Hyperflow Fluid Paths

{% hint style="success" %}
Sygnal gets so many requests for this, we've built a special expertise and internal toolset that enables us to deliver this functionality on Webflow-hosted sites.

Check our our [service page](https://www.sygnal.com/services/webflow-fluid-paths) for details on our **Webflow Fluid Paths** offering.&#x20;
{% endhint %}

SEO specialists have long been frustrated by Webflow's inability to handle custom paths for each page, including CMS pages.&#x20;

Paths are an important indication of the semantic context of a page, such as;

* `/recipes/dinner/main-course/venison`
* `/services/cosmetic/eyes/eyelashes`
* `/course/learning-javascript/getting-started/part-1`

Static pages can be pathed like this using folders and pages, but CMS collection pages require a more rigid path formation of `../collection-slug/item-slug`.&#x20;

This makes things such as hierarchies `/school/course/chapter/lesson`, or `/restaurants/illinois/chicago/pizza` problematic.&#x20;

{% hint style="success" %}
We'll just have none of that, _thank you_.
{% endhint %}

## What is _Path Remapping_?

Sygnal uses the term **remapping** to describe a process by which we;

* Serve any page on your site, under any path that you choose
* Fix the canonical URL, accordingly
* Fix the sitemap, accordingly
* Redirect the actual page to your preferred path

_Welcome to remapping. Isn't it awesome?_&#x20;

Advantages;

* No special linking needed. Your natural Webflow CMS links work perfectly fine with Sygnal's remapping approach.&#x20;
* No SEO loss. Have your old pages already been indexed?  That's great!  Zero SEO loss.&#x20;
* No backlink traffic loss. They'll just get redirected, too.&#x20;

## Important Concepts

### Direct v. Indirect Proxy

Sygnal's path remapping capability is engineered to work on both a directly proxied site, and an indirectly proxied site.&#x20;

* A **directly proxied site** is one where the request origin to the proxy and the underlying origin share the same domain.&#x20;
* An **indirectly proxied site** is one where they differ, and this is particularly useful for testing or special SEO cases such as a localized site, or one which is geo-gated with varying content and prices.&#x20;

### Remapping & Maps

* The **physical path** describes the location of the page on your Webflow site, as Webflow publishes it, e.g. /blog/article.&#x20;
* The **virtual path** describes the new virtual path that the page will be delivered under, and SEO'd under.

{% hint style="warning" %}
It's important to consider the site design you want. A poorly-planned map could have circular routes that cannot be resolved.&#x20;

It's also important to consider how this will play into worker-routes, since they designate the correct worker to run at different parts of your site.
{% endhint %}

### Map Types

* **Static maps** are a simple map of physical paths to virtual paths. &#x20;
* **Dynamic maps** are the same, but are generated dynamically and typically managed within the CMS itself.&#x20;
* **Algorithmic maps** work on match-based mapping and are custom-designed for each site.&#x20;

## Administration Notes

### Webflow Editor

* Untested on fluid paths
* Can edit on webflow.io

Future;&#x20;

* Special mode for FP shutdown possible when in editor mode

