---
description: Show, hide, or toggle the visibility of an element.
---

# Visibility Actions 🧪



trigger:(event name):display-toggle &#x20;

action:(event name):display-hide









{% hint style="danger" %}
UNDER SPECIFICATION. &#x20;
{% endhint %}

e.g. `sa-action-display-show` = ( _event name_ )  &#x20;

|                                 |                                   |                                                    |
| ------------------------------- | --------------------------------- | -------------------------------------------------- |
| `sa-action-display-hide`        | Hide the item                     | Adds style=display: none;                          |
| `sa-action-display-show`        | Show the item                     | Adds style=display: block;                         |
| `sa-action-display-toggle`      | Toggles the item visibility state |                                                    |
| ~~`sa-action-display-revert`~~  | Revert the item display state     | Removes the display style on the element directly  |

{% hint style="info" %}
Works by using \`display attributes. Do not use it on elements that are targeted by Webflow interactions as they also use style.&#x20;
{% endhint %}

Consider how to handle block, flex, grid &#x20;

{% hint style="info" %}
Use only on an element with display: block.  If you are using e.g. flex or grid, use display:
{% endhint %}



wfu-action-unhide&#x20;

### Future

* Transitions like fade-in / fade-out ?&#x20;
* ~~Separate visibility?~~&#x20;
  * Or just rely on class adder&#x20;

