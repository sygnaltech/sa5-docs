---
description: How SA5's databinding works
---

# Binding Data

SA5 supports binding data in two ways;&#x20;

* **Element binding** replaces the entire content of the element. It is also element-type-aware, so that for example binding to a _text element_ replaces the inner text content, while binding to a _form input element_ sets the value of that input element.&#x20;
* **Content binding** selectively binds data to the content within an element, using handlebars style macro-expressions of the format `{{ data-path }}`. This is useful for e.g. rich text elements and descriptive text where you only wish to replace specific words. It is also designed to support CMS content.   &#x20;

{% hint style="info" %}
Currently, all binding is specific to a **Data Item**, which always resolves to a text value. In the future, lists, tables, objects and media elements may be added. &#x20;
{% endhint %}

{% hint style="info" %}
Data-Binding is read-only. It's designed to integrate information into your site from various internal and external sources - but not to update those data sources.
{% endhint %}

## `wfu-bind = (data-path)`

Apply the `wfu-bind` attribute to any element which you want to replace the full content of with your data-bound content.&#x20;

You can place `wfu-bind` on;

* Simple content elements;
  * Text elements&#x20;
  * Paragraph elements
  * Heading elements&#x20;
* Form elements, including;
  * INPUT elements
  * SELECT elements - case sensitive&#x20;
  * TEXTAREA elements
  * CHECKBOX elements

{% hint style="info" %}
Complex elements, including sliders, tabs, and rich text blocks don't make sense here, since there isn't a clear point for content-binding a simple string value. Some elements such as images and video elements may be supported in the future.&#x20;
{% endhint %}

The **data-path** value can be any valid SA5 data path that identifies a data point.&#x20;

Examples;

`wfu-bind=$query.name`

`wfu-bind=+events.item.slug`

`wfu-bind=$local.test`

Here's an example of an element that is bound to the current user's custom data, specifically a the custom data you've named `link-field`.&#x20;

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
**Setting defaults.** The value will only be applied if one is found, therefore you can specify a default value by setting initial content for the element itself. Here we have `...` but it can be whatever you prefer.
{% endhint %}

## `wfu-bind-content = (data-context)`

SA5's _contextual binding_ is used to provide macro expansion support within the content of a plain-text or rich-text template element.

Templates are text marked up with field that contain SA5 data paths, like this;&#x20;

`{{ $user.data.link-field }}`

When the template is processed, these are expanded.&#x20;

{% hint style="success" %}
For certain data sources such as `$db`, it's common to specify a **data context** on the element. This allows the context to change to e.g. a collection list item before the content binding occurs.&#x20;
{% endhint %}

## Data Paths

At the center of data binding is SA5's data paths, which are formatted strings that specifically identify the data that you want to bind.&#x20;

A data path is a dot-notated string with several parts;

`<data-source type>.<data-source-name>.<object-id>.<field-id>`

<table><thead><tr><th width="196.33333333333331">Path Root</th><th width="100">Abbr</th><th width="170">Data Source Type</th><th>Data Path Examples</th></tr></thead><tbody><tr><td><code>$user</code></td><td><code>@</code></td><td>User object</td><td><ul><li><code>$user.name</code> - The current user's name</li><li><code>@data.birthdate</code> - A custom User field named birthdate</li></ul></td></tr><tr><td><code>$cookie</code></td><td></td><td>Cookie</td><td><ul><li><code>$cookie.foo</code> - The cookie named <code>foo</code></li></ul></td></tr><tr><td><code>$local</code></td><td></td><td>Local storage</td><td><ul><li><code>$local.myval</code> - A Webstorage Local-stored value named myval.</li></ul></td></tr><tr><td><code>$session</code></td><td></td><td>Session storage</td><td><ul><li><code>$session.myval</code> - A WebStorage Session-stored value named myval.</li></ul></td></tr><tr><td><code>$query</code></td><td><code>?</code></td><td>Query string </td><td><ul><li><code>$query.foo</code> - The query param named foo.</li><li><code>?foo</code> - The query param named foo.</li></ul></td></tr><tr><td><code>$db</code></td><td><code>+</code></td><td>Database</td><td><ul><li><code>$db.my-db.my-record.my-field</code> - Describes a value in an SA5 Datasource. </li></ul></td></tr><tr><td><code>$global</code></td><td></td><td>Site global vars</td><td><ul><li><code>$global.year</code> - The year property of a Global object you've created.</li></ul></td></tr></tbody></table>

{% hint style="success" %}
Abbreviations are shorthand for the full datasource type name, so e.g. `$user.name` and `@name` are considered identical.&#x20;
{% endhint %}

## SEO Notes

Bound data may or may not be picked up by search indexing bots. Google is generally good at executing script and indexing the page after modification, however you will need to test this yourself. &#x20;

## Deprecated Notes

{% hint style="danger" %}
Ignore the notes below, we're reviewing and integrating during migration.
{% endhint %}

### Dynamic DSD References, using Data-Binding Context

You can specify fixed reference items using a fully-qualified DSD like this, however if the template is in a dynamic context such as a collection list or collection page, SA5 allows you to set the context for partial DSDs to operate in.&#x20;

The way this works is to assign these attributes to the parent of your `wfu-bind-content` tagged element.

* `wfu-bind-dsn` = The data source name, e.g. `my-data`.&#x20;
* `wfu-bind-item-id` = The data source item ID, e.g. `row-28`.&#x20;

{% hint style="info" %}
These context elements can be on the same element as your `wfu-bind-content` tag, but they can also be on any ancestor element. They also do not need to be on the same element. This gives you different flexibilities&#x20;
{% endhint %}











