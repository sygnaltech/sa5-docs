---
description: Invoke the specified event when the element scrolls into view
---

# Scroll Into View Trigger

{% hint style="info" %}
This Trigger fires only once.&#x20;
{% endhint %}

{% hint style="warning" %}
Scroll trigger interactions currently don’t work on iOS devices (iPhone, iPad, iPod) due to Apple’s security restrictions on running scripts during browser scrolling. This limitation is documented in the Apple developer library.&#x20;
{% endhint %}

## Use Cases&#x20;

* Trigger a modal   &#x20;

## Usage Notes&#x20;

### `sa-trigger-scrollintoview` = ( _event name_ )&#x20;

Place on any element that should be invoke the specified event when it is scrolled into view. &#x20;

Assign whatever event name you like, depending on your trigger-event-action setup.&#x20;

```html
<div sa-trigger-scrollintoview="my-event"></div>
```

## Future

Allow repeat triggering&#x20;

* Once
* Unlimited, but element must leave page to reset &#x20;

