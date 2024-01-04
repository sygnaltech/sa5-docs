---
description: Store site-wide content so that it can be easily accessed and integrated
---

# Global Data Source 🧪

{% hint style="warning" %}
Not yet available for production use.
{% endhint %}

{% hint style="success" %}
Use `$global` to access.&#x20;
{% endhint %}

## Use Cases

* Hours of operation
* Copyright notice
* Primary phone
* Primary email

## Design

Store an arbitrary global JSON object in site wide head, e.g.;

```html
<script>
{
  "copyright": "Copyright 2024, Sygnal",
  "contact": {
    "email": "info@sygnal.com" 
  } 
}
</script>
```

Overrides. Allow another object at the page head level that can override specific field values.&#x20;

Reference values as needed, e.g.;

* `$global.copyright`&#x20;
* `$global.contact.email`&#x20;

## Future Plans

Integration with Sygnal Hyperflow, and the ability to source data externally from an external KV store. API to allow for updates externally.&#x20;

Potentially support multiple named global objects, with a `default` one.&#x20;

Support for [Sygnal HSON](../article/).&#x20;

Possible support for special types or type-binding;

* Plain-text
* Numeric
* Boolean ( conditional visibility )
* HTML
  * Used for e.g. a copyright notice, or a chunk of content for hours of operation&#x20;





