# Element Actions ❺🧪



**Actions** are a developing concept in the SA5 Element Lib, which refers to the ability to tag an element with attributes, that "remote control" another element on the page.

Use cases;

* Navigate a swiper, tab, or accordion element
  * First, last, next, prev, specific item #&#x20;
* Change the locale
* ? Hide and show elements

Conceptual rules;&#x20;

* Actions consist of;
  * An action
  * A target
  * Optional data
  * A trigger type ( default click )&#x20;
* Actions are the center of the config&#x20;
  * Target is optional for some actions &#x20;

| Action   | Tabs, Swiper, Accordion | Locale Switcher | Any |
| -------- | ----------------------- | --------------- | --- |
| first    |                         |                 |     |
| last     |                         |                 |     |
| next     |                         |                 |     |
| nextLoop |                         |                 |     |
| prev     |                         |                 |     |
| prevLoop |                         |                 |     |
| goto     | Item #                  | ? Locale code   |     |
| Hide     |                         |                 |     |
| Show     |                         |                 |     |





On elements which&#x20;

### `wfu-action` = ( method ) <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

**Required.** I want my button or link to perform the following action on the targeted deck element.

Method is one of;

* `first` - select the first item
* `prev` - select the previous item
  * ~~`prevLoop`~~ - select the previous item or loop if we're on the first item ( considering )
* `next` - select the next item
  * ~~`nextLoop`~~ - select the next item or loop if we're on the last item ( considering )
* `last` - select the last item
* `goto` - select the specified item, as specified by `wfu-deck-action-item`&#x20;

### `wfu-action-target` = LOCALE-SWITCHER



**Optional.** Specifies the `wfu-tabs`, `wfu-slider` or `wfu-accordion` name you want your action to target.

If unspecified, it will look for the nearest parent deck element as the target. &#x20;

### `wfu-action-item` = ( item number | name )  <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

**Required for the `goto` action only.** Specifies the tab / slide you want to navigate to.&#x20;

* a number - indicates the item number, 1, 2, 3...&#x20;
* a string - activates the item with the specified name&#x20;

### `wfu-action-trigger` = ( trigger-type )  <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

One of;&#x20;

* `click` ( default )
* `scrollTo`&#x20;
* `scrollPercent`&#x20;
* `timer`
* `exitIntent`&#x20;



