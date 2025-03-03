---
description: Invoke an Event by clicking any element
---

# Click Triggers

## Use Cases&#x20;

* Click a button to select a specific tab &#x20;

## Usage Notes&#x20;

### `sa-trigger-click` = ( _event name_ )&#x20;

Place on any element that should be invoke the specified event when it is clicked. &#x20;

Assign whatever event name you like, depending on your trigger-event-action setup.&#x20;

## Example &#x20;

This is a simple _mirror-click_ setup.  Clicking the link clicks the corresponding button.  they are connected by virtue of the Event name.&#x20;

Trigger;

```html
<a sa-trigger-click="my-event">Click me</a>
```

Action;

```html
<button sa-action-click="my-event">Hidden button</button>
```



