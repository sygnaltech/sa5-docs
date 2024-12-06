---
description: Embed tables from Google Docs directly in your Webflow pages.
---

# Google Doc Table Embeds

## Overview

Why Google Docs?

Pros;&#x20;

* Free
* Solid administration
  * Easy to update
  * Easy to control secure access to the Google Doc
  * Easy to re-order rows or columns
  * Easy to add/remove rows or columns
  * Easy to add images and links&#x20;
  * Easy colspan and rowspan options
  * Can place multiple tables in the same Google Doc, and reference the one you want
* Flexible
  * Supports paragraph style content
  * Images
  * List style content
  * Links&#x20;
* Supports unique elements like Smart chips

Cons;

* Styles like highlighting, text color and cell background color do not pass through
  * This is a positive if you want tight control in the design&#x20;
* Styling must be done in custom CSS, or via themes
* Not dynamically responsive
  * We can e.g. adjust font sizes but not rearrange columns to rows



Embed content from Google Docs directly in your Webflow pages.

## Usage Notes

First create your Google Doc;

* Create your doc in any drive you like
* Set its access to readonly with the link
* Get the URL, e.g. \
  `https://docs.google.com/document/d/1CFPmlJ0WmYbtQCyf8NaVCilnxfc0ah9wpm4XpE2b4zo/edit`

### Embed in your Webflow Site

Create an HTML Embed in your page, or within a rich text element, and paste the below HTML in;&#x20;

{% code overflow="wrap" %}
```html
<script type="sygnal/embed" wfu-embed-type="googledoc" wfu-embed-version="1">
{
  "src": "YOUR-LINK-HERE",
  "selector": "table",
  "index": 0,
  "theme": "default",
  "adminLink": true
}
</script>
```
{% endcode %}

Paste your link as the `YOUR-LINK-HERE` value. &#x20;

If you have more than one table in the Google doc, identify the one you want by index. The first on is index `0`, the second is `1`, and so on. &#x20;

If you do not want the admin link to appear in the corner for easy access, you can set that to `false`.&#x20;

{% hint style="info" %}
Whatever modifications you make, the content must be valid JSON.
{% endhint %}

### Future HSON

```html
// Some code
<script type="sygnal/embed+hson">
name: John Doe
slug: john-doe
brief: Software Engineer
</script>
```

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../quick-start.md).&#x20;

### STEP 2 - Embed the script blocks for your embeds, as above <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.&#x20;

