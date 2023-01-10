# Numeric Sequencing

{% embed url="https://wfu.sygnal.com/docs/webflow-html/seq/" %}

Allows you to apply a numeric sequence across a series of elements.

Numbering is always in a traditional 1, 2, 3… style of sequencing.

NOTE: This is primarily useful for sorting and filtering demos, because CSS has a numeric sequencing feature built in for live display.

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-seq-group` attribute <a href="#wfu-seq-group-attribute" id="wfu-seq-group-attribute"></a>

Place on any element. Give an arbitrary named group, for matching the items after, e.g. `articles`

#### `wfu-seq` attribute <a href="#wfu-seq-attribute" id="wfu-seq-attribute"></a>

Place on any child element within that group. Give it the same group name as its parent.

#### Notes <a href="#notes" id="notes"></a>

The HTML DOM is a large tree of element and sub-elements.

* You can use `wfu-seq-group` multiple times throughout your document.
* You can use the same group name on multiple `wfu-seq-group`’s, provided that those subtrees are independent. Do not use the same name if one group is nested within the other.
* You can have nested `wfu-seq-group`’s, as long as you use a different group name.

The purpose of these capabilities is to allow you to use numbering on a Webflow collection list that contains a nested list. You can give one numbering sequence to the parent list, and a numbering sequence to each of the child lists as well.

NOTE: Primarily I’d recommend this for demos, where you need to number items and then permute them. In most numbering situations, CSS numbering is generally a better alternative for general sequencing.

#### Future <a href="#future" id="future"></a>

If there is a need, I can expand this to allow for control of;

* Starting number
* Step size
* Increasing or decreasing count
* Support for decimal values

web AT sygnal.com

* Avoid using the same

Avoid using the same group name on an element that is a child of another element.

You can sequence nested lists separately

Create an HTML Embed inside of your Collection List Item, with this code;

```
<data wfu-sort-key=""></data>
```

As the attribute value for `wfu-sort-key`, insert the field that you want to sort by, using Webflow’s ‘**+ Add Field** at the top-right of the HTML Embed Code Editor window.

Remember to specify `date` in the above configuration if you’re wanting to sort by dates.

Any other field you choose will be sorted alphabetically.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

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

#### STEP 2 - Apply `wfu-sort` and configuration attributes to the elements you want to filter <a href="#step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-sort-and-configuration-attributes-to-the-elements-you-want-to-filter"></a>

See above for details.

\
