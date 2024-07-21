---
description: Dynamically show and hide elements on your page based on user actions
---

# Element Groups ❺🧪

{% hint style="danger" %}
This feature is not yet available to the public.&#x20;
{% endhint %}

Tab components and accordions are great when your elements are together in one area of your page, but what about when your layout is more complex?  What happens when the things you are clicking are scattered around the page, and the corresponding things that your showing and hiding are similarly scattered?

SA5 Element Groups solves this by allowing you to define arbitrary elements groupings, and then conditionally display only those elements within a group that are tagged with a specific item name.

## Concepts

Here is the terminology we'll use in our documentation;&#x20;

* **Elements** are the individual items on your page that you want to dynamically hide or show. These are generally DIVs but can be essentially any HTML element type.&#x20;
* **Groups** represent a grouping of elements. When an element is shown, all other elements in that group will be hidden.
* **Triggers** represent an event - usually a user event - which will change the Elements that you want to be active within a group. Most often, the trigger is another element on the page, such as a button, tab, radio button, or form select.&#x20;

{% hint style="success" %}
To understand this better, consider a simple tabs element.  In this construction, the group is the entire tabs element with all of its tabs and tab panes.  The elements are the individual tab panes.  The tabs themselves are the triggers.&#x20;

Clicking a tab hides all tab panes, and shows only the one tab pane you want.&#x20;

**The reason for this library is that in many page layouts, a standard tabs element would not work- the "panes" are located in different areas of the page.**
{% endhint %}

## Use Cases

A custom tab-style element, where clicking one element shows a content pane.&#x20;

A custom accordion-style element.&#x20;

_Too many to really describe._&#x20;

The general pattern is that you want to have a series of elements that hide/show according to specific user actions.&#x20;

* The page loads with only certain element(s) visible
* When the user clicks on something e.g. a radio button, that configuration changes so that other element(s) are visible  &#x20;
* Dynamic forms with conditional areas&#x20;

{% hint style="success" %}
This supports CMS-driven use cases also &#x20;
{% endhint %}

## Usage Notes

### Define your dynamic elements

To the elements you want to dynamically show and hide, add these attributes;

#### `wfu-element-group`

Specify a unique name for this element group. This will act as a context for related elements.&#x20;

#### `wfu-element-name`

Specify a unique name for this element, which will allow you to identify it directly. No commas or periods.&#x20;

#### `wfu-element-default` ( optional )

Indicates that this element should be displayed on page load, as a default state, before any trigger action occurs.&#x20;

#### `wfu-element-display` ( optional )

Defines the CSS display type to use when the element is made visible- useful for elements that are flex or grid.  Defauts to block.&#x20;

> ? An element with a name, but no group, will be considered part of all groups&#x20;

{% hint style="info" %}
When using CMS data, a useful technique here is to assign a unique static group name, and then use Webflow's CMS-bound attributes to bind the CMS item slug as the element name attribute.&#x20;
{% endhint %}

### Define your triggers

Triggers are ( currently ) other elements anywhere on the page that the user can click or select, which will trigger a change in which item(s) are displayed in the element group.&#x20;

#### `wfu-element-action` = `select`

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









