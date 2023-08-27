---
description: Add embedded GitHub Gist capabilities to your blog.
---

# GitHub Gists ❺

Does your article content contain JavaScript, CSS, HTML, XML, JSON, configuration files, or source code-formatted data of any kind?

Now you can easily add these content blocks to your Webflow rich text elements, with _full syntax highlighting_ and _easily make changes_ later.&#x20;

{% hint style="info" %}
This feature makes use of the [GitHub Gist service](https://gist.github.com/), which is widely used and 100% free.
{% endhint %}

With SA5's Rich Text lib, you can simply drop an HTML embed anywhere in your rich text content and paste in the Gist's embed. That's it.&#x20;

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
* Paste in the gist share code, which is a simple line of script.

### Themes

In addition to the default Gist appearance, SA5 currently supports two themes;

* `midnight`, inspired by CodePen
* `darkmode`&#x20;

<details>

<summary>I want all of my Gists in this Rich Text element to have a specific theme</summary>

Add the class `wfu-gist-theme=(theme)` to the rich text element.&#x20;

</details>

<details>

<summary>I want the Gist in my standalone HTML Embed to have a specific theme</summary>

Add the class `wfu-gist-theme=(theme)` to the HTML Embed element.&#x20;

</details>

### Copy to Clipboard Feature

SA5 supports linking a button to your Gist to copy it.

When clicked, it will locate the identified HTML Embed, and extract, clean and format the code contents, and copy them to the clipboard.&#x20;

<details>

<summary>I want this Button to copy the contents of this Gist to the clipboard</summary>

* Tag your HTML Embed element with the custom attribute\
  `wfu-gist=(identifier)` using any unique identifier you want.
* Tag your button with the custom attribute \
  `wfu-gist-copy=(identifier)`

</details>

{% hint style="warning" %}
Currently this only works with explicitly named embeds, which means that it's not easily adaptable to CMS-sourced rich text content. We're adding a separate feature for that soon.&#x20;
{% endhint %}

## Themes

{% tabs %}
{% tab title="Default" %}

{% endtab %}

{% tab title="midnight" %}

{% endtab %}

{% tab title="darkmode" %}

{% endtab %}
{% endtabs %}

## Roadmap

{% tabs %}
{% tab title="Completed" %}
See above
{% endtab %}

{% tab title="Planned" %}
* More themes
* Auto copy-button feature
{% endtab %}

{% tab title="Considered" %}
* Custom themes&#x20;
{% endtab %}

{% tab title="More Ideas" %}

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
