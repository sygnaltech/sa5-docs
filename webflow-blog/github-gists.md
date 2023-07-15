---
description: Add embedded GitHub Gist capabilities to your blog.
---

# GitHub Gists ❺

## Overview

GitHub's gist service allows you to easily share snippets of code or other information. These snippets, or "gists", can be made public or private, and they are git repositories, which means they can be forked, cloned, and versioned.

You can also embed gists into other websites, which makes them a handy tool for sharing code samples in blog posts or other web pages.

From a blogger's perspective, these provide an excellent way to quickly share and maintain code excerpts in your blog without complex formatting requirements.&#x20;

## Features Sygnal Attributes Adds

* The ability to link a Webflow button and copy the content of your gist to the clipboard, ready to paste as clean, formatted code.&#x20;

## Examples

See here for a [demonstration](https://webflow-breakpoint.webflow.io/).

Scroll down to see the gists, and try the copy buttons.&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

To embed a gist;

* Drop an HTML embed anywhere on your page, or inside of a Rich Text element.
* Paste in the gist share code, which is a simple line of script.

To add the gist copy feature;

* Tag your HTML Embed element with the custom attribute\
  `wfu-gist=X` where X is any unique identifier you want.
* Tag your button with the custom attribute \
  `wfu-gist-copy=X`

When clicked, it will locate the identified HTML Embed, and extract, clean and format the code contents, and copy them to the clipboard.&#x20;

## Getting Started <a href="#getting-started" id="getting-started"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this feature, so we’ll use a _no-code_ integration approach.

Install JS in HEAD, generally site-wide.

{% code overflow="wrap" %}
```html
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@v5.1-alpha.3/dist/nocode/webflow-blog.min.js"></script>
```
{% endcode %}

### STEP 2 - Add your Gist and Copy button. <a href="#step-2---create-an-embed-where-you-want-a-wfu-rating-component-to-appear" id="step-2---create-an-embed-where-you-want-a-wfu-rating-component-to-appear"></a>

Follow the instructions above to add your gist and copy button, and tag them appropriately.&#x20;



\
