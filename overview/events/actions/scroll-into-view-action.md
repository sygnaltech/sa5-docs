---
description: Invoke the specified event when the element scrolls into view
---

# Scroll Into View Action

{% hint style="warning" %}
Scroll trigger interactions currently don’t work on iOS devices (iPhone, iPad, iPod) due to Apple’s security restrictions on running scripts during browser scrolling. This limitation is documented in the Apple developer library.&#x20;
{% endhint %}

## Use Cases&#x20;

* Trigger a modal   &#x20;

## Usage Notes&#x20;

### `sa-action-scrollintoview` = ( _event name_ )&#x20;

Place on any element that should be invoke the specified event when it is scrolled into view. &#x20;

Assign whatever event name you like, depending on your trigger-event-action setup.&#x20;

```html
<div sa-trigger-scrollintoview="my-event"></div>
```

## Future&#x20;

[https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)&#x20;





sa-action-scrollintoview:behavior &#x20;

* smooth ( default )&#x20;

sa-action-scrollintoview:block

* center ( default )&#x20;

sa-action-scrollintoview:inline&#x20;

* nearest ( default )&#x20;
