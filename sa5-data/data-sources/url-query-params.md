---
description: Pass querystring params through to forms and text elements, automatically
---

# URL Querystring Data Source

Extract querystring parameters from the current URL, and apply the contents to tagged elements on your page. &#x20;

## Use Cases

* Use querystring data in your FORM data, to collect it for submissions ( e.g. `utm_` params )
* Pass querystring data through to other links on the page, so it will get carried through
* Use querystring data in visible fields, e.g. to personalize a page from an Email newsletter link click ( “Hey Mary!” )

Examples

$query

{% hint style="success" %}
**Shortcut.** `?` can be used as a shortcut in place of `$query.`, for example `?name` is equivalent to `$query.name`&#x20;
{% endhint %}



## Demonstration

{% embed url="https://data-binding.webflow.io/query" %}

{% embed url="https://webflow.com/made-in-webflow/website/data-binding" %}

## Demos  <a href="#usage-notes" id="usage-notes"></a>

{% embed url="https://url-tracking.webflow.io/query" %}
Demonstration page
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/url-tracking" %}
Cloneable site
{% endembed %}



## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library  <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).&#x20;

### STEP 2 - Apply `wfu-bind` to Desired Elements <a href="#step-2---apply-wfu-query-param-to-desired-elements" id="step-2---apply-wfu-query-param-to-desired-elements"></a>

{% hint style="success" %}
For example, use `wfu-bind=?name` if you want to apply the value of querystring param `name` to that element.
{% endhint %}

See below for details.&#x20;

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

### `wfu-bind` = ( _data source_ )&#x20;

**Required.** Place on any element where you want data binded from a source. &#x20;

For query





Configure everything using simple custom attributes.

This tool will carry any URL querystring params into your webpage, and apply them as follows;

* On any INPUT elements with a custom attribute of `wfu-bind=X`, WFU will replace the `value` attribute with the value of the querystring param `X`.&#x20;
* This works with `type=hidden` INPUT elements as well, so the data can be passed through invisibly.

```html
<input wfu-bind="?name" type="hidden" name="test2-field">
```

* The querystring param you use in `wfu-bind` is case-sensitive. `?name` and `?Name` are different.&#x20;
* Checkbox elements will be set to the boolean truthy value.
* Select elements will be set to the matching select value.&#x20;
* On any other elements with a custom attribute of `wfu-bind=X`, WFU will replace the inner text of the element with the value of the querystring param `X`.&#x20;
