# Hide Section w/ Empty Collection Lists

Want to hide a section when the Collection Lists it contains are empty?

Suppose you have an area of your page called “alerts” and it has some nice styling and icons… but how do you make the whole thing disappear when there are no alerts pulled by the Collection List for display?

This solution provides a simple attributes-based way to do that.

{% hint style="info" %}
In the current CSS-based version of this feature, we use the CSS `:has()` pseudoselector. However it is not yet [supported](https://caniuse.com/css-has) by all browsers, most notably Firefox. If you need 100% browser coverage, you should use a Javascript based solution until Firefox implement :has fully.&#x20;
{% endhint %}

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-hide` attribute <a href="#wfu-hide-attribute" id="wfu-hide-attribute"></a>

To the section you want to hide, add the custom attribute;

```
wfu-hide = empty-collection-list
```

If ALL of the collection lists within that section are empty, the entire section will be hidden.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

This is a CSS-only solution.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.10/dist/css/webflow-html.css">
```
{% endcode %}

#### STEP 2 - Apply `wfu-hide` section or element you want to hide <a href="#step-2---apply-wfu-hide-section-or-element-you-want-to-hide" id="step-2---apply-wfu-hide-section-or-element-you-want-to-hide"></a>

See above for details.

\
