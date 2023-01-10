# Hide Section w/ Empty Collection Lists

Want to hide a section when the Collection List it contains is empty?

Suppose you have an area of your page called “alerts” and it has some nice styling and icons… but how do you make the whole thing disappear when there are no alerts pulled by the Collection List for display?

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-hide` attribute <a href="#wfu-hide-attribute" id="wfu-hide-attribute"></a>

To the section you want to hide, add the custom attribute;

```
wfu-hide = empty-collection-list
```

If ALL of the collection lists within that section are empty, the entire section will be hidden.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

This is a CSS-only solution.

Add this CSS script to the HEAD of your site or page.

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/dist/css/webflow-html.css">
```

#### STEP 2 - Apply `wfu-hide` section or element you want to hide <a href="#step-2---apply-wfu-hide-section-or-element-you-want-to-hide" id="step-2---apply-wfu-hide-section-or-element-you-want-to-hide"></a>

See above for details.

\
