# Component Object Positioning

Webflow doesn't have much support yet for styling of component instances. Here's a technique we use to support the adjustment of images that may be off-center.&#x20;

## Use Cases

The general use case scenario for this is that you have;

* A CMS collection that contains a primary photo, such as a product image, a blog hero image, or a team member's profile photo.&#x20;
* In your collection pages and collection lists, you want to constrain the aspect ratio of that photo, so that it's 1:1
* Due to the variety of the photos, that cropping may not always be centered, so you need a way to adjust this per collection item.&#x20;

We can solve this using Webflow components, property-bound custom attributes, a small piece of CSS, and Webflow's property-to-CMS binding capabilities.&#x20;

In the end result, we can adjust the camera position on each image individually by e.g. specifying `left up` to move the camera position left and upwards slightly.&#x20;

## Usage Notes&#x20;

Once setup you control the positioning with a string value that can contain a horizontal camera position and/or a vertical camera position.

{% hint style="info" %}
All positions here are "camera positions". meaning that "left" moves the camera left, and the image shifts to the right.&#x20;
{% endhint %}

|                 | Horizontal Position | Vertical Position |
| --------------- | ------------------- | ----------------- |
| 0%              | start               | top               |
| 25%             | left                | up                |
| 50% ( default ) | center              | middle            |
| 75%             | right               | down              |
| 100%            | end                 | bottom            |

For example, `start up` would move the camera all the way to the left, and slightly upwards in the image.&#x20;

### Ratios and Object Fit

In most cases, this feature will be setup on an image which has been set to a ratio of e.g. 1:1 , ond object-fit: cover. &#x20;

<figure><img src="../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

What this means is that the image will fill the space, and one of the dimensions ( width or height ) will already be at 100%.

As a result it generally only makes sense to specify either the horizontal camera adjustment or the vertical camera adjustment, but not both.&#x20;

In the 1:1 example;&#x20;

* A perfectly square image already fills the space perfectly and cannot be adjusted at all as there is no more image to see.&#x20;
* A portrait image would already be showing its full width and the camera can only be adjusted vertically.&#x20;
* A landscape image would already be showing its full height, and the camera can only be adjusted horizontally.&#x20;

## Getting Started&#x20;

{% hint style="info" %}
This will be integrated into the SA5 lib later, for now it's a manual setup.
{% endhint %}

{% embed url="https://www.loom.com/share/c9bc131388434b3a9d214a583e59d438" %}

On the component wrapper, put a custom attribute of `wfu-component-position`.

Bind its value to a component property, called **Camera Position**.  This is where you'll enter e.g. `top left` when you want to adjust an item's position.

Inside of the component, add a custom attribute of `wfu-component-position-item` to the elements to which you want the CSS applied.  Generally that will be your main image element.

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

## Best Practices

If you're using the CMS, and have added a text field to control these positions, We recommend you name it e.g. **Profile Photo Camera Position**,

You can can also add this note to help the admin remember the keywords needed.&#x20;

```
Vertical = top up middle down bottom | Horizontal = start left center right end 
```



