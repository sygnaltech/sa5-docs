# Quickstart

{% hint style="info" %}
We're using the subdomain approach as it's likely we'll evolve aspects of HF into a Cloudflare app.&#x20;
{% endhint %}

Given;

* **DOMAIN** e.g. sygnal.com
  * Registered on CF, with DNS and proxy setup&#x20;
* **ZONE-ID** for that domain

## Setup

### DNS

Add a CNAME for hf to @&#x20;

Set it to proxy on&#x20;

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Config

Add a KV store config of to CONFIG, with your ZONE-ID. &#x20;

Key; **`DOMAIN`**`:purge-cache`

```json
{
  "version": 1, 
  "zoneId": "ZONE-ID" 
}
```

### Worker Route

`*hf.`**`DOMAIN`**`/cache/purge` -> `cloudflare-clear-cache`

### Verify

https://hf.DOMAIN/cache/purge

A successful response is;&#x20;

```
Cache Purge Initiated Successfully
```

### Webflow Webhook

Get your site id

[https://developers.webflow.com/reference/list-sites](https://developers.webflow.com/reference/list-sites)

e.g. 62296a1920ec667f814208e2

[https://developers.webflow.com/reference/list-webhooks](https://developers.webflow.com/reference/list-webhooks)





#### Create Webhook

[https://developers.webflow.com/reference/create-webhook](https://developers.webflow.com/reference/create-webhook)

Paste in site\_id

Select site\_publish&#x20;

Paste in your HF URL

e.g. [https://hf.ponsonbydoctors.co.nz/cache/purge](https://hf.ponsonbydoctors.co.nz/cache/purge)

Click Try It!

Check for a valid 201 response e.g.;

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

