# Actions

An **SA5 Action** is an action that is be performed when an [SA5 Event](../events/) occurs.

Example Actions include;

* Simulate a click on an element&#x20;
* Navigate to another URL&#x20;
* Call a webhook&#x20;
* Submit a form&#x20;
* Switch a tab&#x20;
* etc.&#x20;

### Types of Actions&#x20;

Broadly, there are two types of SA5 Actions...&#x20;

* **Element Actions.**  An element-specific action such as clicking a button or submitting a form. These are generally configured directly on the target element, using custom attributes.&#x20;
* **Page Actions.** These are actions that occur in the context of the page, but are not tied to any specific element. We generally configure these using a special SA5 script action block.&#x20;



Modal Actions &#x20;





## Element Actions&#x20;



|                                                |   |   |
| ---------------------------------------------- | - | - |
| [Tab Element Actions](tab-element-actions.md)  |   |   |
| Slider Element Actions                         |   |   |
|                                                |   |   |









## Element-Level Actions

These actions are generally defined using custom attributes.&#x20;

| Action                                          | Detail         | Applies to                   | Description                                          | Notes                                                                                               |
| ----------------------------------------------- | -------------- | ---------------------------- | ---------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| <p>Click<br>wfu-action-click </p>               |                | Any element                  | Fire a click event from script to trigger an element |                                                                                                     |
| [Interaction](interaction-actions.md)           |                |                              |                                                      | `wfu-action-click`, with the element also configured as a click trigger for a Webflow interaction.  |
| <p>Script<br>wfu-action-script </p>             |                | ? Special SA5 block element  | Invoke a script, or function                         |                                                                                                     |
| <p>Function<br>wfu-action-function </p>         |                |                              |                                                      | Invoke a function                                                                                   |
| Scroll Into View                                |                | Any Element                  |                                                      | Offset?                                                                                             |
| Submit                                          |                | Form                         |                                                      |                                                                                                     |
| Popup                                           | Optional scope | SA5 Popup                    |                                                      |                                                                                                     |
| <p>Add Class<br>wfu-action-class-add</p>        | Class name     |                              | Adds a class                                         |                                                                                                     |
| <p>Remove Class <br>wfu-action-class-remove</p> | Class name     |                              | Removes a class                                      |                                                                                                     |
| <p>Toggle Class<br>wfu-action-class-toggle</p>  | Class name     |                              | Toggles the presence/absence of a class              |                                                                                                     |
| Hide / Show Elements                            |                |                              |                                                      |                                                                                                     |







Mode

Hide/show certain elements

Class adder, etc&#x20;



Based on localStorage / cookie / sessionStorage &#x20;











### Video Element

Play

Pause

Seek   sec or %&#x20;

Fullscreen&#x20;







### Lottie & Rive Elements&#x20;

Play

Pause&#x20;









The underlying link approach has proven very useful. We want to expand the capabilities to handle other use cases;

* Trigger interactions ( via a button trigger )&#x20;
* Trigger chatbots
* Trigger Gista with a query&#x20;
* Trigger custom JS, JS-based modals, etc.&#x20;

And also possibly;&#x20;

* Trigger GTM datalayer and events &#x20;







## Page-Level Actions&#x20;

These actions are generally defined by an SA5 Configuration Block;&#x20;

| Action      |                             |   |
| ----------- | --------------------------- | - |
| Navigate    |                             |   |
| Script      | nvoke a script, or function |   |
| OnLoad      |                             |   |
| OnScroll%   |                             |   |
| Exit Intent |                             |   |
| Timer       |                             |   |



```
SA5 block 

```









## Event Detail &#x20;

In some cases, we want to pass detail;&#x20;

* Context or scope so that the event is more specific, e.g. invoke a specific pop-up from a CMS-driven collection list of popups.&#x20;
* Class names or other key data needed by the Action handler.&#x20;

Ideally we want to support multiple detail pieces in the future, and to allow for multiple non-conflicting Actions on the same element.&#x20;

To support this, I'm considering details as a suffix on the event, e.g.; &#x20;

| Suffix     | Notes                                                                                    |
| ---------- | ---------------------------------------------------------------------------------------- |
| \*:class   | Might indicate a specific class name to apply in the case of class add / remove / toggle |
| \*:item    | Limit to a specific item                                                                 |
| \*:offset  | Used to offset a scroll-to-element position                                              |









### Triggering an Event w/ Details&#x20;

Detail





```html
<div wfu-trigger-click="popup" wfu-trigger-click:item="potato"> ... </div> 
```





More verbose, but better for data-binding in a collection list.&#x20;

```html
<div wfu-trigger-class-add="event1" wfu-trigger-click:class="red-text"> ... </div> 
```





### Abbreviated Events w/ Details&#x20;

In some Triggers & Actions it may be useful to offer a simplified syntax for convenience when no custom attribute data-binding is needed;&#x20;

For example, this click trigger-&#x20;

```html
<div wfu-trigger-click="popup#potato"> ... </div> 
```

* Is triggered by a click
* Invokes the Event `popup` on elements where item is `potato`. &#x20;



Meanwhile this&#x20;

Or;&#x20;

```html
<div wfu-action-class-add="event1#foo"> ... </div> 
```

Finds all elements tagged with Triggers a click Action on all elements tagged with the popup event, where the item is potato. &#x20;





### Putting it Together&#x20;



Here's an example from SA5;&#x20;

Constructing event detail; &#x20;

```html
<div wfu-trigger-click="popup">
  <p>
    <a href="##potato"></a>    
  </p> 
</div> 

<div>
  <div> <!-- interactions popup -->  
    <button wfu-action-click="popup" wfu-action-click:item="potato">Invoke popup</button> 
    ...
  </div> 
</div>
```

Receiving event detail; &#x20;



## Trigger Source Gating&#x20;

{% hint style="info" %}
**UNDER CONSIDERATION.**  &#x20;
{% endhint %}

Certain Actions can be restricted to certain trigger sources.&#x20;

We may distinguish between different Trigger sources, such as user-invoked triggers, v. system-invoked triggers. &#x20;

| Trigger type | User sourced                | System sourced                                                                 |
| ------------ | --------------------------- | ------------------------------------------------------------------------------ |
| Click        | Yes, user clicks on an item | Yes, script-generated click, or system-generated click from another SA5 Event  |
| Timer        | No                          | Yes, always                                                                    |
| etc.         |                             |                                                                                |

This differentiation may be useful for;&#x20;

* Handling different action sources differently&#x20;
* Preventing loops by system-generated events&#x20;



System-triggers &#x20;

This could be specified by a prefix to the event name.

For example, `wfu-action-click` = `event-name` &#x20;

|                         | Invoked by                              |   |
| ----------------------- | --------------------------------------- | - |
| `event-name`            | Any trigger source, standard convention |   |
| $event-name             | Only                                    |   |
| \&event-name            |                                         |   |
| event-name#event-detail |                                         |   |





Defined a timer as a trigger&#x20;



```html
<script type="application/sa+json" handler="Action.Script">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ScriptAction",
  "@version": "0.1",
  "timer": "60", 
  "timerRepeat": "120",
  "event": "my-event" 
}
</script>
```







## Technical Notes

### Categories of Actions&#x20;

We have...&#x20;

* **Element Actions.**  An element-specific action such as clicking a button of submitting a form. These are generally configured directly on the target element.&#x20;
* **Script Actions.**  An action that is defined by a special SA5 script action block.&#x20;

Timer example;&#x20;

```html
<script type="application/sa+json" handler="Action.Script" event="my-event">
{
  "@context": "https://attr.sygnal.com",
  "@type": "TimerAction", 
  "@version": "0.1",
  "timer": "60", 
  "timerRepeat": "120"
}
</script>
```

Navigation example;&#x20;

```html
<script type="application/sa+json" handler="Action.Script" event="event1">
{
  "@context": "https://attr.sygnal.com",
  "@type": "NavigationAction", 
  "@version": "0.1",
  "url": "https://something.com",
  "target": "_blank" 
}
</script>
```

































