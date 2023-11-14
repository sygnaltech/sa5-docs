# Proxy Tools

##

## Favicon.ico

```
/favicon.ico
```

## x-attributes



NoIndex

```
<meta name="robots" content="noindex" />
```

A "noindex" HTTP response header

```
X-Robots-Tag: noindex
```



## HTML Decode chunks

To support a kind of HTML Embed field in the CMS.&#x20;

## SmartBundling

Detect SA5 attributes, and load the necessary libs automatically.

versioning?&#x20;

smart bundling&#x20;

## Memberships

Extend memberships with e.g. user data

Get user id

## SA5 Data

One big datasource;

* Uses SA5 to define
* Can contain multiple schemas
* Auto-parsed by ?data

Add ?data to any URL, you'll see the data for that page

Future;

Lockdown&#x20;

Consider adding a filtered focus, e.g. #dsn.

querying ?&#x20;



? Can auto-parse from collection lists?&#x20;

## Path changes

Aliasing CMS items&#x20;

* Fix canonical
* Serve under arbitrary path
* Redirect CMS item path
* Fixup sitemap.xml

Advantages;

* No special linking needed&#x20;
* Supports

KV store configuration;&#x20;

{% hint style="info" %}
Key should have no protocol, and no www. prefix
{% endhint %}

* Key: `sygnal.com/orig-path/`
* Value: `/dest-path/`&#x20;





## Sitemap.xml

Remove paths?

Add mod data

Language

Modify existing Webflow one&#x20;

Support multi-site hybrids, using a main directory file separately&#x20;

Always even with a single site?&#x20;

Master last-changed date&#x20;

&#x20;

## Local scripts

&#x20;/js/

&#x20;/css/



## Google Adsense & Others

Google Adsense and other advertising platforms require an `/ads.txt` file for verification.&#x20;

This tool is a standalone worker, and is designed to work with a Cloudflare KV store;

Key: **`HOSTNAME`**`-ads.txt`

Value: Content you want, multiline should work if desired&#x20;

{% hint style="info" %}
HOSTNAME does NOT include www. for consistency. Other subdomains can be used.
{% endhint %}

e.g. key - `sygnal.com-ads.txt`



{% hint style="info" %}
This is done because Workers and KV store is account wide, while you may have multiple sites under it which need varying configurations.
{% endhint %}



Designed for situations like Google Adsense

File is&#x20;

Here's an example; &#x20;

[https://sygnal.com/ads.txt](https://sygnal.com/ads.txt)



## Language Link cross-references







## SEO









