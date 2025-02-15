# Click Triggers

Click triggers are one of the most basic trigger types.

Click an item an an SA5 Event invokes matching events.&#x20;

## Use Cases&#x20;

* Click a button, and have a tab change&#x20;
* Click a tab, and have a separate click-triggered interction fire&#x20;

## Example&#x20;

Trigger;

```html
<a wfu-trigger-click="my-event">Click me</a>
```

Action;

```html
<button wfu-action-click="my-event">Hidden button</button>
```





