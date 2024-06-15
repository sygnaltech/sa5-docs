---
description: Dynamically show and hide elements on your page based on a switch/case eval
---

# Switch ❺🧪

Current;

* Display elements conditionally depending on a switch/case eval expression
* Work with collections lists&#x20;
* Works inside of components &#x20;

{% hint style="danger" %}
This feature is not yet available to the public.&#x20;
{% endhint %}

## Use Cases

Hide or show elements conditionally.

Show one of several elements, depending on the SWITCH input value.&#x20;

{% hint style="success" %}
This supports CMS-driven use cases also. Both the switch input for evaluation, and the case values themselves, can be stored in the CMS and attribute-bound.&#x20;
{% endhint %}

## Usage Notes

### Define your dynamic elements

To the elements you want to dynamically show and hide, add these attributes;

#### `wfu-logic-switch` = ( value )

Place this on the outer element that contains your elements to be evaluated for conditional display.

The value is typically bound to the value you want to use as the switch.&#x20;

#### `wfu-logic-switch-case` = ( value )

Place this on the descendent elements that you want to conditionally hide / show.&#x20;















