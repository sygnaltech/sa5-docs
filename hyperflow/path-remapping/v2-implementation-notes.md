# v2 Implementation Notes

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
