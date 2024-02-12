---
description: >-
  Embed Google document content directly in your Webflow page, with its original
  formatting.
---

# Hyperflow Google Docs

{% hint style="success" %}
**PRODUCTION RELEASE.**&#x20;

Learn more about this product on the [product page](https://www.sygnal.com/services/hyperflow-for-google-docs).\
Part of `hf-google-doc`.&#x20;
{% endhint %}

## Features

* Embed any public google doc directly into your Webflow-hosted site page
* Modify the Google doc at any time
* Preserve the exact Google doc styling
* Fully part of the page, fully SEO-able&#x20;
* Does well with responsiveness

## Use Cases

* Include a current specials sheet or securely edited Google
* Include content that Webflow cannot format well;
  * Tables

## Feature Roadmap

<table><thead><tr><th width="136">Feature</th><th>Current</th><th>Planned</th><th>Possible</th></tr></thead><tbody><tr><td>Multiple Doc Embeds</td><td>No</td><td>Yes</td><td><ul><li>Fully independent configs, including caching</li></ul></td></tr><tr><td>Caching</td><td>Basic, fixed 5 mins</td><td>Configurable length</td><td><ul><li>Global</li><li>fully configurable</li><li>part caching, i.e. transformed content only</li><li>by element, so different docs can have different cache settings</li></ul></td></tr><tr><td>Styling</td><td><p>Matches Google Doc exactly;</p><ul><li>Headings, paragraphs</li><li>Font family, color, and highlight color  </li><li>Images</li><li>Complex layouts</li><li>Tables</li><li>Smart embeds</li><li>Links </li></ul></td><td>Strip-style mode, apply a richtext class and use Webflow richtext elements.<br><br>Implementation uses a rich text element as the styling base, and then replaces the sub-elements with a translation of Google Docs elements P, H1, H2, etc. </td><td>Strips only from Webflow-supported elements, others are still carry original style classes to prevent breakage, e.g. tables </td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>Partial Embeds</td><td>No, full doc only</td><td></td><td><ul><li>Considering</li></ul></td></tr><tr><td>ToC</td><td></td><td></td><td><ul><li>Utilize built-in header ID's for ToC purposes</li><li>Prefix IDs</li><li>Could auto-apply FS ToC classes? </li></ul></td></tr><tr><td>Google Document Access</td><td>Must be shared as "viewable by anyone with the link"</td><td></td><td>May consider direct API access, for private docs. </td></tr></tbody></table>

## Setup notes

* Setup the page with `hf-google-doc`
* In pages with this handler, drop an HTML embed with this content.&#x20;
  * Use your own Google doc ID
    * Make sure your Google doc is accessible to anyone with the link

{% code overflow="wrap" %}
```html
<script type="hyperflow/google-doc"
  data-google-doc-id="1_t3yiiYHYM6Q5mGbb2piaq3QedOCo3XC12QhHnmd7q8"
  ></script>
```
{% endcode %}
