---
description: >-
  Easily create static & CMS Accordions in Webflow, with no Interactions, no
  custom code and complete designer styling control.
---

# Accordion Element

An **accordion** element is a common user interface ( UI ) component used to organize and manage pieces of content in a structured, compact and user-friendly way. It is named "accordion" because it functions similarly to the musical instrument of the same name, where sections can expand and collapse, revealing or hiding content.

{% hint style="success" %}
In Sygnal's SA5 implementation, the accordion is in the same family of UX's as a tab component or a slider, and we collectively refer to these as "deck elements".  It is also not based on a native Webflow element and is instead&#x20;
{% endhint %}

## Use Cases

* **Content Organization:** Accordions are particularly useful for organizing large amounts of information into digestible chunks. For example, they are often used in FAQs, where each question expands to reveal the answer.
* **Forms and Surveys:** They can be used to break down lengthy forms into manageable steps or sections, improving the user's ability to focus on one task at a time.
* **Mobile Design:** In responsive design, accordions are helpful in presenting content on small screens, where space is limited.

## Goals

* No interactions dependencies
* Easy designer setup
* Good designer view
* Strong programmatic control
  * Ability to tell when a new panel has opened&#x20;
  * Ability to change the open panel programmatically&#x20;

## Demonstration

{% embed url="https://sa5-elements.webflow.io/accordions" %}

{% embed url="https://webflow.com/made-in-webflow/website/sa5-elements" %}

## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../quick-start.md).

### STEP 2 - Setup your Accordion element structure <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See [Element Structure](./#element-structure), below.&#x20;

```
DIV - [wfu-accordion]
  DIV - [wfu-accordion
```

### STEP 2 - Apply the custom attributes to the elements you want to affect <a href="#step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect" id="step-2---apply-the-custom-attributes-to-the-elements-you-want-to-affect"></a>

See above for details.

### STEP 3 - ( OPTIONAL ) Use the API & Callbacks to control the element from your custom code

See above for details.

## Setting Up Your Accordion&#x20;

To keep everything easily managed and controlled within the designer, SA5's accordion uses the addition and removal of classes to control the open and closed states. This gives you the ability to define what open state looks like and what closed state looks like, all within the designer.&#x20;

{% hint style="info" %}
Use the cloneable above for reference if you're unclear on any portion of the docs here.&#x20;
{% endhint %}

Accordion setup requires three parts;

1. A simple element structure that defines the Accordion, its items, tabs, and contents&#x20;
2. The custom attributes applied to these elements to describe and configure the Accordion&#x20;
3. The definition of `is-open` and `is-closed` classes that allow you to fully control the open and closed-state appearance of;
   1. The item wrapper
   2. The item tab ( background color, icon, text color, etc. )&#x20;
   3. The content panel ( especially the size when open / closed )&#x20;

## Accordion Elements

**SA5's Accordion** follows a simple, general structure that consists of a main wrapper DIV, and then 3 DIVs per Accordion item.&#x20;

A static Accordion can simply be built with DIVs in this arrangement.&#x20;

```
DIV - Accordion element
  DIV - Accordion item
    DIV - Accordion item tab
      ... tab contents ...
    DIV - Accordion item content
      ... main contents ...
  ... more Accordion items
```

For CMS-driven Accordions, you can use a Collection List;

```
DIV - Collection List Wrapper
  DIV - Collection List - Accordion element
    DIV - Collection Item - Accordion item
      DIV - Accordion item tab
        ... tab contents ...
      DIV - Accordion item content
        ... expando contents ...  
```

## Accordion Classes&#x20;

You can style your Accordion any way you like, including horizontal and vertial orientations. Our goal was to make the Accordion styling 100% under designer control with zero custom CSS.&#x20;

SA5 Accordion works by adding and removing the `is-open` and `is-closed` classes from your Accordion items, tabs, and content panes.&#x20;

Typically, the easiest approach is;

1. Design and style your Accordion items in the open state, exactly how you like.&#x20;
2. Ensure that the Accordion Item, Accordion Item Tab, And Accordion Item Content elements all have classes defined.
3. Then to each, add an `is-closed` compound class and style the closed state.
4. Once you're done, you can remove that `is-closed` class to make content admin easier in the designer.  It will still exist in the published site.&#x20;

{% hint style="warning" %}
To prevent your `is-closed` class from being removed by Webflow's **Clean up unused styles** feature, apply the same combo class series to a DIV, and then put that in your style guide or wrap it in a hidden DIV on the page.  This will ensure Webflow knows that the class is still needed.&#x20;

![](<../../.gitbook/assets/image (66).png>)
{% endhint %}

{% hint style="info" %}
The `is-open` class can also be styled but often this is not needed.&#x20;
{% endhint %}

{% hint style="success" %}
If you find it easier in the designer, you can keep the `is-open` and `is-closed` classes on your elements and publish the site that way.  Either say SA5 will reset the classes appropriately when the page is loaded.&#x20;
{% endhint %}

## Accordion Attributes&#x20;

For SA5 Accordion to setup the accordion properly, you will need these custom attributes;&#x20;

### wfu-accordion = ( name )

**Required.**  Place this on the outer wrapper of your Accordion, the immediate parent of the items.  In the case of a collection list, this is the middle Collection List element of the 3.&#x20;

The name is arbitrary, but it is used by the JS-API to allow you to differentiate between Accordions on your page in methods and events.&#x20;

### wfu-accordion-item = ( name )&#x20;

**Required.**  Place this on the wrapper for each Accordion Item. In a collection list, this is the innermost Collection Item element of the 3.&#x20;

The name is arbitrary, and in a collection list you can bind it to the slug. It is used by the JS-API to allow you to select a specific accordion item by name, rather than by position.&#x20;

### wfu-accordion-item-tab = ( no value )

**Required.**  Place this on the tab DIV you create as an immediate child of the element with `wfu-accordion-item` attribute.&#x20;

### wfu-accordion-item-content = ( no value )

**Required.**  Place this on the content DIV you create as an immediate child of the element with `wfu-accordion-item` attribute.&#x20;

### wfu-accordion-class-open = ( class name )

**Optional.** Allows you to specify a different class name for your open-state compound classes.&#x20;

Default is `is-open`

### wfu-accordion-class-closed = ( class name )&#x20;

**Optional.** Allows you to specify a different class name for your closed-state compound classes.&#x20;

Default is `is-closed`







