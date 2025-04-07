---
description: Show, hide, or toggle the visibility of an element.
---

# Visibility Actions

## Goals

* Show a hidden element
* Hide a visible element
* Toggle the visibility of an element &#x20;

## Action Attributes&#x20;

{% hint style="danger" %}
UNDER SPECIFICATION. &#x20;
{% endhint %}

e.g. `sa-action-display-show` = ( _event name_ )  &#x20;

|                             |                                   |                             |
| --------------------------- | --------------------------------- | --------------------------- |
| `sa-action-display-hide`    | Hide the item                     | Adds style=display: none;   |
| `sa-action-display-show`    | Show the item                     | Adds style=display: block;  |
| `sa-action-display-toggle`  | Toggles the item visibility state |                             |

{% hint style="warning" %}
Works by using the `display` style property. Do not use it on elements that are targeted by Webflow interactions which affect the `display` style property, as it will conflict. In that situation, wrapping your elements in a DIV and using the SA5 attributes on that DIV is generally the recommended approach.&#x20;
{% endhint %}

## Data



### `sa-action-display:mode` = ( _mode_ )&#x20;

**Optional.** One of... &#x20;

* `display` ( default )&#x20;
* `visibility`&#x20;
* `opacity`&#x20;

### `sa-action-display:display` = ( _display mode_ )&#x20;

**Optional.** Any valid [CSS display mode](https://developer.mozilla.org/en-US/docs/Web/CSS/display)...

* `block` ( default )&#x20;
* `flex`&#x20;
* `grid`&#x20;
* `inline-block`&#x20;
* _etc._&#x20;

{% hint style="success" %}
Used with a mode of display.&#x20;

By default, displaying a hidden element sets the display to block.  You can override this behavior here, which will be used both by sa-action-display-show and sa-action-display-toggle.&#x20;
{% endhint %}

### sa-action-display:opacity = ( min opacity )

Optional. Defaults to 0% ( fully hidden )&#x20;







## Future

* Hide and show&#x20;
  * Display
  * Visibility&#x20;
  * Opacity
* Transitions like fade-in / fade-out ?&#x20;
* ~~Separate visibility?~~&#x20;
  * Or just rely on class adder&#x20;

