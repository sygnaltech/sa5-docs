# Future

Future ideas include;&#x20;

* Copy v. Move &#x20;
* Control the sequence of operations?&#x20;
* Part control
* Position control
  * Sorting control?&#x20;
* Handlers
  * Slider&#x20;
  * SwiperJS
  * Lightbox Galleries
  * Accordion
  * Dropdown Navs

## Custom Callbacks

* Pre-layout callback
  * e.g. create containers for calendar events\
    [https://discourse.webflow.com/t/issues-fetching-filtered-cms-items-via-serverless-function-due-to-cors-policy/270353/4](https://discourse.webflow.com/t/issues-fetching-filtered-cms-items-via-serverless-function-due-to-cors-policy/270353/4)
  * Normalize dates from an ISO-8601 embed to a scoped attribute
    * Year, month, day, hour... levels of scoping&#x20;
* Post-layout callback
  * Could put styling classes here, iterate through containers, with layout report information&#x20;

## Styling classes

Apply after layout to containers

* No elements&#x20;
* No element added
* Number of elements ( attribute )
* Number of elements added ( attribute )

Assign classes for easy styling?

## Tabs Layout

Ability to do more complex tabs

[https://www.apple.com/ca/today/calendar/](https://www.apple.com/ca/today/calendar/)

## Future

Consider behavior if no layout elements are found- keep the container hidden?&#x20;







#### Options ( Under Consideration )&#x20;

`wfu-layout-priority` = NUMBER ( optional )

Control the sequence of layout operations.&#x20;

`wfu-layout-item-method` =&#x20;

* `move` (default) - move the item
* `copy` - copy the item

`wfu-layout-item-part` =&#x20;

* `element` (default) - move the element and its children
* `children` - move only the children of the element

`wfu-layout-item-position` =&#x20;

* `bottom` | `end` (default) - layout at the bottom of the container
* `top` | `start` - layout at the top of the container &#x20;

wfu-layout-item-name (special) = TEXT-STRING&#x20;

* Used for e.g. tab name







