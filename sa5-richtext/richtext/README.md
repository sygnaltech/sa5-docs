---
description: Add special features to your rich-text content.
---

# Richtext ❺🧪

{% hint style="warning" %}
**NOT YET AVAILABLE** 🧪\
Currently in ALPHA experimentation.&#x20;
{% endhint %}

## Goals

Suppression. Ability of SA5 to suppress unnecessary actions if it's being reverse proxied, as determined by a response header?&#x20;

* Smart extensions
  * URL recognition and conversion...&#x20;
    * Video URLs, Vimeo etc.&#x20;
    * FB Post
    * Tweet
    * Possible OG transaction support preview?
    * Ignore raw URLs with a space&#x20;
* xTxT markup
  * Hints&#x20;
  * Leading symbols for class matches like !, ?, #, &
    * Prefacing any RTE, we apply a subclass to that item
  * Example  blockquote with prefix?&#x20;
* Blockquotes
  * Merging of adjacent blockquotes, conversion to paragraphs&#x20;
  * Addition of citations&#x20;
* Auto-link expansions
  * Add **nofollow** by default ( config )&#x20;
  * Intelligent handler and expansion options
* Images
  * Automatic lightboxing option&#x20;
  * Possible zoom options
  * Other treatments
  * link ## or #\~# rule - ##!popup ###popup ###zoom ###popup2 ###popupzoom ###custom1
  * Can include custom handlers?&#x20;
  * Pre trigger handler
* Footnotes&#x20;
  * Identify all `##` links, and format them as footnotes&#x20;
  * Styling&#x20;

## Usage Notes



## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../../sa5-html/quick-start.md).&#x20;

### STEP 2 - Apply the custom attributes as desired <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

\
