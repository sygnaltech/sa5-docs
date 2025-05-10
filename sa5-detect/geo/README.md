---
description: Route Visitors and Display Conditional Elements Based on Country or City.
---

# Geolocation Detection 🧪

{% hint style="danger" %}
**UNDER DEVELOPMENT**\
Watch this space.
{% endhint %}



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









## IPinfo Lite&#x20;

| <p>IPinfo Lite gives you essential IP data completely free, with no restrictions. Here’s what you have to look forward to:</p><ul><li>Industry-leading, enterprise-grade accuracy</li><li>Country, continent, and ASN data</li><li>Use it commercially with no caps or usage limits</li><li>Data updated daily</li><li>Unlimited usage via API or download</li></ul><p>Here's an example of the Lite API, showing the ASN and county level geolocation fields that are included:</p><p> </p><p>$ curl <a href="https://api.ipinfo.io/lite/8.8.8.8?token=$TOKEN">https://api.ipinfo.io/lite/8.8.8.8?token=$TOKEN</a></p> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

<table data-header-hidden><thead><tr><th align="center" valign="top"></th></tr></thead><tbody><tr><td align="center" valign="top"><a href="https://email.ipinfo.io/e3t/Ctc/DP+113/d2R-Zr04/VVTdCq7srf4wW1P5jv82Xrv-zW1KLHGL5wktfyN9k7M9C3qgyTW6N1vHY6lZ3m2VHCn2L8j2v8NW2JlGNV3BzPbFW6GT3q44xh3B4W8pG6Hj4-Z16-VP74-966_m2xW4jT-z95D3kCvVsnF-W7RCFv0W7lKscX50ZgnyW7BfTxF3XZ08LW60LPvY3-kdV0N4gxjl_h9m4cW3CJmn07BtlyHW1W8dxK8gq0S3W2NZlBX7StsGBW9d0TKF2rq5bDW4V6tmK4ttwVPW6bhNlM1qRy-JVvLHP08pj4sLW10210G1PGqwjW2TtbRb5D3gYLN9l3zLgCk9VjW8qmjFx3WRWHjf6QRJ7204"><img src="https://ci3.googleusercontent.com/meips/ADKq_Nb2cqr0MJsLpoynVFdlkwwBLuHAyexUDxO6fDrEyo14VOrsQVeuk1dkCJ4dWBN7YGGSY_ICKH0SkcKHEefLckzZ4Y4JGGYd3mnvlBo6lV9OqiXcZLrIXJ3qVjZTjFbfew_pX4JZ0vyjzoatP5cdntkIcGX5FS0gUbUKjN2S8xxOSw=s0-d-e1-ft#https://email.ipinfo.io/hs-fs/hubfs/sample%20response.png?width=900&#x26;upscale=true&#x26;name=sample%20response.png" alt="sample response"></a></td></tr></tbody></table>

| <p>Prefer working with files? The data is also available as a download, in JSON, CSV, MMDB and Parquet formats – ready to integrate into your tools, dashboards, or workflows.</p><p><br>IPinfo Lite is your new go-to – and built to support everything from side projects to production systems. While IPinfo Lite only includes a subset of all of the data we offer, there's no compromise to the data quality, or the refresh rate.</p> |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |



