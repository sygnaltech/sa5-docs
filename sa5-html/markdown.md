---
description: Embed markdown content, including tables and more.
---

# Markdown ❺

## Usage Notes

Use the `<markdown>` element inside of any HTML Embed.

* Works in standalone Embeds or as an embed within a rich text block
* Works with static rich text blocks, or CMS-bound RTBs&#x20;
* Supports any Markdown that Showdown supports, plus table extensions

Here's an example of an H1 followed by a table;

```html
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

### ~~Markdown "elements"~~

~~You can convert a standalone HTML Embed element into a markdown element without needing the `<markdown>` tag, using a custom attriute;~~&#x20;

~~`[wfu-markdown]`~~

## Themes <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Markdown can be themed by specifying a theme attribute, e.g.;

```
<markdown theme="theme1">
 ...
</markdown>
```

When unspecified, this will default to `default`.&#x20;

This allows you to target CSS directly on the markdown.

The default theme includes some basic table styling and nothing more.&#x20;

### Custom Themes

When a markdown element is converted to markdown it is wrapped in a DIV with an attribute of theme=theme-name, according to your specified theme or `default`.  &#x20;

This can be used in CSS for example;&#x20;

```scss
[theme=default] table {
    border-spacing: 10px 10px; 
    margin-bottom: 1rem; 
}
```

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply the custom attributes as desired <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

## Technical Notes & Credits

Uses Showdown.js for the Markdown conversion

In your live site, the markdown elements are initially hidden until they are processed. Users may see an empty space briefly before the markdown conversion happens.&#x20;

For very large tables ( which this is not suited for ) that may result in a content layout shift.&#x20;

\
