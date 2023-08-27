---
description: How to Bind Data
---

# Binding Data

SA5 supports binding data in two ways;&#x20;

* **Element binding** replaces the entire content of the element. It is also element-aware, so that for example binding to a Text Element is different from binding to an Input Element.&#x20;
* **Content binding** selectively binds data to the content within an element, using handlebars style macro-expressions like \{{ name \}}. This is useful for e.g. rich text elements and descriptive text where you only wish to replace specific words. Can be used with CMS content.   &#x20;

{% hint style="info" %}
Currently, all binding is specific to a **Data Item**, which always resolves to a text value. In the future, lists, tables, objects and media elements may be added. &#x20;
{% endhint %}

{% hint style="info" %}
Data-Binding is inbound-only. They're designed to integrate information into your site from various sources - but not to update external data stores. This may expand in future versions.
{% endhint %}

## `wfu-bind = (DSD)`

Apply to any element which you want to replace the full content of with your data-bound content.&#x20;

can be given the `wfu-bind` attribute, with a Data Source Descriptor.&#x20;

You can place `wfu-bind` on;

* Text elements&#x20;
* Paragraph elements
* Heading elements&#x20;

Form elements, including;

* INPUT elements
* SELECT elements - case sensitive&#x20;
* TEXTAREA elements
* CHECKBOX elements

The DSD value can be any valid DSD that identifies a data point.&#x20;

Examples

`wfu-bind=$query.name`

`wfu-bind=+events.item.slug`

`wfu-bind=$local.test`

Here's an example of an element that is bound to the current user's custom data, specifically a the custom data you've named `link-field`.&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
**Setting defaults.** The value will only be applied if one is found, therefore you can specify a default value by setting initial content for the element itself. Here we have `...` but it can be whatever you prefer.
{% endhint %}

## `wfu-bind-content`

Used to bind a plain-text or rich-text template element.

Templates are text marked up with field DSD's like this;&#x20;

`{{ $user.data.link-field }}`

When the template is processed, these are expanded.&#x20;

## Data Paths

At the center of data binding is SA5's data paths, which are formatted strings that specifically identify the data that you want to bind.&#x20;

A data path is a dot-notated string with several parts;

`<data-source type>.<data-source-name>.<object-id>.<field-id>`

|        |   |   |
| ------ | - | - |
| $user  |   |   |
| @name  |   |   |
| $db    |   |   |
| $query |   |   |
| $url   |   |   |

### Dynamic DSD References, using Data-Binding Context

You can specify fixed reference items using a fully-qualified DSD like this, however if the template is in a dynamic context such as a collection list or collection page, SA5 allows you to set the context for partial DSDs to operate in.&#x20;

The way this works is to assign these attributes to the parent of your `wfu-bind-content` tagged element.

* `wfu-bind-dsn` = The data source name, e.g. `my-data`.&#x20;
* `wfu-bind-item-id` = The data source item ID, e.g. `row-28`.&#x20;

{% hint style="info" %}
These context elements can be on the same element as your `wfu-bind-content` tag, but they can also be on any ancestor element. They also do not need to be on the same element. This gives you different flexibilities&#x20;
{% endhint %}



Bind the entire element using wfu-bind, will replace the entire content.&#x20;

In Webflow static ( not CMS-bound ) rich text and plain-text elements you can select text and create a bold, italic, or span sub-element.

When that is created, you can select is separately, and you can assign custom attributes directly to it. In this way you can directly bind parts of a text or rich text element.&#x20;

Another way is macro-expansion \{{ name \}}&#x20;







## SEO Notes

Bound data may or may not be picked up by search indexing bots. Google is generally good at executing script and indexing the page after modification, however you will need to test this yourself. &#x20;

## Technical Notes

SA5 uses Handlebars for the template processing.&#x20;

{% embed url="https://handlebarsjs.com/" %}





