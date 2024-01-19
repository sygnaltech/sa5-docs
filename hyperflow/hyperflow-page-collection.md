---
description: Serve a set of pages using an external data source for the primary content
---

# Hyperflow Page Collection

Goals;

* Identify an external headless CMS or data source&#x20;
* Retrieve a list of all docs
  * Render in sitemap
  * Support a ToC view, or collection-list style cards
* Retrieve an individual item
  * Render a page using a /\_template/x page with tagged areas
    * Support Rich text styling, etc&#x20;
* Optimized, cached&#x20;
* Detect and handle new items ( or changes / removals ) efficiently&#x20;
  * Including cache&#x20;

Systems;

* Airtable&#x20;
* Contentful
* Netlify CMS
* Ghost
* Mailchimp archive history&#x20;

Design;

* List items
  * Store in R2, to support querying lists?&#x20;
    * Filtering
    * Sorting&#x20;
* Get item
* Need an item slug
* Sitemap.xml modify
* Detect changes, purge cache item&#x20;



## Similar approach notes

[https://discourse.webflow.com/t/sync-cms-data-to-mysql/240079/10?u=memetican](https://discourse.webflow.com/t/sync-cms-data-to-mysql/240079/10?u=memetican)

[https://www.youtube.com/watch?v=7eXX4-G3sqU\&ab\_channel=MateuszNowak](https://www.youtube.com/watch?v=7eXX4-G3sqU\&ab\_channel=MateuszNowak)

[https://www.youtube.com/watch?v=bmlCCqUlzFc\&ab\_channel=BenParker](https://www.youtube.com/watch?v=bmlCCqUlzFc\&ab\_channel=BenParker)



