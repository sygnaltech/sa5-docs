# CMS-Bound Custom Attributes ⛔

{% hint style="success" %}
**NOW NATIVE TO WEBFLOW!**

As of 16-Mar-2023, Webflow has added support for [CMS-bound custom attributes and ID's](https://webflow.com/feature/use-cms-data-in-custom-attributes)! Phenomenal, guys!
{% endhint %}

{% hint style="info" %}
**DEPRECATED** ⛔

This Attribute no longer needs development. It will remain in the Sygnal Attributes library to support projects already using it, however we recommend switching to the new Webflow-native feature when possible.&#x20;
{% endhint %}

**This library allows you to dynamically apply custom attributes to HTML elements.**

* This is most valuable within a Webflow Collection List, where the attributes are changing and unknown in advance.
* Attributes are applied in WFU’s post-processing script, executed immediately after the page loads.
* WFU has no restrictions on what custom attributes you can add, or which elements you can add them to. This means that Webflow’s reserved fields are not a barrier here.&#x20;

Dynamic attributes are not natively visible. _View source_ in order to see the dynamic attributes in the HTML of this demo page.

For demonstration purposes, I’ve applied the attributes as `style` attributes, which apply a visible background color.

### Limitations <a href="#limitations" id="limitations"></a>

* None identified.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

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

#### STEP 2 -Add an HTML Embed with your custom Attributes <a href="#step-2--add-an-html-embed-with-your-custom-attributes" id="step-2--add-an-html-embed-with-your-custom-attributes"></a>

Put an HTML Embed right after, or right inside of the element you wish to affect.

Paste in the following code.

```html
<data 
  wfu-attr="style" 
  wfu-attr-target="prev" 
  wfu-attr-val="background-color: yellow;"
  ></data>
```

* `wfu-attr` indicates the name of the attribute you want to add
* `wfu-attr-target` identifies the element you want to apply it to, one of;
  * `prev` indicates the prior sibling.
  * `next` indicates the following sibling.
  * `parent` indicates the containing element.
* `wfu-attr-val` is the value you want applied. Use Webflow’s CMS field embed for this, for dynamic values.

NOTE: Any existing attribute will be overwritten.

* Yes you can put multiple attributes in the same embed, and even target them differently

### Future <a href="#future" id="future"></a>

May allow value modification;

* Prepend, append
* Regex transforms

May allow advanced targeting;

* jQuery or CSS selectors

\


