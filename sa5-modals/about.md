---
description: Tools for better modal & popup solutions in Webflow
---

# 🔍 About SA5's Webflow Modals & Popups Lib

This library extends Webflow with some capabilities to support modals & popups;

* Ability to close an element and have it remain closed on the next visit
* Timed suppression on close, using a cookie

## Future <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Modals, popups, and other UX elements take a huge range of forms. Webflow has no in-built features to support these, and interactions are often the go-to solution. We're gradually exploring ways to expand on this. &#x20;

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







