# Decode HTML

{% embed url="https://wfu.sygnal.com/docs/webflow-html/decode-html/" %}

Do you have a chunk of HTML stored in the CMS, which you need decoded when it emits into your page?

Simply position and data-bind your HTML Embed as normal, and then add a cu

Good for…

* 3rd party embed like soundcloud, and YouTube
* JSON+LD embeds

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-decode` attribute <a href="#wfu-decode-attribute" id="wfu-decode-attribute"></a>

Add this to the HTML Embed element you want the contents decoded for. No value needed.

Note that the CSS will hide this element initially until after it’s decoded, at which point we make it visible.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

This is a CSS-only solution.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/dist/css/webflow-html.min.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/nocode/webflow-html.min.js"></script>
```
{% endcode %}

#### STEP 2 - Apply `wfu-decode` to the HTML Embed element you want to decode <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

\
