---
description: Count and sum items in your collection lists.
---

# Count & Sum Items ❺🧪

{% hint style="info" %}
**These are 100% internal R\&D.**\
No public product is available, but if you need these features, contact us for details on how we can implement them for you.&#x20;
{% endhint %}

## Use Cases

* Count the number of items with a specific CMS field
  * Also works with option fields and single-ref fields&#x20;
* Sum a specific CMS field, such as price, or quantity&#x20;

## Usage Notes <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### `wfu-calc-method` = ( method )

**Required.** Method is one of;&#x20;

* `sum` - sum of values.
* `count` - count of items.

### `wfu-calc-source` = ( source type )

* `selector` - a CSS selector

### `wfu-calc-select` = ( css selector )

**Required** when using a _selector_ source.&#x20;

Identifies the elements on the page to use&#x20;

e.g. `[result=win]`

{% hint style="info" %}
The value of this identified attribute is typically populated from a CMS-bound custom attribute.
{% endhint %}

### `wfu-calc-field` = ( field )&#x20;

**Required** when using the _sum_ method.&#x20;

Indicates the attribute to retrieve the data item from.

### `wfu-preload` = ( preload method )

**Optional.** See [preloaders](../overview/preloaders.md).&#x20;





## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../404/quick-start-or-sa5-404.md).&#x20;

### STEP 2 - Add `wfu-404-search` to your Search input

Add a [Webflow Search](https://university.webflow.com/lesson/site-search) element, and on the input field add a custom attribute of `wfu-404-search`. No value is needed.

