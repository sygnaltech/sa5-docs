---
description: Extend and control Webflow's Form Select Element
---

# Form Select Element

HTML `<select>` fields are form elements that allow users to choose one or more options from a dropdown list. They are used to present a list of choices, enabling users to select the most appropriate option(s) for their input.&#x20;

### Multi-Selects - Why this is needed.

When used with the `multiple` attribute, they allow for the selection of multiple items simultaneously.

{% hint style="success" %}
In Webflow, this is enabled under the element's settings.&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

In most web browsers, users typically need to hold down the `Ctrl` (Windows) or `Cmd` (Mac) key to select multiple non-contiguous options or use the `Shift` key to select a range of options.

This UX can be difficult and inconvenient for users, especially those unfamiliar with keyboard modifiers or those using mobile devices. It can lead to accidental deselection or selection errors, and lead to confusion and frustration.&#x20;

{% hint style="success" %}
SA5 fixes this by overriding the browser's default UX behavior.&#x20;
{% endhint %}

## Demos

{% embed url="https://sa5-forms.webflow.io/select" %}
Click to see this feature in action.&#x20;
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/sa5-forms" %}
Cloneable site in Made in Webflow.&#x20;
{% endembed %}

## Usage Notes

{% hint style="info" %}
Currently, SA5's primary feature regarding `<select>` elements is to "fix" the problematic multi-select UX behavior.&#x20;
{% endhint %}

On the **Form Select** element you want to augment, add the attribute;

`wfu-form-select` = ( name )

Assign a meaningful name. The name is only used for referencing this element.&#x20;

### Multi-Select Capabilities

If you have your select element set to multiple in Webflow, it will display as a list-style element and support the selection of multiple items.&#x20;

SA5 allows you to change the browser's default multi-select behavior, so that a click will select/deselect each item individually.&#x20;

To the select element, add;

`wfu-form-select-mode` = ( ... )

* `toggle` - enables the click-to-toggle-selection mode&#x20;

{% hint style="info" %}
Usable only for selects which have the `multiple` setting enabled.&#x20;
{% endhint %}

### Theming

Multi-Selects also have a less-than-obvious styling for selected items.  If this does not suit you, SA5 has a simple theme setting that will change the selected item background to blue.&#x20;

`wfu-form-select-theme` = ( ... )

* `blue` - applies a blue background to the selected items&#x20;

{% hint style="info" %}
If you want to specify your own selected-option styling, you can do so with custom CSS.&#x20;
{% endhint %}

## Future&#x20;

Consider using special Webflow variables to dictate styling options in SA5?&#x20;

What is the CSS specificity for libraries and CSS vars ?&#x20;

background color

text color

padding

select and de-selected&#x20;



