---
description: Display your nested Collection List Lightboxes in separate groups
---

# CMS & Lightbox + Groups ❺

Webflow's [lightbox element](https://university.webflow.com/lesson/lightbox) is CMS compatible, however it it [does not provide](https://discourse.webflow.com/t/full-cms-lightbox/33669) the ability to CMS-bind the lightbox group.&#x20;

In a CMS-driven layout like this one, we may want specific groupings of images ( here, each purple box ) to have their own distinct lightbox group.&#x20;

At present, this is not natively supported in Webflow.&#x20;

**SA5 offers a no-code attributes-based solution to add this ability.**&#x20;

<figure><img src="../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**Important Webflow ECommerce limitation**

Webflow currently does not support CMS-bound custom attributes when a CMS collection is bound to the ECommerce Products or Categories collection. This creates a configuration problem for an attributes-based library, since those custom attributes are essential for the grouping.&#x20;

Currently this SA5 feature should be considered incompatible with any collection list that is bound to Webflow ECommerce Products or Categories.

_If you need that capability in your project, you can_ [_contact Sygnal_](https://sygnal.com/contact) _about building a custom, non-attributes version of this library for your project._&#x20;
{% endhint %}

## Use Cases

Common examples of where designers need this;

* Product catalogs where you have multiple product shots
* Real estate sites
* Event sites&#x20;

## Demonstration

Here is a demonstration of CMS-driven lightbox grouping, with a cloneable.

{% hint style="success" %}
Use the cloneable as a reference for your own implementation. It will show you the exact placement and setup of the attributes for a typical product catalog configuration.
{% endhint %}

{% embed url="https://cms-lightbox-groups.webflow.io/" %}
Demonstration
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/cms-lightbox-groups" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

This library is very flexible in its configuration options.&#x20;

The documentation here will focus on the most common use case - a product gallery where each product has a main photo and series of additional photos, which we want lightboxed together in a single group.

![](<../../.gitbook/assets/image (47).png>)

This setup is demonstrated in the cloneable above, and here's a **video walkthrough** on the implementation details.

{% embed url="https://www.loom.com/share/761c02e34c5146e993c2b14afc40650a" %}

{% hint style="info" %}
Use the video as your primary reference for this type of build, however below are some additional notes for designers who want to vary the setup.&#x20;
{% endhint %}

### Enable the _Link with other lightboxes_ feature

Enable the **Link with other lightboxes** feature on each of your lightboxes.&#x20;

Leave the **Group name** _blank_.&#x20;

![](<../../.gitbook/assets/image (31).png>)

### Add the `wfu-lightbox-group` attribute <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Add the `wfu-lightbox-group` custom attribute with the group name you want _to any parent element of the lightbox_, and all lightboxes _within_ that parent element ( descendants ) will be assigned that same lightbox group.&#x20;

For example,&#x20;

`wfu-lightbox-group` = `mygroup`

would assign that static string "mygroup" as the group name for _every lightbox that is within your tagged element_.&#x20;

You can assign any unique value you choose for your group, but the purpose of this library is to make those groups dynamic, _based on your CMS data_.&#x20;

To do that, we'll use Webflow's [CMS-bound custom-attribute feature](https://university.webflow.com/lesson/custom-attributes#how-to-use-cms-data-in-custom-attributes) and set it to the parent item's `slug`. This ensures that each group has a unique name.&#x20;

`wfu-lightbox-group` = `{{ slug }}`

{% hint style="info" %}
SA5 supports this "attribute affects descendants" approach because of the way Webflow's nested collection lists work in relation to custom attributes. See the descussion of this in the video above.&#x20;
{% endhint %}

Choosing where to place the attribute matters, for two reasons;

1. SA5 will apply the group you specify in the attribute to any lightboxes within that element
2. Webflow's CMS-bound custom attributes have specific rules in what you can bind to, which means that elements within the _nested_ collection list cannot be bound to fields of the _parent_ collection list.

In our nested list configuration, this means that the best place to place the attribute \[2] is on the parent collection list item \[1]. &#x20;

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If you have other lightboxes on your page outside of the collection lists, make certain their group names (if any) do not conflict with your CMS item slugs. An easy way to do this is to prefix them with a hyphen or underscore.&#x20;
{% endhint %}

{% hint style="danger" %}
Avoid placing the attribute on two elements that have a parent-child relationship to one another, as this will create an undefined situation as to which group will be applied.&#x20;
{% endhint %}

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

## Credits

Full credit to [Travis Orams](https://discourse.webflow.com/u/oramsdesign) for [detailing](https://discourse.webflow.com/t/full-cms-lightbox/33669) the original solution approach. SA5 uses a similar group-setting approach, but has redesigned it so that there is no need to replace the lightbox element manually.&#x20;



