---
description: When an Event fires, click the specified element
---

# Click Actions



## Use Cases&#x20;

* Place on a form submit button to trigger a submit attempt&#x20;
* Place on a tab to select that tab&#x20;
* Place on a slider next button to advance&#x20;
* Place on a hidden button, which is wired as a click trigger to a Webflow interaction.  This allows you to invoke an interaction anytime you like.&#x20;

## Usage Notes&#x20;

### `sa-action-click` = ( _event name_ )&#x20;

Place on any element that should be clicked when the specified event is invoked. &#x20;

Assign whatever event name you like, depending on your trigger-event-action setup.&#x20;

## Example&#x20;

This is a simple _mirror-click_ setup.  Clicking the link clicks the corresponding button.  they are connected by virtue of the Event name.&#x20;

Trigger;

```html
<a sa-trigger-click="my-event">Click me</a>
```

Action;

```html
<button sa-action-click="my-event">Hidden button</button>
```













