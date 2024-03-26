# Sygnal DevProxy

{% hint style="success" %}
PRODUCTION. &#x20;

app-dev-proxy&#x20;
{% endhint %}

Setup

Add CONFIG

e.g. dev.sygnal2.xyz

dev-src











This tool is designed to make it easy to swap out scripts and CSS to alternate DEV-mode versions and view your _live_ site with those scripts in place.&#x20;

It's most useful in situations where you have a production site, using CDN-delivered scripts, and you need to switch them out for dev or testing.

## Features

* Support for multiple DEV / TEST configurations&#x20;
* Uses the subdomain as the prefix, e.g. test.mydomain.com would apply the test prefix
* Automatically overrides `src` and `href` attributes on any element with the CONFIG-src or CONFIG-href equivalent
* Uses the subdomain as the CONFIG prefix, e.g. `test.mydomain.com` would apply the `test` prefix and override `src` with the value of `test-src`.&#x20;

The subdomain acts as the prefix.

### Multiple Entry Points

e.g. `https://dev.mysite.com`

Or for specific needs, can switch mode via Chrome Ext.&#x20;

{% hint style="info" %}
Document Chrome Extension.&#x20;
{% endhint %}

### Page Info

In HTML comments;

{% code overflow="wrap" %}
```html
<!DOCTYPE html>
<!-- Origin: https://mysite.webflow.io/blog/best-non-wearable-sleep-tracker -->
<!-- Last Published: Sat Jan 06 2024 03:09:21 GMT+0000 (Coordinated Universal Time) -->
<!-- Age: 0 days, 0 hours, 36 minutes, 6 seconds -->
```
{% endcode %}

## Future

* Expose Page Info as JSON, display and manage in Chrome Ext
* DEV / TEST modality to internal scripts&#x20;
  * Via `<html>` `hf-mode=`

## Config

SITE-NAME:devproxy

```
{
    	"version": 1, 
	"origin": "https://www.sygnal.com",
	"type": "static", 
	"map": {
		"/foo": "/about"
	}
}
```



### DNS

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

CNAME dev proxy.webflow.com Proxied  &#x20;

### KV / DEVPROXY

In the KV store you configure the underlying content origin for each of your devproxy sites individually. Typically, this will be your `webflow.io` site;&#x20;

e.g. `dev.mysite.com` -> `mysite.webflow.io`

If not found, it defaults to the www subdomain on the same site;

e.g. `dev.mysite.com` -> `www.mysite.com`











| Route                                                   | Worker            | Notes                                              |
| ------------------------------------------------------- | ----------------- | -------------------------------------------------- |
| [https://dev.sygnal.com/\*](https://dev2.sygnal.com/\*) | webflow-dev-proxy | Will replace all dev-src and dev-href attributes.  |
|                                                         |                   |                                                    |
|                                                         |                   |                                                    |

Automatic Norobots on this Route&#x20;



Route

[https://dev.sygnal.com/\*](https://dev2.sygnal.com/\*)

Worker
