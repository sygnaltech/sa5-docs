---
description: Display an estimated price in the user's local currency
---

# Price in Local Currency 🧪

{% hint style="info" %}
ALPHA, not ovailable to the public.&#x20;
{% endhint %}

## How it Works

There are two parts to this feature-

* Determining the local currency
  * Using GeoIP mechanics to identify their country
  * And possibly a currency switcher UX&#x20;
* Converting your prices from their actual currency to the local currency

## Currency Detection

Determine the country and use a lookup.

* Cloudflare reverse proxy
* IPInfo lib

? Work with SA5 Detect lib?&#x20;

## Usage Notes

Identify your source currency somewhere, e.g. config settings

Identify your destination currency on an element

Use SA5 formatting? To handle price display&#x20;

## Technical Notes

[https://exchangeratesapi.io/#pricing\_plan](https://exchangeratesapi.io/#pricing\_plan)



[https://github.com/fawazahmed0/exchange-api](https://github.com/fawazahmed0/exchange-api)

[https://latest.currency-api.pages.dev/v1/currencies/eur.json](https://latest.currency-api.pages.dev/v1/currencies/eur.json)



