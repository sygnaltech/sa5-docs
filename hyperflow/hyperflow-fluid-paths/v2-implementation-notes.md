# v2 Implementation Notes

## Future

* Add localization base path support?&#x20;

## Technical Configuration Notes



### Remapping Paths

`CONFIG`

`mysite.com:remap`

```json
{
  "version": 1,
  "origin": "https://www.mysite.com",
  "type": "static", 
  "map": {
    "/": "/",
    "/about": "/about/1"
  }
}
```

* Version: 1
* Origin: optional, used if the actual site is separate from the current site proxied
* Map types
* Config version converters?&#x20;

All mapped paths are stored in the key-value store;&#x20;

{% hint style="info" %}
Keys are the base domain, with no protocol, and no `www.` prefix, e.g. `mydomain.com`
{% endhint %}

For example;

* Key: `sygnal.com/orig-path/`
* Value: `/dest-path/`&#x20;

### Automatically Remapping Paths

We also have situationally-specific strategies for remapping paths internally, using a special field in your CMS collection. This allows you to define the remapping path per-item more simply from the CMS itself, but requires additional programming.&#x20;

### Technical notes

The rewriting, canonical, and sitemap changes are actually quite straightforward. The complex part is the generally URL map itself.

If your site doesn't change often or your path permutations are very predictable, you can hardcode that map into your reverse proxy code. But if you need it to be more dynamic, you'll need a way to build and admin your map.

One way is to use a separate CMS collection to store that map, and you publish it on a hidden page like **/\_map**. Your reverse proxy can then parse it into data, cache it, and use it for path resolution. My SEO clients prefer this approach because it lets them use entirely arbitrary paths.

If you want to build an actual automatically self-managed hierarchy, that's actually more complex since you need to extract all of those ref & multiref relationships and construct that map dynamically. Due to its programming complexity, this is not recommended for most projects, I've only done this for universities which tend to have large and complexly organized sites.

Keep in mind you will also want to correct your canonicals and your sitemap.
