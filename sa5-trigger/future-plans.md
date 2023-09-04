# Future Plans 🧪📝

The underlying link approach has proven very useful. We want to expand the capabilities to handle other use cases;

* Trigger interactions ( via a button trigger )&#x20;
* Trigger chatbots
* Trigger Gista with a query&#x20;
* Trigger custom JS, JS-based modals, etc.&#x20;

And also possibly;&#x20;

* Trigger GTM datalayer and events &#x20;

## Syntax Expansion

Likely we'll support named or "slotted" formats;&#x20;

* `##` - Generic trigger prefix
  * e.g. `##glossaryterm`
* `#1#` - Typed trigger prefix
  * e.g. `#1#abc`

Essentially;

* Identify a trigger-capable area ( can be page-wide )
* Find links that begin with `#`
* and contain
  * May be able to regex match `#..#..` in selector.&#x20;

{% code overflow="wrap" %}
```javascript
const elements = [...document.querySelectorAll('a[href^="#"][href*="#"]:not([href="#"])')].filter(el => {
    const match = el.getAttribute('href').match(/^#(\w*)#(\w+)$/);
    return match !== null;
});
```
{% endcode %}

Extract the name, trigger the name.&#x20;

On page load, build a list of trigger targets, e.g. IX buttons

Typed trigger wiring process;

* Match to known targets, by name&#x20;

## Registered Type Handlers

* ix
* gista ( register and define these as typed trigger handlers in the config code )&#x20;

### Generic trigger

* Create attribute first&#x20;
  * wfu-trigger-type
  * wfu-trigger-id&#x20;
* wfu-trigger-target-type
* wfu-trigger-target-id

## Other Trigger Types

Currently we have **click** trigger types

Considering scrolling triggers, and timer-based triggers.&#x20;

Inactivity-timer based triggers&#x20;

## Technical Notes

### What is a Trigger?

Currently SA5 supports the click trigger type only.  In this context a trigger is an element such as a link, button, or DIV that is clicked.&#x20;

In SA5 terms, a trigger may have these properties;

* Handler. Identifies how the trigger will be handled. Determined as follows;
  * If the trigger element has the attribute `wfu-trigger-handler` - identifies the handler for the trigger.&#x20;
  * If unspecified, and the trigger is in a group, that handler is used instead.&#x20;
  * If there is no group-specified handler, then the trigger is "unhandled," and defaults to a click handler.&#x20;
* ID. Uniquely identifies the trigger, or more specifically the triggering action you want performed. In the case of a click trigger, this identifies the click target.&#x20;
  * `wfu-trigger-id` - the unique ID of the trigger&#x20;
* Group (optional). If the trigger is in a named group, that group name is applied to the trigger. It acts as a namespace.&#x20;
  * wfu-trigger-group
* Content. A trigger element may also contain content;
  * Plain-text content ( innerText )
  * HTML content ( innerHTML )

### What are Trigger Handlers?

Trigger handlers identify how a particular trigger is handled. For example-&#x20;

* Click a matching target link.
* Prompt an AI chatbot
* Center a pin in Google maps
* Start a WhatsApp message
* Invoke custom code

The trigger's _handler_ is determined as follows;

* If the trigger itself has a `wfu-trigger-handler`, that handler is used
* If not, we check for a trigger group, and a `wfu-trigger-group-handler`.&#x20;
* If not, the trigger is considered _unhandled_. It defaults to using the **click handler**, and can be captured in custom code. &#x20;

### What is a Trigger Group?

A trigger group is defined as the nearest ancestor ( containing ) element of a trigger which has the custom attribute of `wfu-trigger-group`.&#x20;

A group serves two purposes.&#x20;

* It can be named, as in `wfu-trigger-group` = (name), in which case that name becomes a namespace for the triggers. Some handlers will use this as a scoping mechanism, so that only targets also matching that group will be triggered
* Default trigger handlers. A group can additionally define a `wfu-trigger-group-handler` which acts as the handler for any _unhandled_ triggers within.&#x20;

### What are Trigger Targets?&#x20;

Some trigger handlers such as the **click handler** can utilize a target element that you specify.&#x20;

These are identified by wfu-trigger-target = ID. OPTIONALLY They can be namespaced, by wfu-trigger-target-group, which must match.&#x20;

## Setting It Up

### Configure the Trigger Library ( optional )

Register handlers, such as Gista.&#x20;

{% code overflow="wrap" %}
```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['triggerConfig', 
  (config) => {
    config.handlers.add ('gista'); 
    return config;
  }]); 
</script> 
```
{% endcode %}

### Custom Code in the the Trigger Callback ( optional )

Custom-code to handle specific trigger events.&#x20;

{% code overflow="wrap" %}
```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['triggerEvent', 
  (event) => {
    console.log("TRIGGER FIRED", event); 
  }]); 
</script> 
```
{% endcode %}

### Setup

A **click trigger** can be placed on any element that can be clicked. It is governed by;

* `wfu-trigger-type` - the type of trigger, which functions as a namespace
* `wfu-trigger-handler` - identifies the handler for the trigger. If unspecified, and the trigger is in a group, that handler is used instead. If there is no group-specified handler, then the trigger is "unhandled," and will only fire events in code. &#x20;
* `wfu-trigger-id` - the unique ID of the trigger&#x20;
* It can also contain content

All click triggers MAY be in a trigger group. This would be the nearest containing element which has the attributes;

* `wfu-trigger-group` - an optional name
* `wfu-trigger-group-type` - an optional default type, which will be applied to untyped (generic) triggers

A **trigger target** can also be placed on any element that can be clicked. Typically this would be a button that is associated with an interaction. It is goverened by;

* wfu-trigger-target-type - type type of target, which functions as a namespace and must match the trigger
* wfu-trigger-target-id - unique ID of the target&#x20;

### Activation

When a trigger is activated, an event is raised in custom code, with-

* Trigger container name
* Trigger type
* Trigger ID

If trigger target elements are found which match that trigger, they will also be clicked.&#x20;

If a handler has been associated with the trigger type, it will be invoked, e.g. Gista.&#x20;

### How it Works

Pre-processing;

* Identifies relevant areas to process links in. These are referred to as `trigger-containers`.
  * Identified with a wfu-trigger-area custom attribute. It can optionally be given a unique name
  * Optionally, set the default type with wfu-trigger-default-type =&#x20;
* Resolves links in those areas, including the parent node&#x20;





&#x20;
