# Limit Items by Breakpoint

{% embed url="https://wfu.sygnal.com/docs/webflow-html/limit-items-by-breakpoint/" %}

Webflow has a built-in Limit Items feature on Collection Lists, however it is not breakpoint-sensitive.

Our solution dynamically adjusts the number shown for the breakpoint that the site is being viewed at, with no refresh needed.

This feature is also very useful when used with `wfu-sort`, using the `random` setting. With the combination of random sorting and item limits, you can display a random set of items on every page refresh.

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

NOTE: Use only one of these two approaches;

#### `wfu-limit-items` attribute <a href="#wfu-limit-items-attribute" id="wfu-limit-items-attribute"></a>

Place on any Collection List directly ( not the Collection List Wrapper ).

Specify the number of items you want to show from 1 to 12.

#### OR, use the breakpoint variations <a href="#or-use-the-breakpoint-variations" id="or-use-the-breakpoint-variations"></a>

If you want breakpoint-specific counts, use ALL 4 of these attributes.

* `wfu-limit-items-D` the number to show for desktops
* `wfu-limit-items-T` the number to show for tablet
* `wfu-limit-items-L` the number to show for mobile landscape
* `wfu-limit-items-P` the number to show for mobile portrait

Place on any Collection List directly ( not the Collection List Wrapper ).

Specify the number of items you want to show from 1 to 12.

#### Advanced note <a href="#advanced-note" id="advanced-note"></a>

If you want to have the item limits also shown in the Designer, you can add a special chunk of CSS code into an HTML Embed. See the Cloneable, above. You’ll find this CSS in the HTML Embed at the very bottom of the homepage.

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

#### STEP 2 - Apply the attributes for the limits you want applied <a href="#step-2---apply-the-attributes-for-the-limits-you-want-applied" id="step-2---apply-the-attributes-for-the-limits-you-want-applied"></a>

See above for details.

\
