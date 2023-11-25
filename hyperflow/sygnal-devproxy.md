# Sygnal DevProxy

This tool is designed to make it easy to swap out scripts and CSS to alternate DEV-mode versions and view your _live_ site with those scripts in place.&#x20;

It's most useful in situations where you have a production site, using CDN-delivered scripts, and you need to switch them out for dev or testing.

## Features

* Support for multiple DEV / TEST configurations&#x20;
* Uses the subdomain as the prefix, e.g. test.mydomain.com would apply the test prefix
* Automatically overrides `src` and `href` attributes on any element with the CONFIG-src or CONFIG-href equivalent
* Uses the subdomain as the CONFIG prefix, e.g. `test.mydomain.com` would apply the `test` prefix and override `src` with the value of `test-src`.&#x20;

The subdomain acts as the prefix.

## Config

### DNS

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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
