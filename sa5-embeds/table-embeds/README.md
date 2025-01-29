---
description: Embed tables and more, directly from sources such as Google Docs.
---

# Table Embeds ❺

{% hint style="success" %}
**RELEASED in SA5 v5.3.13**
{% endhint %}

## Goals

* Embed tables from Google Docs directly in your Webflow pages
* Support embedding in;
  * Standalone elements
  * Rich text blocks&#x20;
  * CMS-bound rich text blocks&#x20;
* Support specific content formatting
  * Bulleted lists
  * Links
* Remove all other content formatting to be brand-compliant&#x20;

## Demonstration

Here's a demo of SA5 embedded tables in action;&#x20;

[https://www.sygnal.com/lessons/client-seats](https://www.sygnal.com/lessons/client-seats)

And the source content; &#x20;

[https://docs.google.com/document/d/1rIWGo3yUQvEfJNDrykgP7amqSdI5p45USXpVQGHj6rc/edit?tab=t.0](https://docs.google.com/document/d/1rIWGo3yUQvEfJNDrykgP7amqSdI5p45USXpVQGHj6rc/edit?tab=t.0)

Here's how and why to integrate them;&#x20;

{% embed url="https://www.loom.com/share/293e86a178ef4cc19458354d82bcae68" %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../sa5-html/quick-start.md).&#x20;

### STEP 2 - Prepare your Google Doc Table

Make certain to make the document read-only to anyone with the link.&#x20;

### STEP 3 - Create an Embed Where you Want the Table

* Either standalone in your page design
* Or within static rich text content
* Or within CMS-stored rich text content

Paste this in.

Replace the src with your own document.&#x20;

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



\
