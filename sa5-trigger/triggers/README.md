# Triggers 🧪

The sub-pages in this section contain specific trigger events.&#x20;

Make certain to ready the About page for an understanding of&#x20;



{% hint style="info" %}
Triggers from modal invocation should be placed here.&#x20;
{% endhint %}





A Trigger invokes an Event which results in Actions.&#x20;

|                                                                                                                                                                                                                                              |                                                                                                |   |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | - |
| <ul><li>A click on an element</li><li>A click on a link</li><li>Mouse over over something</li><li>Scrolling an element into view</li><li>Scrolling to % position on the page</li><li>An interaction occurring, reaching a certain </li></ul> | <ul><li>Fire an interaction</li><li>Click another element</li><li>Navigate to a page</li></ul> |   |
|                                                                                                                                                                                                                                              |                                                                                                |   |
|                                                                                                                                                                                                                                              |                                                                                                |   |



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





