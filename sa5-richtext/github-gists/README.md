---
description: Add embedded GitHub Gist capabilities to your blog.
---

# GitHub Gists ❺

Does your article content contain JavaScript, CSS, HTML, XML, JSON, configuration files, or source code-formatted data of any kind?

Now you can easily add these content blocks to your Webflow rich text elements, with _full syntax highlighting_ and _easily make changes_ later.&#x20;

{% hint style="info" %}
This feature makes use of the [GitHub Gist service](https://gist.github.com/), which is widely used and 100% free.
{% endhint %}

With SA5's Rich Text lib, you can simply drop an HTML embed anywhere in your rich text content and paste in the Gist's embed.&#x20;

The code will be line numbered, and syntax-highlighted like this-

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

That's it.&#x20;

And there's more...

* You do not need to "fixup" any HTML tags to prevent HTML errors&#x20;
* You get Gist's full syntax highlighting for your code
* SA5 let's you embed the Gist unstyled, or to apply our themes
* Update your Gists anytime, using Gist's easy interface&#x20;
* Name your Gist elements and assign a copy-to-clipboard button &#x20;
* Can also be used outside of the rich text element, with standalone HTML Embeds&#x20;

## What is Gist?

GitHub's gist service allows you to easily share snippets of code or other information. These snippets, or "gists", can be made public or private, and they are git repositories, which means they can be forked, cloned, and versioned.

You can also embed gists into other websites, which makes them a handy tool for sharing code samples in blog posts or other web pages.

From a blogger's perspective, these provide an excellent way to quickly share and maintain code excerpts in your blog without complex formatting requirements.&#x20;

## Features Sygnal Attributes Adds

* The ability to link a Webflow button and copy the content of your gist to the clipboard, ready to paste as clean, formatted code.&#x20;

## Examples

For a standalone Gist in an HTML Embed, plus a copy button, see here for a [demonstration](https://webflow-breakpoint.webflow.io/). Scroll down to see the gists, and try the copy buttons.&#x20;

For a Rich Text-embedded Gist using the midnight theme, check out;

[https://www.sygnal.com/lessons/breakpoints](https://www.sygnal.com/lessons/breakpoints)

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

To embed a Gist;

* Drop an HTML embed anywhere on your page, or inside of a Rich Text element.
* On the Gist page, copy the embed code ( top right ), and paste that code into your HTML embed. The code is a simple line of script that looks like this;

{% code overflow="wrap" %}
```html
<script src="https://gist.github.com/memetican/b27a2d7c9649c379034deed0daf2ce5c.js"></script>
```
{% endcode %}

* If you have a multi-file Gist, the above code will show all of the files in the Gist, one after another. If you want to show only one file, you can append a querystring to the script, e.g.;

{% code overflow="wrap" %}
```html
<script src="https://gist.github.com/memetican/b27a2d7c9649c379034deed0daf2ce5c.js?file=richtext-loaded-event.html"></script>
```
{% endcode %}

### Themes

In addition to the default Gist appearance, SA5 currently supports two themes;

* `midnight`, inspired by CodePen
* `darkmode`&#x20;

To assign a theme, add the following attribute to the rich text block. That theme will be applied to all embedded Gists.

`wfu-gist-theme=(theme)`&#x20;

{% hint style="info" %}
This feature can also be used with a standalone HTML Embed element that is not part of a Rich Text Block ( RTB ).&#x20;
{% endhint %}

{% hint style="info" %}
For _static_ Rich Text Blocks that are not CMS-bound, you can assign custom attributes and classes directly to sub-elements.  In this case if you want to use different themes for different Gist embeds in the same RTB, you can assign the attribute directly to the HTML embed instead.&#x20;
{% endhint %}

### Copy to Clipboard Feature

SA5 supports linking a button to your Gist to copy it.

When clicked, it will locate the identified HTML Embed, and extract, clean and format the code contents, and copy them to the clipboard.&#x20;

I want this Button to copy the contents of this Gist to the clipboard

* Tag your HTML Embed element with the custom attribute\
  `wfu-gist=(identifier)` using any unique identifier you want.
* Tag your button with the custom attribute \
  `wfu-gist-copy=(identifier)`

{% hint style="warning" %}
Currently this only works with explicitly named embeds, which means that it's not easily adaptable to CMS-sourced rich text content. We're adding a separate feature for that soon.&#x20;
{% endhint %}

## Roadmap

{% tabs %}
{% tab title="Completed" %}
* Theming Gist embeds
* `midnight` theme
* `darkmode` theme
* Copy-to-clipboard support for _standalone_ HTML Embeds
{% endtab %}

{% tab title="Planned" %}
* More themes
* Auto copy-button feature with each code embed
{% endtab %}

{% tab title="Considered" %}
* Custom themes&#x20;
* Line-range highlighting
* Line-range excerpting&#x20;
{% endtab %}

{% tab title="More Ideas" %}
Admin editing link when in ?edit mode?&#x20;


{% endtab %}
{% endtabs %}

## Getting Started

{% hint style="success" %}
**100% NOCODE**\
All aspects of this feature are attributes-based for your convenience.&#x20;
{% endhint %}

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).&#x20;

### STEP 2 - Apply the Attributes you want <a href="#step-2---apply-wfu-listsnested-to-desired-elements" id="step-2---apply-wfu-listsnested-to-desired-elements"></a>

See above for details.&#x20;

\
