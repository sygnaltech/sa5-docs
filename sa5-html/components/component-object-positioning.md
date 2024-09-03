# Component Object Positioning

Problem



|      | Horizontal Position | Vertical Position |
| ---- | ------------------- | ----------------- |
| 0%   | start               | top               |
| 25%  | left                | up                |
| 50%  | center              | middle            |
| 75%  | right               | down              |
| 100% | end                 | bottom            |

## Usage Notes

{% hint style="info" %}
This will be integrated into the SA5 lib later, for now it's a manual setup.
{% endhint %}



On the component wrapper, put a custom attribute of `wfu-component-position`.

Bind its value to a component property, called Position.  This is where you'll enter e.g. `top left` when you want to adjust an item's position.



Inside of the component, add a custom attribute of `wfu-component-position-item` to the elements to which you want the CSS applied.  Generally that will be image elements.

Make certain the image elements are setup properly, e.g.;

* e.g. width 100%, height 100% if they need to fill the container
* Overflow clip
* Fit cover
  * Default fit cover position is usually centered at 50% 50%&#x20;

Add an embed inside of your component, with this CSS;&#x20;

```html
<style>
/* Horizontal Positions */
[wfu-component-position~="start"] {
  --wfu-component-position-x: 0%;
}

[wfu-component-position~="left"] {
  --wfu-component-position-x: 25%;
}

[wfu-component-position~="center"] {
  --wfu-component-position-x: 50%;
}

[wfu-component-position~="right"] {
  --wfu-component-position-x: 75%;
}

[wfu-component-position~="end"] {
  --wfu-component-position-x: 100%;
}

/* Vertical Positions */
[wfu-component-position~="top"] {
  --wfu-component-position-y: 0%;
}

[wfu-component-position~="up"] {
  --wfu-component-position-y: 25%;
}

[wfu-component-position~="middle"] {
  --wfu-component-position-y: 50%;
}

[wfu-component-position~="down"] {
  --wfu-component-position-y: 75%;
}

[wfu-component-position~="bottom"] {
  --wfu-component-position-y: 100%;
}

/* Apply Object Position using Namespaced Variables */
[wfu-component-position-item] {
  object-position: var(--wfu-component-position-x, 50%) var(--wfu-component-position-y, 50%);
}
</style>
```

