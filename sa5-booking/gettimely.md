---
description: Easily integrate versatile bookings into your Webflow site using GetTimely
---

# GetTimely ❺🧪

{% hint style="danger" %}
This feature is not yet available to the public.&#x20;
{% endhint %}

<div align="left">

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

</div>

GetTimely originated as a salon-booking service, but its well-designed approach and excellent website integration make it a good choice for other business types as well such as smaller medical clinics.&#x20;

{% embed url="https://www.gettimely.com/" %}

## Usage Notes

### Define your dynamic elements

To the elements you want to dynamically show and hide, add these attributes;

#### `wfu-book` = `timely`

Identifies that this button triggers a booking with Timely.

#### `wfu-book-service = service id`

Specify a unique name for this element, which will allow you to identify it directly. No commas or periods.&#x20;

#### `wfu-book-category` ( optional ) = category id

Indicates that this element should be displayed on page load, as a default state, before any trigger action occurs.&#x20;

#### `wfu-book-location` ( optional ) = location id

Defines the CSS display type to use when the element is made visible- useful for elements that are flex or grid.  Defauts to block.&#x20;

> ? An element with a name, but no group, will be considered part of all groups&#x20;

{% hint style="info" %}
When using CMS data, a useful technique here is to assign a unique static group name, and then use Webflow's CMS-bound attributes to bind the CMS item slug as the element name attribute.&#x20;
{% endhint %}

#### `wfu-book-provider` = `select`

Trigger-type aware;

* Radio buttons
* Buttons and other elements, click&#x20;

Future;

* Future - Selects&#x20;
* Future - Tabs
* Future - Sliders
* Code-based triggers
  * e.g. querystring checks - Use case- tracked referrer&#x20;

#### `wfu-element-target-group = (group-name)`

Specify the group that you want to target.

#### `wfu-element-target-name = (item-name)`

Specify the element name you want to be visible. All other elements in the same group will be hidden.&#x20;

{% hint style="info" %}
If you want to make multiple elements visible, you can comma-separate them in this attribute.&#x20;
{% endhint %}

{% hint style="warning" %}
Do not tag a single element as both an Element and as a Trigger.&#x20;
{% endhint %}









