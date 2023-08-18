---
description: Display your nested Collection List Lightboxes in separate groups
---

# CMS & Lightbox + Groups ❺

Webflow's [lightbox element](https://university.webflow.com/lesson/lightbox) is CMS compatible, however it has some limitations.

One limitation is that it [does not provide](https://discourse.webflow.com/t/full-cms-lightbox/33669) the ability to bind the lightbox group. This means that if you are using the CMS multi-image field, and you are using a nested collection list to display them, you cannot lightbox-group these images together.  &#x20;

## Use Cases

Common examples of where designers need this;

* Product catalogs where you have multiple product shots
* Real estate sites
* Event sites&#x20;

SA5 offers a no-code attributes-based solution to add this capability.&#x20;

## Demonstration

{% embed url="https://cms-lightbox-groups.webflow.io/" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/cms-lightbox-groups" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

{% hint style="info" %}
SA5 will assigns lightbox groups _regionally_ in your element hierarchy.&#x20;

Place the attribute on any element, and all of the lightboxes that are descendants of that element will be assigned the same lightbox group.&#x20;
{% endhint %}

### Enable the _Link with other lightboxes_ feature

This may not be necessary for the library to work, but it's best to enable the **Link with other lightboxes** feature on each of your lightboxes. Leave the **Group name** blank.&#x20;

![](<../../.gitbook/assets/image (5) (1).png>)

### Add the `wfu-lightbox-group` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-lightbox-group` custom attribute with the group name you want to any parent element of the lightbox, and all subordinate lightboxes ( descendants of that element ) will be assigned that same lightbox group.&#x20;

> What value should I assign to the attributes?

You can assign any unique value you choose for your group.&#x20;

To create separate groups for each of your parent list items, use Webflow's [CMS-bound custom-attribute feature](https://university.webflow.com/lesson/custom-attributes#how-to-use-cms-data-in-custom-attributes) and set it to the parent item's `slug`. This ensures that each group has a unique name.&#x20;

{% hint style="info" %}
If you have other lightboxes on your page outside of the collection lists, make certain their group names (if any) do not conflict with your CMS item slugs. An easy way to do this is to prefix them with a hyphen or underscore.&#x20;
{% endhint %}

> Where should I place the attribute?

For this nested list scenario, there are two common strategies.&#x20;

Collection lists individually have a 3-level hierarchy of Collection List Wrapper, Collection List, and Collection Item, which we'll refer to here as _wrapper_, _list_, and _item_. &#x20;

In a nested list arrangement, they'll appear like this;&#x20;

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Example of a nested list, in which the parent contains a lightbox image, and the child Multi-image</p></figcaption></figure>

In this example, the parent collection list has a main image which is light-boxed, and it has a nested collection list - bound to a multi-image field - whose images are also light-boxed. &#x20;

Here you typically choose one of two configuration options;

1. If you want all of the images _including the main image_ to be grouped together in the same lightbox, then place the attribute on the parent's _item_ element.
2. If you want the child thumbnails to appear in the same lightbox, but exclude the parent's image, then place the attribute on the child's _wrapper_ element.

Remember to bind your custom attribute value to the parent item's slug, so that they all get the same unique group name.&#x20;

{% hint style="danger" %}
Avoid placing the attribute on two elements that have a parent-child relationship to one another, as this will create an undefined situation as to which group will be applied.&#x20;
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this code to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Elements -->  
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.32/dist/css/webflow-elements.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.32/dist/nocode/webflow-elements.js"></script>
```
{% endcode %}

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

## Credits

Full credit to [Travis Orams](https://discourse.webflow.com/u/oramsdesign) for [detailing](https://discourse.webflow.com/t/full-cms-lightbox/33669) the original solution approach. SA5 uses a similar group-setting approach, without the need to replace the lightbox element manually.&#x20;



