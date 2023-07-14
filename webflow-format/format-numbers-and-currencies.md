# Format Numbers & Currencies

Webflow supports the storage of numbers, including integers and decimals, in the CMS, but has virtually no formatting options.

For decimal values, Webflow allows you to specify the number of decimal places you want to see in the CMS-bound field, however there are no options for commas, units, or currency formats.

This library allows you to format those numbers in commonly recognized formats, including

* `usd` - US currency ( also useful for AUD, NZD, and others )
* `gbp` - British pound sterling
* `eur` - European currency
* `jpy` - Japanese currency
* `%` or `percent` - percentages
* `,` or `comma` - thousands formatting with commas

And more will come as [users request](mailto:wfu@sygnal.com).

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-format` attribute <a href="#wfu-format-attribute" id="wfu-format-attribute"></a>

Use `wfu-format` directly on the CMS-bound numeric field.

```
wfu-format = usd
```

Also, use Webflow’s designer to format the number of decimal places you want to see, as we’ll apply this in your formatted result.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/dist/css/webflow-format.min.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/nocode/webflow-format.min.js"></script>
```
{% endcode %}

### STEP 2 - Apply `wfu-format` to the elements you want to format <a href="#step-2---apply-wfu-format-to-the-elements-you-want-to-format" id="step-2---apply-wfu-format-to-the-elements-you-want-to-format"></a>

See above for details.

\
