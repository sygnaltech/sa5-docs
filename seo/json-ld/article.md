---
description: Generate valid JSON-LD Structured data from CMS Content
---

# JSON-LD Article ❺🧪

{% hint style="danger" %}
**EXPERIMENTAL ALPHA** ⑤

DO NOT USE this in production code, as it may be removed. We'll see if this approach works. Testing with Google is in progress.&#x20;

**STATUS**

Testing Google response to our script generated JSON-LD.&#x20;
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

## Variants

* Article
* NewsArticle
* BlogPosting
* TechArticle (maybe)

[https://developers.google.com/search/docs/appearance/structured-data/article](https://developers.google.com/search/docs/appearance/structured-data/article)

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Place this code in your site or page level **/body** code.

{% code overflow="wrap" %}
```html
<script>
var article = new window.sa5.LdJsonArticle();
article.headline = `Article headline`;
article.addAuthor (`Bob Hershel`);
article.publisher = `Sygnal`;
article.generate();
</script>
```
{% endcode %}

### .headline



### .addAuthor()



### .publisher



### .generate()

Renders the JSON-LD as a script element and appends it to the `<body>`.&#x20;



{% hint style="success" %}
The build script can be split into multiple parts so that they can execute in the most appropriate locations on the page. For example, if you have a list of content that is generated from a Collection List, part of the script can separately assemble that part.&#x20;
{% endhint %}
