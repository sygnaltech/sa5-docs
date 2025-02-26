# Element Actions













## Click Action&#x20;

Clicks the tagged elemet when the Event fires.&#x20;

```
wfu-action-click = ( event name )
```

### Notes

Distinguish touch?&#x20;



## Scroll To Action

Scroll To the specified element&#x20;

{% hint style="warning" %}
**IMPORTANT** \
Use only one of these per Event .&#x20;
{% endhint %}



## Visibility ( Hide, Show, & Toggle ) Actions&#x20;

{% hint style="danger" %}
UNDER SPECIFICATION. &#x20;
{% endhint %}

e.g. `wfu-action-show` = ( _event name_ )  &#x20;

|                                  |                                   |                                                    |
| -------------------------------- | --------------------------------- | -------------------------------------------------- |
| `wfu-action-display-hide`        | Hide the item                     | Adds style=display: none;                          |
| `wfu-action-display-show`        | Show the item                     | Adds style=display: block;                         |
| `wfu-action-display-toggle`      | Toggles the item visibility state |                                                    |
| ~~`wfu-action-display-revert`~~  | Revert the item display state     | Removes the display style on the element directly  |

{% hint style="info" %}
Works by using \`display attributes. Do not use it on elements that are targeted by Webflow interactions as they also use style.&#x20;
{% endhint %}

Consider how to handle block, flex, grid&#x20;

{% hint style="info" %}
Use only on an element with display: block.  If you are using e.g. flex or grid, use display:
{% endhint %}



wfu-action-unhide&#x20;

### Future

* Transitions like fade-in / fade-out ?&#x20;
* ~~Separate visibility?~~&#x20;
  * Or just rely on class adder&#x20;

