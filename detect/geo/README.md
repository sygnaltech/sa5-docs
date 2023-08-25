---
description: Route Visitors and Display Conditional Elements Based on Country or City.
---

# Geolocation Detection ❺

{% hint style="danger" %}
**UNDER DEVELOPMENT**

Watch this space.
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>



## Use Cases

* Route visitors to a Country-specific home page
* Route visitors to a City-specific contact-us page

## Future Plans

* Support for multiple Geoip handlers&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### Routing Rules

Routing rules are configured just before the library is loaded in the script section indicated with // Routing rules ( see quick start ).&#x20;

* You may have multiple rule configurations in this section, though this is mostly a future design facilitation. Most likely, the first rule matched will be applied.&#x20;

#### Route by Country

Specify the rule `type` as `geo-country`.

Supply your routes, from country code to path, exactly as in the structure below. You may have as few or as many routes as you like.&#x20;

If the visitor's country is not in the list, they will not be routed. They will simply match the default page.&#x20;

{% hint style="info" %}
We're working on a design for grouped countries as a regional definition.
{% endhint %}

```html
<script>
// Routing rules
window['sa5_route'] = [{
    type: 'geo-country',
    path: '/',
    route: [
        ["NZ", "/nz"],
        ["AU", "/au"],
        ["US", "/us"],
        ["GB", "/gb"],
    ]
}];
</script>
```

{% hint style="danger" %}
**ALPHA PRE-RELEASE.** Not advised for production use. Use v4 for production sites.&#x20;
{% endhint %}

### Setup the Cache

Place this code in your site or page level **/head** code,





