# Triggers

## SA5 Events&#x20;

{% hint style="warning" %}
_**NEW!**_**&#x20; UNDER TESTING 🧪**\
Learn more about [SA5 Events](../../overview/events/events/) here. &#x20;
{% endhint %}

SA5 Events is a centralized pub-sub event system which makes triggers and actions consistent throughout all SA5 modules.&#x20;

Modals is one of the first modules we're refitting with this capability.&#x20;

### Modal Triggers&#x20;

[SA5 Triggers](../../overview/events/triggers/)&#x20;

Common triggers used to;    &#x20;



| Trigger                                                                         | Notes   |
| ------------------------------------------------------------------------------- | ------- |
| [Click Trigger](../../overview/events/triggers/click-triggers.md)               |         |
| [Timer](../../overview/events/triggers/timer-trigger.md)                        |         |
| [Scroll into View](../../overview/events/triggers/scroll-into-view-trigger.md)  |         |
| Scroll Position 🧪                                                              |         |
| Exit Intent 🧪                                                                  |         |







### Modal Actions&#x20;

#### `sa-event-action-modal-open` = ( _event-name_ )&#x20;

When the event event-name is invoked, open the current modal.&#x20;

Place this directly on the `wfu-modal` element that you want to open.   &#x20;



### Future&#x20;

sa-event-action-modal-hide&#x20;

sa-event-trigger-modal-opened&#x20;

sa-event-trigger-modal-closed&#x20;





## Modal-Specific Triggers&#x20;

{% hint style="warning" %}
**DEPRECATED** \
These attributes are fully supported but considered **deprecated**. \
[SA5 Events](triggers.md#sa5-events) is the modern way to trigger modals.&#x20;
{% endhint %}



| Trigger             | SA5 Modals               | SA5 Events         |
| ------------------- | ------------------------ | ------------------ |
| Click               | wfu-modal-trigger-click  | SA5 Events Action  |
| Timer               | wfu-modal-trigger-timer  |                    |
| Scroll Position 🧪  |                          | SA5 Event Trigger  |
| Scroll into View 🧪 |                          |                    |
| Exit Intent 🧪      |                          |                    |
|                     |                          |                    |









<table><thead><tr><th width="220">Trigger</th><th>Type </th><th></th></tr></thead><tbody><tr><td>Click <br><code>wfu-modal-trigger-click</code> = ( modal-name ) </td><td>Manual</td><td>Defined on any button, link, or other element </td></tr><tr><td>Timer <br><code>wfu-modal-trigger-timer</code> = ( time in milliseconds ) </td><td>Automatic</td><td>Configured in seconds </td></tr><tr><td>Scroll Position 🧪</td><td>Automatic</td><td>Configured for a specific page % or a specific px position </td></tr><tr><td>Scroll into View 🧪</td><td>Automatic</td><td>Tied to an element</td></tr><tr><td>Exit Intent 🧪</td><td>Automatic</td><td>When the mouse moves outside of the page canvas </td></tr><tr><td>Gate</td><td>Manual</td><td></td></tr></tbody></table>





## Usage Notes ( Modal Setup )

There are many different ways to trigger a modal open. Depending on the type of trigger, these attributes will be placed either on a triggering element, or on the modal element itself.&#x20;

### I want this button or element to trigger my modal on click

On the button or element to be clicked, add this attribute;

`wfu-modal-trigger-click` = ( modal-name )&#x20;

Specify the modal's name that you want to open.&#x20;

### I want the modal to appear after X milliseconds

Triggers the modal when a timer has elapsed, starting from page load.&#x20;

Place this directly on the modal element.&#x20;

`wfu-modal-trigger-timer` = ( time in milliseconds )&#x20;

{% hint style="info" %}
1 second = 1,000 ms, so if you want to wait 5 seconds, set the value to `5000`.
{% endhint %}

<table><thead><tr><th>Trigger</th><th width="130">Trigger Type</th><th>Attribute </th><th>Value</th><th>Notes </th></tr></thead><tbody><tr><td>Click</td><td>Direct</td><td><code>wfu-modal-trigger-click</code> </td><td>Modal name</td><td>Place on the triggering button, link, or element</td></tr><tr><td>Timer</td><td>In-Direct</td><td><code>wfu-modal-trigger-timer</code> </td><td>Time in milliseconds</td><td>Place on the modal element directly</td></tr></tbody></table>

{% hint style="success" %}
This is being combined with SA5 Trigger.  \
Event = open modal\
Action&#x20;
{% endhint %}



























Types;&#x20;

* Manual triggers are user-actioned. These can be configured to ignore modal suppression even if it has already been closed.&#x20;
* Automatic triggers will only open the modal if it is un-suppressed.&#x20;

Suppression;







Goals;

* Timed open, in ms
  * Auto unhide
  * Or, click trigger, for interaction
  * Respects suppression setting
* Triggered open, by scroll
* Triggered open, by exit intent&#x20;
* Timed close, in ms
  * Element removal
  * Or, click trigger, for interaction
  * ? Option to suppress



