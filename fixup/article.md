---
description: Fix common Webflow issues in the Editor and published site.
---

# Webflow Fixups ❺🧪

{% hint style="danger" %}
**EXPERIMENTAL ALPHA** ⑤

DO NOT USE this in production code, as it may be removed. We'll see if this approach works. Testing with Google is in progress.&#x20;
{% endhint %}

## Overview <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Unsupported Browser pop-up

Problem- this appears even when you are not logged into the editor.

### ![](<../.gitbook/assets/image (3).png>)

###

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

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

{% hint style="info" %}
This feature is using WFU's v5 new TypeScript-based library, so it is has different URLs and _code placement_ from the v4 JS-based library.&#x20;

You can use both the v4 and v5 libraries simultaneously to get the full feature set during migration.
{% endhint %}

Add this to the **before HEAD** custom code area of your site or page.



{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | HTML -->
<script defer
src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.1/dist/nocode/webflow-fixup.min.js"
></script> 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.1/dist/css/webflow-fixup.min.css">
```
{% endcode %}

Nothing is needed in the before BODY code area.&#x20;



