# Hyperflow Page

{% hint style="success" %}
Released to Sygnal production.
{% endhint %}

**Hyperflow Page** is a core architecture piece of the Hyperflow framework which fields the responses for every _content_ page on a Webflow-hosted site.

It handles a wide range of permutations, such as;

* DevProxy support
* Replace jQuery with latest version
  * Fixes Adblocker Plus (ABP), Brave, and Adblocker issue with jQuery suppression&#x20;

Future;&#x20;

* Remove conditionally visible elements
* Remove gated content by User Accounts access group
* Modify links to page-default settings such as `rel=nofollow` or `target=_blank`

## Config

```
// Some code
<script type="application/sa5-config">
[
    { "sitemap": { "lastUpdated": "2023-11-06" } },
    { "conditional": "remove" },
    { "nofollow": "external" }
]
</script>
```

Future;

* HSON support

## Setup

Worker route;

`*domain.com/*` -> `webflow-page`

