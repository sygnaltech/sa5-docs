---
description: Create any custom attribute, even if it's reserved by Webflow
---

# Dynamic Attributes

## Overview

Webflow's custom attributes feature is much more powerful with the new CMS binding capability- but many important attribute names are reserved to protect unwary web designers from themselves.&#x20;

In certain cases, the ability to set these attributes is _crucial_.

**SA5's Dynamic Attributes** feature overcomes this by allowing you to create proxy attributes that are then applied to the page once the page has loaded.&#x20;

{% hint style="warning" %}
Webflow's ECommerce Products and Categories do not support Webflow's CMS bound custom attributes. See the Future subpage here for some work we're doing on that.&#x20;
{% endhint %}

### Reserved Attribute Names

If you've never encountered it, this is what happens in Webflow when you attempt to use a reserved attribute name.&#x20;

![](<../../.gitbook/assets/image (27).png>)

Here's a partial list of reserved attribute names, as [documented](https://discourse.webflow.com/t/list-feature-availability-limits/23610) by samliew;&#x20;

_abbr, accept, action, align, alt, autofocus, autoplay, bgcolor, border, char, charoff, charset, cite, class, cols, colspan, content, controls, coords, crossorigin, datetime, default, disabled, download, for, form, formaction, formenctype, formmethod, formnovalidate, formtarget, frame, group, headers, height, high, href, hspace, icon, id, ismap, kind, label, list, loop, low, manifest, media, method, multiple, muted, name, optimum, placeholder, poster, preload, radiogroup, readonly, required, reversed, rows, rowspan, sandbox, scheme, scope, scoped, scrolling, seamless, selected, shape, size, sizes, src, srcdoc, srclang, style, type, value, vspace, width, wrap, xmlns, onblur, onclick, ondblclick, ondrag, ondrop, onerror, onfocus, onfocusin, onfocusout, onhelp, oninput, onkeydown, onkeypress, onkeyup, onload, onmousedown, onmouseenter, onmouseleave, onmousemove, onmouseout, onmouseover, onmouseup, onmousewheel, onpaste, onredo, onscroll, onsubmit, onundo_

## Use Cases

This is a more technical feature, but it has an incredible range of uses. Here are a few;

* Use `x-value` = ( your value ) to initialize an INPUT, TEXTBOX, or SELECT element from a CMS collection item. &#x20;
* Use `x-checked` = ( boolean value ) to initialize a checkbox element.&#x20;
* Use `x-type` = `date` on an INPUT element to change it to a date type&#x20;

{% hint style="warning" %}
As of 2024-Jun-03, Webflow does not yet support attribute binding to switch ( boolean ) field types or to select ( option ) field types. In a pinch you could use CMS text fields instead.&#x20;
{% endhint %}

## Demonstration <a href="#usage-notes" id="usage-notes"></a>



## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### `x-*` attributes <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

Place on any Collection List directly ( not the Collection List Wrapper ). No value is needed.

Any attribute prefixed with `x-` will be processed into the same attribute-value, without the prefix.

e.g. `x-value` = `foo` will be applied as `value` = `foo`&#x20;

When you use this feature with Webflow's CMS-bound attributes, you can initialize the input field's value from any CMS field you choose.&#x20;

### Special Element Handling <a href="#wfu-sort-dir-attribute" id="wfu-sort-dir-attribute"></a>

To assist with the use case of initializing form fields, we've added special handling exceptions for specific element types;&#x20;

#### Textarea Elements

Just like an input element, you can use the `x-value` attribute to initialize the content of a Textarea.&#x20;

In browsers, Textarea elements behave a bit differently than Input elements. You can initialize them with a value attribute _before_ page load, but if the attribute is set later by script, that value will not be applied. We set the value _property_ as well to ensure it's applied.&#x20;

#### Checkbox Elements ( Input type=checkbox )

Use  the `x-checked` attribute directly on the Checkbox element itself.  We'll evaluate it as **true** or **false**, and set or remove the `checked` attribute accordingly.&#x20;

#### Select Elements&#x20;

Use  the `x-value` attribute.  We'll select the matching option, by value, if it exists. &#x20;

{% hint style="info" %}
Note that Select options have both a Name and a Value.  It's the Value that is matched, not the Name.  Ensure your Values are set correctly.&#x20;
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).&#x20;

### STEP 2 - Apply `x-` prefixed custom attributes to any elements <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

## Resources

{% embed url="https://university.webflow.com/lesson/custom-attributes" %}

{% embed url="https://webflow.com/feature/use-cms-data-in-custom-attributes" %}
