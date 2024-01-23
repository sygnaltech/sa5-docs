# Page Change Detection

## Goals

* Make it easy for the browser to determine when content has changed on the page

Approach

* Provide some cached, refreshing, queryable mechanic to determine;
  * Webflow page republished
    * Impacted by CMS API issued changes
  * Other external things

## # Technology

## Datasources

* Current page
* Other specific pages on the same site

Changed-since mechanic, provide ID / hash / timestamp, get a yes/no result&#x20;

### Page Change Detection

Query every N sec from a single source, headers only

Look for changes in marker fields&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

[https://discourse.webflow.com/t/div-auto-refresh-without-site-reloading-each-2-minutes/267573/2?u=memetican](https://discourse.webflow.com/t/div-auto-refresh-without-site-reloading-each-2-minutes/267573/2?u=memetican)
