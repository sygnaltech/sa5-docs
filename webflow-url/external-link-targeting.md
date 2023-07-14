# External Link Targeting

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

In most situations, you will automatically want external links to open in a new tab.

This library automatically looks for FQDN links such as `https://...` and adds a `target=_blank`.

It will only add a target if none is specified.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Install JS in BODY, site-wide or on the specific pages you want the script to affect.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/nocode/webflow-url.min.js"></script>
```
{% endcode %}

### STEP 2 - Create Links as desired <a href="#step-2---create-links-as-desired" id="step-2---create-links-as-desired"></a>

See above notes.

\
