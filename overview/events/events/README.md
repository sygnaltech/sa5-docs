# Events







## Simple v. Complex Events

Most events in SA5 Events are defined by attributes directly on the affected element.  However, there is a potential for "attribute glut" and complexity here in two situations;&#x20;

* If a single element has many possible Events triggering many possible Actions.&#x20;
  * e.g. A tabstrip where 10 buttons might activate 10 different tabstrip actions.&#x20;
* If an Event fires many different Actions on many different elements to a point where it's easy to lose track of the attributes in use.&#x20;
  * e.g. A button Trigger, whose Action triggers 100 different Events.&#x20;

In both cases, we can potentially centralize the admin with an Event configuration block.

This would look something like;

```
<script type="sa5-event+json" name="event1">
{
  "actions": [
    {
      "type": "scrollToPercent",
      "value": "50%"
    },
    {
      "type": "selectTabNum",
      "target": "tab1",
      "value": "2" 
    }
  ]
}
</script> 

```





There may be a case for supportin&#x20;







## Frequency Gating

Unlimited ( default )&#x20;

Once&#x20;

N-Times&#x20;

Max frequency ( no more than once every 500ms )    &#x20;















### Event&#x20;

An **SA5 Event** is effectively a messaging pipeline, which has a name.  When an event fires, it triggers a series of _SA5 Actions_. &#x20;

* Multiple Triggers can invoke the same Event.&#x20;
* An Event can perform several Actions&#x20;

{% hint style="info" %}
We're considering the ability for a single Trigger to invoke multiple Events. This may be limited to certain trigger types.&#x20;
{% endhint %}







An SA5 Event is a named construction, which connects Triggers and Actions.&#x20;

<img src="../../../.gitbook/assets/file.excalidraw (3).svg" alt="" class="gitbook-drawing">

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







