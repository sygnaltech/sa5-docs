---
description: Extend and control Webflow's Form Select Element
---

# Form Select Element





## Usage Notes

On the Form Select element you want to augment, add the attribute;

`wfu-form-select` = ( name )

Assign a meaningful name. The name is only used for referencing this element.&#x20;

### Multi-Select Capabilities

If you nave your select element set to multiple in Webflow, it will display as a list-style element and support the selection of multiple items.&#x20;

In default browser behavior, the UX for this is extremely awkward, as it requires the use of CTRL and SHIFT modifier keys.&#x20;

SA5 allows you to change this behavior, so that a click will select/deselect each item individually.&#x20;

To the select element, add;

`wfu-form-select-mode` =&#x20;

* `toggle`

Usable only for selects which have the multiple option enabled.&#x20;

### Theming

The coloring for this is weird.&#x20;

`wfu-form-select-theme` =&#x20;

* `blue` - applies a blue background to the selected items&#x20;



## Future

Consider using special Webflow variables to dictate styling options in SA5?&#x20;

What is the CSS specificity for libraries and CSS vars ?&#x20;

background color

text color

padding

select and de-selected&#x20;



