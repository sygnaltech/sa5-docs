---
description: How Hyperflow's configuration model works
---

# Configuring Hyperflow Services

Each service within Hyperflow has its own configuration needs per-site, and those configurations are centrally stored in a KV store.&#x20;

## The KV Store

By convention, that store is named `CONFIG`, and it contains one element per site-service-configuration.

This is represented in the key as-

`<base-domain>:<service-name>`

* `base-domain` is the domain name you're configuring the service for, minus any `www.` prefix.
* `service-name` is the unique service name for the Hyperflow service you're configuring.

For example;

`sygnal.com:purge-cache`

Subdomains can be specially configured, e.g.;

`blog.sygnal.com:purge-cache`&#x20;

Except;&#x20;

* `www.` is resolved to the base domain
* `hf.` is resolved to the base domain&#x20;
* `z.` is reserved for local debugging

## The Config value

The configuration value is a JSON object.

Its specifics will depend on the service you're configuring, but there are always two standard parts;

* `version` is an integer value indicating the version of the config
* `origin` is reserved and identifies a 3rd party source as the proxied site. It's used for indirect proxy configurations. Origin always specifies the protocol and domain, as in `https://www.sygnal.com`

## Embedded Configs

HtmlRewriter can easily locate matched elements however it does not have the ability to pull the text content. For this reason it's currently easiest to use attributes.&#x20;

{% code overflow="wrap" %}
```html
<script type="hyperflow/google-doc"
  data-google-doc-id="1_t3yiiYHYM6Q5mGbb2piDq3QedOCo3XC12QhHnmd7q8"
  ></script>
```
{% endcode %}

### Notes

It is possible to get text elements separately with HtmlRewriter, however it may not be possible to identify the containing element, in which case we have no context.

Ideally, we want to standardize on JSON or HSON configs.&#x20;

{% code overflow="wrap" %}
```html
<script type="hyperflow/google-doc">
{
  "type": "gdoc",
  "version": "1",
  "src": "https://docs.google.com/document/d/1_t3yiiYHYM6Q5mGbb2piDq3QedOCo3XC12QhHnmd7q8/edit",
  "theme": "default"
}
</script>
```
{% endcode %}



