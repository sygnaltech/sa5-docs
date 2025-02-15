# Events 🧪



An SA5 Event is a named construction, which connects Triggers and Actions.&#x20;

<img src="../.gitbook/assets/file.excalidraw (3).svg" alt="" class="gitbook-drawing">

Events are tracked by SA5 and always have a name, so that they can be invoked and logged. &#x20;

Element Click Trigger

wfu-trigger-click="event1"

wfu-action-click="event1"&#x20;



Sa5.Events.Invoke("event1");&#x20;

















Currently, all events must be named.&#x20;

## Technical Notes & Consideration&#x20;

### Preventing Loops&#x20;

Simple - threading. limit the number of automated events that can chain. &#x20;

Event stack?  Breadcrumbs?  Detect loops? &#x20;







