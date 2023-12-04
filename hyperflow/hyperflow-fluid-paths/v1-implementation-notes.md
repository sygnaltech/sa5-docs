---
description: Path Remapping implementation notes
---

# v1 Implementation Notes

4 Workers work together in this solution;&#x20;

* `cmsitem-redirect` handles all redirects from the source path to the destination path.
* `cmsitem-redirect-page` handles all rewrites from source path to the destination path, as well as canonical URL changes.
* `cmsitem-redirect-sitemap` handles the path remapping in the sitemap.xml&#x20;
* `debug-rewrite` handles all other pages, this is used for indirectly proxied sites, often in a test setup.&#x20;

All of these draw from a central configuration file stored in the `CONFIG` KV store;

The key is your base domain, followed by `:cmsitem-redirect`;

e.g. `mydomain.com:cmsitem-redirect`

The value is a JSON config chunk that all of the **cmsitem-redirect** workers use, e.g.;&#x20;

```json
{
  "version": 1,
  "origin": "https://www.mysite.com", // optional, for indirect-proxy setup
  "type": "static", 
  "map": {
    "/blog/my-article": "/path/that/i/want/to/use" 
  }
}
```

{% hint style="warning" %}
When modifying your config, it's essential to make sure your JSON is valid. We recommend you protect yourself from mistakes with these two practices;

* Always [validate your JSON](https://jsonlint.com/), before setting a new config.
* Always save your previous JSON config somewhere safe before changing it.&#x20;
{% endhint %}

Worker routes;

| Route ( example )           | Worker                   | Notes                                             |
| --------------------------- | ------------------------ | ------------------------------------------------- |
| `*mydomain.com/blog/*`      | cmsitem-redirect         | Define the routes you want to be redirected here. |
| `*mydomain.com/path/*`      | cmsitem-redirect-page    | Define the routes wher                            |
| `*mydomain.com/sitemap.xml` | cmsitem-redirect-sitemap | Define the route to your sitemap.xml.             |
| `*mydomain.com/*`           | debug-rewrite            | Only needed for indirect proxy setups.            |

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note all config work is managed by the Config class within the cmsitem-redirect worker
{% endhint %}

## Future

* Add dynamic map types
  * Support hiding of dynamic pages

## Map Types

static, stored in KV as JSON

dynamic, generated on site, on a hidden page

