---
description: Invoke the specified event when the element scrolls into view
---

# Hover Trigger



## Usage Notes&#x20;

### `sa-trigger-mouseenter` = ( _event name_ )&#x20;

Place on any element that should invoke the specified event when the mouse enters. &#x20;

Assign whatever event name you like, depending on your trigger-event-action setup.&#x20;

```html
<div sa-trigger-mouseenter="my-event"></div>
```

### `sa-trigger-mouseleave` = ( _event name_ )&#x20;

Place on any element that should invoke the specified event when the mouse leaves. &#x20;

Assign whatever event name you like, depending on your trigger-event-action setup.&#x20;

```html
<div sa-trigger-mouseleave="my-event"></div>
```









## Future&#x20;

Allow restricted triggering&#x20;

* Once
* Unlimited, but element must leave page to reset &#x20;

Do this at the event level?&#x20;

