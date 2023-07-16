---
description: Generate valid JSON-LD Structured data from CMS Content
---

# JSON-LD Article \[EXPERIMENTAL] ❺🧪

{% hint style="danger" %}
**EXPERIMENTAL ALPHA** ⑤

DO NOT USE this in production code, as it may be removed. We'll see if this approach works. Testing with Google is in progress.&#x20;
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

**A great website is a wonderful thing, but it's useless if no one can find it.**&#x20;

In the SEO game, structured data is a powerful tool, but there is no direct support for generating it in Webflow.&#x20;

Here we want to make that easier;

* Generate structured JSON data reliably, with zero concerns about malformed JSON
* Generate JSON-LD without needing to know the exact syntax, convert dates, or know constants
* Handle arrays and sub-structures with the same level of ease
* Do this all _dynamically_ so that it can be accomplished with collection list data as well.&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### Setup the JSON-LD Generator

Place this code in your site or page level **/head** code.

It includes a few things;

* An application/ld+json script element to hold the resulting JSON-LD.
* In inline script, which will load and execute immediately to generate the necessary JSON inline, synchronously. In experiments, it seems this is necessary for Google to see the JSON results.
* A script chunk to initialize the generator object(s) you want.
* Script to update the object with information you need, during your page generation, collection list generation, etc.
* Script to complete the object generation and emit the JSON-LD.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | SEO -->
<script type="application/ld+json" id="ldJsonArticle">
</script>
<script 
src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.1-alpha/dist/experimental/webflow-seo.js"
src-dev="https://memetican-ideal-train-qvvrv94vq9f9vq6-3000.preview.app.github.dev/dist/experimental/webflow-seo.js"></script>
<script> 

// Setup the JSON-LD Generator
var article = new window.LdJsonArticle();

// Set the data
article.headline = `{{wf {&quot;path&quot;:&quot;name&quot;,&quot;type&quot;:&quot;PlainText&quot;\} }}`;
article.addAuthor (`Michael Wells`);
article.publisher = `Sygnal`;

// Generate and write the data out
var s = JSON.stringify(article.toJSON(),null,2); 
document.getElementById('ldJsonArticle').textContent = s;

</script>
```
{% endcode %}

The usage script can be split into multiple parts so that they can execute in the most appropriate locations on the page.

For example, if you have a list of content that is generated from a Collection List, part of the script can separately assemble that part.&#x20;



