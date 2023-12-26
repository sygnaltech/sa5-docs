---
description: Embed tables and more, directly from sources such as Google Docs.
---

# Table Embeds ❺🧪

{% hint style="success" %}
**RELEASED in SA5 v5.3.13**

Currently in BETA.&#x20;
{% endhint %}

Embed content from Google Docs directly in your Webflow pages.





### Embedding Tables from Google Docs

{% code overflow="wrap" %}
```html
<script type="wfu-embed">
{
  "type": "gdoc",
  "version": "1",
  "src": "https://docs.google.com/document/d/1CFPmlJ0WmYbtQCyf8NaVCilnxfc0ah9wpm4XpE2b4zo/edit",
  "selector": "table:eq(0)",
  "theme": "default"
}
</script>
```
{% endcode %}





## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Create a Google Document containing the table(s) you want.

&#x20;



n HTML Embed or plain-text element on your page, data-bound to the CMS if you like.

### `wfu-decode` attribute <a href="#wfu-decode-attribute" id="wfu-decode-attribute"></a>

Add this to the HTML Embed element you want the contents decoded for. No value needed.

Note that the CSS will hide this element initially until after it’s decoded, at which point we make it visible.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../sa5-html/quick-start.md).&#x20;

### STEP 2 - Apply `wfu-decode` to the HTML Embed element you want to decode <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

\
