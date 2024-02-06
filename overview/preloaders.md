# Preloaders

Much of SA5 is dedicated to creating a dynamic UX experience- sorting, filtering, data-binding, calculations, and much more.

This requires placeholder elements which - before the SA5 code executes, will be uninitialized.

To ensure a perfect view, we are standardizing on a specific preloader approach which can be controlled per-element using the wfu-preload attribute.

{% hint style="info" %}
Final details are being refined, and this capability is being rolled out across all libs gradually.&#x20;
{% endhint %}

## Options

`wfu-preload` = ( method )&#x20;

* `hidden` - the element is initially hidden and collapsed from view using CSS display: none.
* `invisible` - the element is initially invisible, but takes space using CSS visibility: hidden.
* `animated` - the element has an element-specific loading animation.&#x20;

Animation types;&#x20;

* redacted, animated &#x20;
* SVG animation
  * dot-dot-dot
* static placeholder text
* blurred placeholder text, then unblurred on load&#x20;

## Technical Notes&#x20;

* All preloaders are CSS-based, and are driven by the wfu-preload attribute.&#x20;
* On load, the value is set first
* Then the wfu-preload attribute is removed. This gives the element its default visibility.&#x20;

{% hint style="info" %}
Preload effects generally do not appear at design time, only in the published site.
{% endhint %}

