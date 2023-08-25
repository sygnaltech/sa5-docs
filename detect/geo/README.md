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

## Feature Roadmap

{% tabs %}
{% tab title="Completed" %}
* Route user by Country
* Routing table support
  * Supports routing any defined path, e.g. /about to any Geo-specific variants you have, e.g. `/about/gb`, `/about/au`, `/jp/about`.&#x20;
  * Routed sources and destinations are unlimited, no enforced path rules.&#x20;
* Standardized GeoInfo object, to consistently describe the detection regardless of the GeoIP handler source&#x20;
* Cached responses, for minimal GeoIP service traffic
  * One request per unique user&#x20;

GeoIP handlers;

* IPInfo support. 50,000 requests/mo free.&#x20;
{% endtab %}

{% tab title="Planned" %}
* Route user by Continent
* Route user by City
* Cache duration as a setting
* Named route efficiency
  * Modify page paths on e.g. Home / to the routed page variant, to avoid unnecessary redirects. &#x20;

Override support;

* The ability to apply the current setting to a Dropdown, and automatically indicate the current Country, City, etc.
* The ability to change country, city, etc and have that override the detected settings.&#x20;

GeoIP handlers;

* Support for multiple Geoip handlers&#x20;
  * Ability to select in config
{% endtab %}

{% tab title="Considering" %}
Developer support;

* Expose and document the Detect objects for use in code, e.g.;
  * Data-binding support, populate a form's Zip code field, select a country, etc.&#x20;
  * Auto-center maps&#x20;
* Automatic Filter-binding support for FS-Filter

GeoZone definitions;&#x20;

* Collection of countries, cities, zips, etc into a Zone, like "Europe"&#x20;

GeoIP handlers;

* Ability to select the GeoIP handler dynamically in config&#x20;
* Fallback handlers&#x20;
{% endtab %}

{% tab title="More Ideas" %}
GeoZone definitions;

* Point-and-radius
* Sort list by nearest ( branch locators, etc. )&#x20;
* Zip to data chaining&#x20;

GeoIP handlers;

* Possibly a Sygnal-specific Geoip handler&#x20;
{% endtab %}
{% endtabs %}



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

###





