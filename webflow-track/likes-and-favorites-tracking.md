---
description: Track likes, favorites, page visits, and more.
---

# Likes & Favorites Tracking

{% hint style="danger" %}
UNDER DEVELOPMENT
{% endhint %}

This feature described a general-purpose external tracking mechanism, integrated with Webflow.

## Use Cases

* Track anonymous likes on a collection item such as a product or block post
* Allow only logged-in users to like anonymously ( but everyone to see ).&#x20;
* Track page visits
* Track button clicks&#x20;

{% hint style="info" %}
This feature is likely to always work on an anonymous basis, meaning that it will never know who clicked an item, and therefore features like one-like-per-user or remove-like, or show-me-my-favorite's are not supported here. Look at Wized, or possibly JetBoost + Memberstack, if you need to combine those. &#x20;
{% endhint %}

{% hint style="info" %}
Although this design provides a flexible tracking mechanism, we do not advise using it for analytics or conversion metrics. GTM and Analytics are purpose-built for that.
{% endhint %}

## Roadmap

{% tabs %}
{% tab title="Completed" %}
This feature is in early prototyping stages.&#x20;
{% endtab %}

{% tab title="Planned" %}
* Site-specific likes and favorites.
* Anonymous meaning anyone can vote, as many times as they want to&#x20;
* Multiple tracking handlers
{% endtab %}

{% tab title="Considering" %}
Unlike

User-specific tracking&#x20;

Custom data store

Caching

User-data storage, using SA5's user info object&#x20;

Connecting SA5's Sort & Filter capabilities to allow for sorting and filtering of lists using likes & favorites.&#x20;
{% endtab %}
{% endtabs %}

## Technical Notes

Balance simplicity with control.&#x20;

Keys composed of 3 parts;&#x20;

`SITEID-COLLECTIONSLUG-ITEMSLUG`

SiteID composed from;

| Site ID                               | Collection ID                      | Item ID                               |
| ------------------------------------- | ---------------------------------- | ------------------------------------- |
| Webflow SiteID                        | ~~Path part?~~ not viable          | Slug                                  |
| Webflow Hostname                      | Custom setting in custom attribute | Custom override ( to support change ) |
| Custom override ( to support change ) |                                    |                                       |

### Handlers

[https://countapi.xyz/](https://countapi.xyz/)

Automatic tracking&#x20;





