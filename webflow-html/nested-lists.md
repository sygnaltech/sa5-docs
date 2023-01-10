# Nested Lists

Supported nested lists markup in Webflow’s Lists and within Rich Text elements.

Indicate nesting depth by prefixing list items with `>`’s.

Also supports + and - prefixing for special PRO and CON lists.

### DEMO - Nested Lists <a href="#demo---nested-lists" id="demo---nested-lists"></a>

Nested Lists in Webflow, with prefix markup.

[https://wfu.sygnal.com/docs/webflow-html/nestedlists/](https://wfu.sygnal.com/docs/webflow-html/nestedlists/)\
Getting Started ( NOCODE )

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/dist/css/webflow-html.css">
```

Add this JS reference to the BODY of your site or page.

```
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/src/nocode/webflow-html.js"></script>
```

#### STEP 2 - Apply `wfu-lists=nested` to Desired Elements <a href="#step-2---apply-wfu-listsnested-to-desired-elements" id="step-2---apply-wfu-listsnested-to-desired-elements"></a>

Positioning is important, make sure you’re placing this custom attribute on the correct element.

* To nest a standalone list element, place it directly on the top level element in the list structure.
* To nest lists within a Rich Text element, place it directly on the Rich Text element itself.

Can be placed on Rich Text elements (directly on the main element), or on

`wfu-lists=nested`

\
