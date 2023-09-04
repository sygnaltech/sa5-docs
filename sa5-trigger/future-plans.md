# Future Plans 🧪

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

Currently we have link-click trigger types

Considering scrolling triggers, and timer-based triggers.&#x20;

Inactivity-timer based triggers&#x20;

Technical Notes



&#x20;
