---
description: Tools for better modal & popup solutions in Webflow
---

# 🔍 About SA5's Webflow Modals & Popups Lib

Modals, popups, and banners are built with a wide range of styles and behaviors. In most cases, interactions are used to handle the show and hide effects, but Webflow doesn't offer any native capabilities for behaviors like;

* Suppression for N days after close
* Exit intent triggers to open a modal

We also felt that some basic modal mechanics should be more accessible to our clients, in the form of custom attributes that can be easily documented for configuration.

* Timed-trigger for open ( defined in milliseconds )
* Timed-trigger for close ( defined in milliseconds )
* Scroll-trigger for open ( defined as page-scroll % )
* Hover-trigger for open ( placed on any element )&#x20;
* Click-trigger for open ( placed on any element )&#x20;

The SA5 team wanted an attributes-based infrastructure that allows us to easily create and configure modals, popup and banner behavior in any project.&#x20;

{% hint style="info" %}
**What are modals?** To SA5, Modals, Popups, and Banners are all the same thing.  They're simply elements in your project which are assigned custom attributes to give them behaviors, so you can create the UX you want.&#x20;

_For convenience, we use the term **modals** to describe any element that you want to assign display, hide, and suppress capabilities to._&#x20;
{% endhint %}

## Goals

There are a few key goals in our design of this library;

* Full flexibility of configuring how these elements behave, using attributes.&#x20;
  * How and when triggers work to display, hide, and suppress elements&#x20;
  * Supporting a wide range of triggers, such as click events, hover, scroll, timers, and exit intent&#x20;
* Full compatibility with Webflow interactions&#x20;
* Separation of the styling in interactions from the timing, so that the timing can be easily changed or exist in many variations throughout your project. For example, we want to be able to use interactions to define how a modal "flies in" to the page, but we do not want interactions to specify when that happens, or what kinds of things can trigger it.&#x20;
  * We also want to separate the "what", so that we can arbitrarily set this up on any element. That can currently be achieved by using Webflow class-based targeting, a hidden sibling trigger button, and a sibling targeting constraint.&#x20;

## Updates&#x20;

<table><thead><tr><th width="129.6666259765625">Date</th><th width="181.99993896484375">Feature </th><th>Updates </th></tr></thead><tbody><tr><td>12-Jun-2025</td><td><a href="dismissible.md">Dismissible Elements</a> </td><td><ul><li>Added <code>wfu-preload</code> support </li><li>Updated cloneable demos </li></ul></td></tr></tbody></table>



## Future <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>



Currently when the element is suppressed, it is removed from the DOM. This is the simple way, however it precludes the ability to manually open and review a message, e.g.;&#x20;

* Show an alert
* User closes the alert, it's now closed forever
* But there is a "show alerts" button on the page that can un-suppress them&#x20;

We may redesign this lib so that the modals are not deleted, but hidden instead.&#x20;

wfu-modals-unsuppress="name"

wfu-modals-unsuppress="name1,name2,name3"

wfu-modals-unsuppress="\*"

Other UX support concepts under development;

1. **Tooltip**: A small pop-up that displays information when a user hovers over or focuses on an element, such as an icon or link.
2. **Modal**: A dialog box or pop-up window that is displayed on top of the main content and typically requires user interaction before they can return to the main content.
3. **Popover**: Similar to a tooltip, but often triggered in ways other than just hovering, such as clicking on an element.
4. **Overlay**: A layer that appears over the main content, often dimming the background and presenting additional information or options.
5. **Dropdown**: A list of options that appears when interacting with certain elements, like a button or form field.
6. **Reveal**: General term to describe content or elements that become visible upon interaction.
7. **Expando**: Informal term sometimes used in web design to describe an element that can be expanded to reveal more content, often used in the context of "collapsible" or "expandable" sections.







