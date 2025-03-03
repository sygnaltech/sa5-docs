---
description: Add, remove, or toggle a specific class on an element.
---

# Class Adder Actions 🧪

{% hint style="danger" %}
**UNDER SPECIFICATION**&#x20;


{% endhint %}

Problems;

Ideally we want to be able to attach multiple event-actions to a single element. &#x20;

sa-action-class-data:test&#x20;





## Usage Notes&#x20;

Add the appropriate attribute to add, remove, or toggle classes.  Assign it to the Event name that will invoke this Action.&#x20;

e.g. `sa-action-class-add` = ( _event name_ )&#x20;

Separately, define the class that is being manipulated;&#x20;

e.g. `sa-action-class-data` = ( _class name_ ) &#x20;

{% hint style="success" %}
See [Data](class-adder-actions.md#data) for more details on the class name.&#x20;
{% endhint %}

### Attributes

These are the supported Action attributes;&#x20;

| Attribute                 |                                   |                                                                      |
| ------------------------- | --------------------------------- | -------------------------------------------------------------------- |
| `sa-action-class-add`     | Add a class to the element        | See [Data](class-adder-actions.md#data) for how to specify the class |
| `sa-action-class-remove`  | Remove a class from the element   | See [Data](class-adder-actions.md#data) for how to specify the class |
| `sa-action-class-toggle`  | Toggles the class on the element  | See [Data](class-adder-actions.md#data) for how to specify the class |

## Data

### `sa-action-class-data` = ( _class name_ )  &#x20;

Specify the class name that will be added, removed, or toggled.&#x20;

## Future &#x20;

### Multiple Classes

{% hint style="success" %}
It may be possible to specify multiple classes, space-delimited, e.g. `red highlight`. &#x20;

In this case we would add or remove both classes.&#x20;
{% endhint %}

{% hint style="warning" %}
Toggling here could be ambiguous, e.g. if the element has `red` but not `highlight` than what state is it in?  In this scenario, we would likely consider it "off", and the initial toggle action would turn it "on" by ensuring both classes are added.&#x20;
{% endhint %}

