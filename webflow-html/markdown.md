---
description: Embed markdown content, including tables and more.
---

# Markdown ❺🧪

{% hint style="warning" %}
**NOT YET AVAILABLE**

Currently in experimentation
{% endhint %}

## Usage Notes

Embed as an element, anywhere

```
<markdown>
  
# This is Markdown  
  
| Day | Ponsonby Doctors | Viaduct Doctors |  
| :--- | :--- | :--- |
| Mon 15th | 1pm - 5pm | 8am - 12pm |
| Tue 16th | closed | closed |
| Wed 17th | 9am- 5pm | 9am - 5pm |
| Thurs 18th | 1pm - 5pm | 8am - 12pm |
| Fri 19th | 1pm - 5pm | 8am - 12pm | 
| Sat 20th | closed | 9pm - 1pm |
| Sun 21st | closed | closed |
</markdown>
```

### Markdown "elements"

You can convert a standalone HTML Embed element into a&#x20;

\[wfu-markdown]

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

Store HTML directly in CMS text fields, and render them in decoded form on the page.

## Use Cases&#x20;

Good for…

* 3rd party embeds like SoundCloud, and YouTube
* JSON+LD embeds

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

Create an HTML Embed or plain-text element on your page, data-bound to the CMS if you like.

### `wfu-decode` attribute <a href="#wfu-decode-attribute" id="wfu-decode-attribute"></a>

Add this to the HTML Embed element you want the contents decoded for. No value needed.

Note that the CSS will hide this element initially until after it’s decoded, at which point we make it visible.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Add this code to the **before HEAD** of your site or page.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | HTML -->
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.8/dist/css/webflow-html.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.8/dist/nocode/webflow-html.js"></script>
```
{% endcode %}

### STEP 2 - Apply the custom attributes as desired <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

## Technical Notes & Credits

Uses Showdown.js for the Markdown conversion

In your live site, the markdown elements are initially hidden until they are processed. Users may see an empty space briefly before the markdown conversion happens.&#x20;

For very large tables ( which this is not suited for ) that may result in a content layout shift.&#x20;

\
