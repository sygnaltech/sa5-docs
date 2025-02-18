---
description: Count and sum items in your collection lists.
---

# Count & Sum Items ❺

{% hint style="warning" %}
While the base functionality for **SA5 Calc** is fully implmented, there are a number of advanced features indicated with a ~~strikethrough~~ that are not yet available.&#x20;
{% endhint %}

## Use Cases&#x20;

* Count the number of items with a specific CMS field
  * Also works with option fields and single-ref fields&#x20;
* Sum a specific CMS field, such as price, or quantity&#x20;
* Average a specific CMS field, such as price, or quantity&#x20;
* Count the total number of items in a collection 🧪

{% hint style="success" %}
See [Use Cases](calc-use-cases.md) for an understanding of common setup possibilities.&#x20;
{% endhint %}

## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start-or-sa5-calc.md).&#x20;

### STEP 2 - Add the Attributes&#x20;

Add the attributes you want, for the calculation you want to display.&#x20;

This library generally involves two elements; &#x20;

* A **display element**, where the calculation such as the count of items is shown on the page. This is generally a simple Webflow text element.&#x20;
* One or more **source element(s)**, which the calculation is performed with. These are also generally simple Webflow text elements, but&#x20;

## Usage Notes   <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### `wfu-calc` = ( _method_ )&#x20;

**Required.** Defines the type of calculation that will be performed.&#x20;

_Method_ is one of;&#x20;

* `sum` - sum of values. &#x20;
* `count` - count of items.&#x20;
* `avg` - average of items ( mean ). &#x20;

{% hint style="info" %}
Place this on the **display element** where you wish the calculation result to appear. Typically this is a Webflow text element, but it can also be an INPUT element.&#x20;
{% endhint %}

### `wfu-calc-source-type` = ( _source type_ )&#x20;

**Optional.** Defaults to `field` when not specified.&#x20;

_Source Type_ is one of;&#x20;

* `field` - ( default ) the name of a field tagged with `wfu-calc-field`&#x20;
* ~~`selector` - a CSS selector~~&#x20;
* ~~`sitemap` - 🧪 indicates the sitemap as the source~~ &#x20;

Learn more about [Source Types](source-types.md).&#x20;

{% hint style="info" %}
Place this on the **display element** with the `wfu-calc` attribute. &#x20;
{% endhint %}

### `wfu-calc-source` = ( source )&#x20;

**Required.** The value specified here depends on the Source Type you've chosen.&#x20;

This table shows the different settings you can use, depending on the Source Type;&#x20;

| Source Type      | Value                                                               | Notes                                                                       |
| ---------------- | ------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `field`          | The name of the field to use, as tagged with `wfu-calc-field`       | e.g. `blog` would match all items which have `wfu-calc-field` = `blog`      |
| ~~`selector`~~   | Any valid CSS selector for identifying the unique elements we want. | <p>e.g. <code>[my-type=foo]</code> <br></p>                                 |
| ~~`sitemap` 🧪~~ | The path prefix to match, e.g. `/blog/`                             | e.g. `/blog/` would count all items with the path beginning with `/blog/`.  |

Learn more about [Source Types](source-types.md).&#x20;

{% hint style="info" %}
Place this on the **display element** with the `wfu-calc` attribute. &#x20;
{% endhint %}

### `wfu-calc-field` = ( field name )&#x20;

**Required** when the Source Type is `field`.&#x20;

Indicates the attribute to retrieve the data item from. &#x20;

{% hint style="info" %}
Place this on the **source elements** directly which you are counting or using in your calculated result.
{% endhint %}

See [Use Cases](calc-use-cases.md) for an understanding of common setup possibilities.&#x20;

### ~~`wfu-preload` = ( preload method )~~

**Optional.** See [preloaders](../../overview/preloaders.md).&#x20;

{% hint style="info" %}
Place this on the display element with the `wfu-calc` attribute. &#x20;
{% endhint %}





