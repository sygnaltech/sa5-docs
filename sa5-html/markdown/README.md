---
description: Embed markdown content, including tables and more.
---

# Markdown ❺

This feature brings basic Markdown capabilities into Webflow projects.&#x20;

## Goals

* Support the embedding of simple, small chunks of markdown content directly in your Webflow page, including both;&#x20;
  * "Chunk" format with multiple elements&#x20;
  * Single-line format, where you only are using inline styles like bold, italics, highlight, strikethrough, etc.&#x20;
* Make them Embed compatible for simple editing&#x20;
* Support CMS use, within Rich Text field Embeds&#x20;
* Support Components, and component properties&#x20;

## Use Cases

* Small table generation, in an easily-editable fashion&#x20;
* Small tables within blogs and other rich text content&#x20;
* Component property text formatting, such as bolding, italics, and highlighting within a property text string&#x20;

## Usage Notes

### Rendering a block of Markdown

SA5 supports two approaches for Markdown content;&#x20;

1. Use the `<markdown>` or `<md>` element inside of any HTML Embed.&#x20;
2. Use a standard `<div>` with a custom attribute of `wfu-markdown` on it.&#x20;

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

And another example, using the `<div>` approach;

```html
<div wfu-markdown>
# This is more markdown

- List
  - Indented
    - And more
  - Less Indented
  
1. Numbered
2. List

> Blockquote
> here. 

</div>
```

Both approaches are widely-supported;&#x20;

* Works in standalone embed elements or as an embed within a rich text block
* In rich text blocks, works with both static rich text blocks, and CMS-bound RTBs&#x20;

{% hint style="warning" %}
Note that some users report that the `<markdown>` approach may be ignored by Webflow's Site Search feature.  If you need that content indexed, try the `<div>` approach.  The markdown content within it should be treated as plaintext for indexing purposes.&#x20;
{% endhint %}

{% hint style="success" %}
If you need to use Markdown extensively, and need _server-side rendering_ to ensure 100% SEO support, Sygnal Hyperflow supports this.  Contact us for details about a custom build.&#x20;
{% endhint %}

### Rendering an individual element as Markdown

In some cases, you may want only a small amount of Markdown rendered, for inline styling. &#x20;

{% hint style="success" %}
This is very useful for components, when you are binding to a plain text component property. Basic formatting like bold, underline, strikethrough and highlighting can be expressed as markdown and rendered properly into your page.
{% endhint %}

In this case, you have a two options that do not require embeds.

1. Create a DIV, heading, or other element, and assign the custom attribute of `wfu-markdown` to that element ( no value is needed ).&#x20;
2. Create a custom element of type `markdown` or `md` and put your content within it as text.

{% hint style="info" %}
Both approaches work in components, and support binding to component properties. You can then use markdown directly in the component property itself.&#x20;
{% endhint %}

## What Markdown Syntax is Supported?

SA5 supports;

* All [Markdown that Showdown supports](https://showdownjs.com/docs/markdown-syntax/) natively&#x20;
* Plus [table syntax](https://www.markdownguide.org/extended-syntax/#tables) using Showdown's [table extensions](https://showdownjs.com/docs/markdown-syntax/#tables)
* Plus a custom SA5 _highlighting_ extension, which uses a [popular `==` syntax](https://stackoverflow.com/questions/25104738/text-highlight-in-markdown)  that is [widely recognized](https://www.markdownguide.org/extended-syntax/#highlight).&#x20;

See the markdown&#x20;

Other markdown-generated styling can be similarly targeted.&#x20;

<table><thead><tr><th>Style</th><th>Markdown</th><th width="130">Element</th></tr></thead><tbody><tr><td><em>Italics</em></td><td><code>*Text*</code></td><td><code>&#x3C;em></code> </td></tr><tr><td><strong>Bold</strong></td><td><code>**Text**</code></td><td><code>&#x3C;strong></code> </td></tr><tr><td>Highlighting</td><td><code>==Text==</code></td><td><code>&#x3C;mark></code> </td></tr><tr><td><del>Strikethrough</del></td><td><code>~~Text~~</code></td><td><code>&#x3C;del></code> </td></tr></tbody></table>



## Styling Your Markdown Content

Customize styling using custom CSS in an embed, like this;&#x20;

```html
<style>
[theme=default] mark {
  background-color: lightblue;
}
</style>
```

This targets `<mark>` elements which are generated with the `==highlighting==` markdown syntax.

Other markdown-generated styling can be similarly targeted.&#x20;

<table><thead><tr><th>Style</th><th>Markdown</th><th width="130">Element</th><th width="239">CSS Selector</th></tr></thead><tbody><tr><td>Italics</td><td><code>*Text*</code></td><td>em</td><td>[theme=default] em</td></tr><tr><td>Bold</td><td><code>**Text**</code></td><td>strong</td><td>[theme=default] strong</td></tr><tr><td>Highlighting</td><td><code>==Text==</code></td><td>mark</td><td>[theme=default] mark</td></tr><tr><td>Strikethrough</td><td><code>~~Text~~</code></td><td>del</td><td>[theme=default] del</td></tr></tbody></table>



### Themes <a href="#getting-started-nocode" id="getting-started-nocode"></a>

Markdown can be themed by specifying a theme attribute, e.g.;

```
<markdown theme="theme1">
 ...
</markdown>
```

See the [Themes page](themes.md) for more details.&#x20;

## Getting Started <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).&#x20;

### STEP 2 - Apply the custom attributes as desired <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

## Technical Notes & Credits

Uses Showdown.js for the Markdown conversion

In your live site, the markdown elements are initially hidden until they are processed. Users may see an empty space briefly before the markdown conversion happens.&#x20;

For very large tables ( which this is not suited for ) that may result in a content layout shift.&#x20;

\
