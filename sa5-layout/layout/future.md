# Future

{% hint style="success" %}
**SA5** is continually evolving.  Want to [sponsor a feature](../../overview/sponsor.md)?  Learn more at the link. &#x20;
{% endhint %}











Future ideas include;&#x20;

* Copy v. Move &#x20;
* Control the sequence of operations?&#x20;
* Part control
* Position control
  * Sorting control?&#x20;
  * Move to child position &#x20;
* Handlers
  * Slider&#x20;
  * SwiperJS
  * Lightbox Galleries
  * Accordion
  * Dropdown Navs
* Distributed layouts, where an item can be placed in one of multiple locations
* Item sets, which acts as a card set

## Group Layouts

Tar

## Distributed Layouts

Some possibilities we're considering;&#x20;

Allow multiple containers to have the same name, along with some optional rules for distribution.&#x20;

* On layout distribute items randomly across those groups
* Random distribution
  * Place each item in a random container
* Flow distribution
  * N items in the first matching container
  * M items in the second matching container
  * etc. crop overflow&#x20;
* Ordered segmentation
  * 1 - 7 in this specific container
  * 8 - 23 in that specific container
  * 24+ in the other ( or crop overflow )&#x20;
* Ordered segmentation by portion
  * 50% to group 1, 50% to group 2&#x20;
* Group-match layouts
  * Identify possible matching groups ( regex, eval, custom function )
  * Allocate to first,&#x20;

And possible mixes, like random ordered segmentation by portion

Possible attributes;&#x20;

Source elements, ordered, or random ( pre-build an element pointer list and randomie it? )&#x20;

Container constraints. Item positions min and max. Max items total. % of allocation, and max.  Support multiple constraints, like width, max width, min width

In general;

* Item-centric-layout. Go through each item, and identify where it lay it out.&#x20;
  * Matching process, identifying which group(s) are suitable for placing this item
  * Allocation process
* Group-centric-layout. Go through each group, and identify what lays out in it. Group specifies the matching&#x20;
  * Matching process, identifies which item(s) are suitable for placing in this group
  * Allocation process
    * % of items
    * Min/max of items&#x20;

Algo;&#x20;

* Get all groups
  * Segment by ns
  * Capture ordinal positioning within NS
  * Allow ordering override via attribute?&#x20;
* Get all items, with positioning within NS
  * Segment by ns&#x20;
  * Capture ordinal positioning within NS
    * Allow ordering override via attribute? &#x20;
* Decide on group/item-centric layout
  * Depends on layout type?&#x20;
    * Should be consistent&#x20;

Use cases;

[https://discourse.webflow.com/t/display-collection-data-outside-of-data-collection/286328/3](https://discourse.webflow.com/t/display-collection-data-outside-of-data-collection/286328/3)

## Item Sets

Card deck concept, we may want some deck level controls&#x20;

Crop overflow... extra items that do not "fit", either leave where they are, or delete them.&#x20;



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

Ability to do more complex tabs&#x20;

Specify a special sub-layout item which is pulled out of line for this purpose

[https://www.apple.com/ca/today/calendar/](https://www.apple.com/ca/today/calendar/)

Support other card-based layouts, such as accordion;&#x20;



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

## Old Notes



<figure><img src="../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>





