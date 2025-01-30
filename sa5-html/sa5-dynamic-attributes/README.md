---
description: Create any custom attribute, even if it's reserved by Webflow
---

# Dynamic Attributes

Webflow's custom attributes feature has a powerful data-binding capability that supports binding to CMS fields and component properties- but there are several key limitations;&#x20;

1. **Reserved attributes.** many important attribute names are reserved to protect novice web designers. See the notes section below for a list. &#x20;
2. **ECommerce.**  Collection pages and collection lists that are bound to ECommerce Product and Categories do not support attribute data binding.&#x20;

**SA5's Dynamic Attributes** feature overcomes this by allowing you to create proxy attributes that are then applied to the page once the page has loaded.&#x20;

## Use Cases

This is a more technical feature, but it has an incredible range of uses. Here are a few;

* Forms
  * Initialize form field values on INPUTs, TEXTAREAs, SELECTs, CHECKBOXes and other elements with data from a CMS collection item or component property. &#x20;
    * e.g. Use `x:value` = ( your value ) to initialize an INPUT, TEXTBOX, or SELECT element from a CMS collection item.    &#x20;
    * e.g. Use `x:checked` = ( boolean value ) to initialize a checkbox element.&#x20;
  * Special field configuration&#x20;
    * e.g. Use `x:type` = `date` on an INPUT element to change it to a date type&#x20;
  * Set hidden form fields to capture data silently, such as the Collection page you're on when the form is submitted. &#x20;
* Element behavior
  * Such as onclick&#x20;
* Supporting other SA5 libraries, such as CMS Lightbox Captions and Groups&#x20;
  * And making these work with ECommerce content    &#x20;

{% hint style="warning" %}
As of 2024-Jun-03, Webflow does not yet support attribute binding to switch ( boolean ) field types or to select ( option ) field types. In a pinch you could use CMS text fields instead.&#x20;
{% endhint %}

## How it Works <a href="#usage-notes" id="usage-notes"></a>

SA5 Dynamic Attributes can be applied in two ways.

1. **Custom Attributes.** Any attribute created with an `x:` prefix on the name is specially recognized as an SA5 Dynamic Attribute.  It will be processed, and the un-prefixed attribute will then be set to that value. \
   e.g. A custom attribute named `x:value` would override the `value` attribute.&#x20;
2. **Custom Embeds.** Webflow's embed element can be used to contain a special `<script>` element, which will be processed and then apply the attribute value to the specified element. As an embed, this is more compatible with ECommerce data-binding.&#x20;

## Getting Started <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).&#x20;

### STEP 2 - Apply `x:` prefixed custom attributes to any elements <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

These will overwrite existing attributes on that element.\
e.g. `x:onclick` will be applied as `onclick` on that same element.&#x20;

Data-bind the value where to CMS fields or component properties where it makes sense.  &#x20;

{% hint style="warning" %}
In previous versions, SA5 also supported dynamic attribute prefixes of `x-` however we've moved away from that to avoid conflict with Alpine.js which also uses the `x-` prefix on attributes. Currently this is still supported but considered obsolete.&#x20;
{% endhint %}

### STEP 3 - Create Embeds where custom attributes cannot work&#x20;

SA5 Dynamic Attributes use a special embed `<script>` structure containing a JSON chunk that specifies the target element ( relative to the Embed ), the name of the attribute to set, and the value of that element.&#x20;

In this example, the `style` attribute would be created on the parent element containing the Embed, and would be set to a value of `font-weight: bold;`. &#x20;

```html
<script type="application/sa5+json" handler="DynamicAttribute">
{
  "@context": "https://attr.sygnal.com",
  "@type": "DynamicAttribute",
  "@version": "0.1",
  "name": "style", 
  "target": "parent", 
  "value": "font-weight: bold;"    
}
</script>
```

See the usage notes for specific details and advanced use.

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### `x:*` attributes <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

Create a custom attribute beginning with `x:` on any element in your page.  Set the value you want, and bind it to a CMS field or component property if you want.&#x20;

### `x:*:pre` attributes <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

Attributes that are also suffixed with `:pre` are prepended to the attribute value.&#x20;

### `x:*:post` attributes <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

Attributes that are also suffixed with `:post` are appended to the attribute value. &#x20;

### Embeds&#x20;

SA5's embed feature has the same capabilities, defined in a JSON chunk.&#x20;

It must be placed in an Embed, and positioned relative to the element you want the attribute to be applied to, either as a child or as an adjacent sibling.&#x20;

Here's an example;&#x20;

```html
<script type="application/sa5+json" handler="DynamicAttribute">
{
  "@context": "https://attr.sygnal.com",
  "@type": "DynamicAttribute",
  "@version": "0.1",
  "name": "style", 
  "target": "parent", 
  "value": "font-weight: bold;", 
  "pre": "font-style: italic;",
  "post": "color: blue;"  
}
</script>
```

Notes;&#x20;

* Both the script `type` and `handler` are essential&#x20;
* `target` can be `parent`, `prev`, or `next`, and identifies the element that the attribute will be applied to&#x20;
* `name` indicates the name of the attribute to create or replace&#x20;
* `value` ( opional ) indicates the value to set&#x20;
* `pre` ( opional ) prefixes the existing or replaced value&#x20;
* `post` ( opional ) suffixes the existing or replaced value &#x20;

### Special Element Handling <a href="#wfu-sort-dir-attribute" id="wfu-sort-dir-attribute"></a>

To assist with the use case of initializing form fields, we've added special handling exceptions for specific element types;&#x20;

#### Textarea Elements

Just like an input element, you can use the `x:value` attribute to initialize the content of a Textarea.&#x20;

In browsers, Textarea elements behave a bit differently than Input elements. You can initialize them with a value attribute _before_ page load, but if the attribute is set later by script, that value will not be applied. We set the value _property_ as well to ensure it's applied.&#x20;

#### Checkbox Elements ( Input type=checkbox )

Use  the `x:checked` attribute directly on the Checkbox element itself.  We'll evaluate it as **true** or **false**, and set or remove the `checked` attribute accordingly.&#x20;

#### Select Elements&#x20;

Use  the `x:value` attribute.  We'll select the matching option, by value, if it exists. &#x20;

{% hint style="info" %}
Note that Select options have both a Name and a Value.  It's the Value that is matched, not the Name.  Ensure your Values are set correctly.&#x20;
{% endhint %}

## Notes   <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### Reserved Attribute Names

If you've never encountered it, this is what happens in Webflow when you attempt to use a reserved attribute name. &#x20;

![](<../../.gitbook/assets/image (27).png>)

Here's a partial list of reserved attribute names, as [documented](https://discourse.webflow.com/t/list-feature-availability-limits/23610) by samliew;&#x20;

_abbr, accept, action, align, alt, autofocus, autoplay, bgcolor, border, char, charoff, charset, cite, class, cols, colspan, content, controls, coords, crossorigin, datetime, default, disabled, download, for, form, formaction, formenctype, formmethod, formnovalidate, formtarget, frame, group, headers, height, high, href, hspace, icon, id, ismap, kind, label, list, loop, low, manifest, media, method, multiple, muted, name, optimum, placeholder, poster, preload, radiogroup, readonly, required, reversed, rows, rowspan, sandbox, scheme, scope, scoped, scrolling, seamless, selected, shape, size, sizes, src, srcdoc, srclang, style, type, value, vspace, width, wrap, xmlns, onblur, onclick, ondblclick, ondrag, ondrop, onerror, onfocus, onfocusin, onfocusout, onhelp, oninput, onkeydown, onkeypress, onkeyup, onload, onmousedown, onmouseenter, onmouseleave, onmousemove, onmouseout, onmouseover, onmouseup, onmousewheel, onpaste, onredo, onscroll, onsubmit, onundo_

## Resources

{% embed url="https://university.webflow.com/lesson/custom-attributes" %}

{% embed url="https://webflow.com/feature/use-cms-data-in-custom-attributes" %}
