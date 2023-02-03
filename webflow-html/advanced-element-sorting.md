# Advanced Element Sorting

{% embed url="https://wfu.sygnal.com/docs/webflow-html/sort/" %}

Sort Collection List in unique situations.

Such as Embedded Collection Lists, which have no sort option.

Supports;

* Sorting by string or date values ( defaults to string )
* Sorting ascending / descending ( defaults to ascending )
* Sorting randomly ( on every page refresh )

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-sort` attribute <a href="#wfu-sort-attribute" id="wfu-sort-attribute"></a>

Place on any Collection List directly ( not the Collection List Wrapper ). No value needed.

#### `wfu-sort-dir` attribute <a href="#wfu-sort-dir-attribute" id="wfu-sort-dir-attribute"></a>

If you want to change the direction, add this attribute with a value of;

* `asc` for ascending
* `desc` for descending
* `random` for random ( on every page refresh )

Defaults to ascending when unspecified or unrecognized.

#### `wfu-sort-type` attribute <a href="#wfu-sort-type-attribute" id="wfu-sort-type-attribute"></a>

If you want to specify the data type of the field being sorted, add this attribute with a value of;

* `string` for values that should be sorted as strings
* `number` for values that should be sorted as numbers
* `date` for values that should be sorted as dates
* `semver` for values that should be sorted as [semantic versions](https://semver.org/) \*\*

Defaults to `string` when unspecified or unrecognized.

\*\* Note that semver sorting is a numeric-only implementation of the sort rules. It is not designed to handle alphanumerics in pre-release identifiers.

#### Creating your Sort Key <a href="#creating-your-sort-key" id="creating-your-sort-key"></a>

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
