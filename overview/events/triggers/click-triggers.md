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

## Future&#x20;

### Link Triggers&#x20;

Place on a container, esp. a rich text element.&#x20;

#### `sa-trigger-click:context` = `child-links`&#x20;

{% hint style="success" %}
This changes the trigger setup so that the parent element is ignored, and only links within it are triggered.&#x20;
{% endhint %}

Generally you would also also specify a namespace;&#x20;

#### `sa-trigger-click:ns` = ( _namespace_ )&#x20;

### Link Triggers | Example&#x20;

{% code overflow="wrap" %}
```html
<div class="w-richtext" sa-trigger-click="*" sa-trigger-click:context="child-links" sa-trigger-click:ns="myns">
  <p>Some text and <a href="##mylink">a link</a></p> 
</div>
```
{% endcode %}

In this example;

* A Webflow Richtext element is being used&#x20;
* The `:context` attribute is used and specifies `child-links`&#x20;
* The `:ns` attribute is used and specifies `myns` as the namespace name&#x20;
* Within it is a link, with an href of `##mylink`&#x20;

In this setup;&#x20;

* All links beginning with `##` are treated as SA5 Triggers.&#x20;
* The event name they trigger follows the `##`, in this example the event name is `mylink`&#x20;
* They are handled as click triggers due to the attribute on the rich text element, and the :context setting&#x20;

Inside,&#x20;

`##link2`&#x20;

This is a click trigger for that event&#x20;

In this example;&#x20;

The event fired on link click will be `ns1.link2` &#x20;



Consider sa-trigger-click:\*   as the indicator for children&#x20;











