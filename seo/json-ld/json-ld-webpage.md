# JSON-LD WebPage

> This type can get a bit tricky in the fact that every URL is essentially a “web page.” The cool thing about this type is that it (may) yield a [site name](https://developers.google.com/structured-data/site-name) within Google’s search results as well as a search box if implemented correctly.
>
> [https://jsonld.com/web-page/](https://jsonld.com/web-page/)



## Features

* Place in site-wide code
* Auto-generates `WebPage` JSON-LD schema for every page
* Pulls meta title and description automatically
  * Options to pull others
  * SEO preference before mechanical `<title>`?&#x20;
  * Options to override?

### Future

* Template options
* Callback option for modification
  * Or suppression
  * Passes object in, can be modified and returned
    * or null to suppress&#x20;

## Example

Why?



{% code overflow="wrap" %}
```html
<script type="application/ld+json">
{
    "@context": "http://schema.org",
    "@type": "WebPage",
    "name": "About Patrick",
    "description": "In addition to Patrick's work in the SEO field, he also enjoys classical jazz dancing and organic farming ",
    "publisher": {
        "@type": "ProfilePage",
        "name": "Patrick's Website"
    }
}
</script>
```
{% endcode %}

[https://jsonld.com/web-page/](https://jsonld.com/web-page/)
