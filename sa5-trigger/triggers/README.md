# Triggers 🧪







### Trigger&#x20;

An **SA5 Trigger** is something that occurs, which invokes an _SA5 Event_.  These are generally classified as;

* User triggers.  Click, scroll, hover, etc.&#x20;
* Systems triggers.  Timers, etc.&#x20;
* Webflow triggers. &#x20;
  * Interactions, at any point in the interaction.&#x20;
  * Possibly, certain other system.level mechanics... open or close of a hamburger menu
  * Tab switches
  * Slider events&#x20;
* Custom triggers.  Custom code-triggered events. &#x20;
* Breakpoint change triggers.&#x20;
* Keyboard triggers.&#x20;
* Mutation Observer triggers. &#x20;
* Custom triggers. &#x20;
* Other triggers. &#x20;

### Event&#x20;

An **SA5 Event** is effectively a messaging pipeline, which has a name.  When an event fires, it triggers a series of _SA5 Actions_. &#x20;

* Multiple Triggers can invoke the same Event.&#x20;
* An Event can perform several Actions&#x20;

{% hint style="info" %}
We're considering the ability for a single Trigger to invoke multiple Events. This may be limited to certain trigger types.&#x20;
{% endhint %}

### Action&#x20;

An **SA5 Action** is a resulting action that can be invoked when an SA5 Event occurs.

Examples;

* A click on another element&#x20;
* Navigation
* A webhook call&#x20;
* A logged event&#x20;
* A GTM event&#x20;
* etc.&#x20;

{% hint style="info" %}
We're considering the concept of a Trigger as an Action type, so that we can chain Trigger-Event-Action sequences.&#x20;
{% endhint %}









The sub-pages in this section contain specific trigger events.&#x20;

Make certain to ready the About page for an understanding of&#x20;



{% hint style="info" %}
Triggers from modal invocation should be placed here.&#x20;
{% endhint %}





A Trigger invokes an Event which results in Actions.&#x20;

| Trigger                                                                                 | Applies to             | Notes                                |
| --------------------------------------------------------------------------------------- | ---------------------- | ------------------------------------ |
| <ul><li>An interaction occurring, reaching a certain point in the interaction</li></ul> |                        |                                      |
| Click                                                                                   | Any element            | Also touch                           |
| Mousover on an element                                                                  | Any element            | Only works on devices with a pointer |
| Scroll into view                                                                        | Any element            |                                      |
| Focus                                                                                   | Any focusable element  |                                      |
| Blur                                                                                    |                        |                                      |
| Change                                                                                  | Input elements         |                                      |
| Scroll to                                                                               |                        |                                      |
| Video played                                                                            | Video elements         |                                      |
| Video paused                                                                            |                        |                                      |
| Video at %                                                                              |                        |                                      |
| Link Click                                                                              |                        |                                      |



Triggers









## Element-Level Triggers

<table><thead><tr><th width="130">Type</th><th width="197">Trigger</th><th>Notes</th><th></th></tr></thead><tbody><tr><td>Any</td><td><a href="click-triggers.md">Click</a></td><td>wfu-trigger-click </td><td>wfu-action-click </td></tr><tr><td>Any</td><td><a href="dynamic-interaction-trigger-links.md">Link click</a></td><td>Used in <code>##event</code> constructions </td><td></td></tr><tr><td>Any</td><td>Scrolled into view</td><td>wfu-trigger-scrollintoview</td><td></td></tr><tr><td>Any</td><td>Hover </td><td>wfu-trigger-hover</td><td></td></tr><tr><td>Any</td><td>Interaction trigger</td><td>wfu-trigger-ix</td><td></td></tr><tr><td>Video</td><td>Video Played</td><td>wfu-trigger-play</td><td>wfu-action-play </td></tr><tr><td>Video</td><td>Video Paused</td><td>wfu-trigger-pause</td><td>wfu-action-pause </td></tr><tr><td>Video</td><td>Video Ended</td><td>wfu-trigger-finished</td><td></td></tr><tr><td>Video</td><td>Video Progression %</td><td>wfu-trigger-seek</td><td>wfu-action-seek </td></tr><tr><td>Dropdown</td><td>Opened</td><td>wfu-trigger-opened</td><td>wfu-action-open </td></tr><tr><td>Dropdown</td><td>Closed</td><td>wfu-trigger-closed</td><td>wfu-action-close </td></tr><tr><td>Tab</td><td>Changed</td><td></td><td></td></tr><tr><td>Form</td><td>Submit Attempt</td><td>wfu-trigger-submit </td><td></td></tr><tr><td>Form</td><td>Submit Success</td><td>wfu-trigger-submit-success </td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>ECom</td><td>Cart Opened</td><td>wfu-trigger-open </td><td>wfu-action-open </td></tr><tr><td>ECom</td><td>Cart Closed</td><td>wfu-trigger-close </td><td>wfu-action-close </td></tr><tr><td>ECom</td><td>Item Added</td><td>wfu-trigger-add-item </td><td></td></tr><tr><td>ECom</td><td>Item Removed</td><td>wfu-trigger-remove-item </td><td></td></tr></tbody></table>







## Page-Level Triggers&#x20;



| Trigger            | Description |                            |
| ------------------ | ----------- | -------------------------- |
| Timer              |             | wfu-trigger-timer          |
| Page scrolled to % |             | wfu-trigger-scrollpercent  |
| Exit intent        |             | wfu-trigger-exitintent     |
| Rageclick          |             |                            |
| Inactivity         |             |                            |





## Interaction Triggers&#x20;

Refers to a category of triggers that are invoked by an interaction.&#x20;

Since IX2 does not include support for mouse / keyboard events&#x20;









Make these easier to find&#x20;

```html
<script type="application/sa5+json" handler="ConversionEvent">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": ""  
}
</script>
```





? change @type to @handler   &#x20;





