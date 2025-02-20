# Triggers 🧪

An **SA5 Trigger** is a user action or system state-change that occurs, which invokes an _SA5 Event_.  These are generally classified as;

* User triggers.  Click, scroll, hover, etc.&#x20;
* Systems triggers.  Timers, etc.&#x20;
* Webflow triggers. &#x20;
  * Interactions, at any point in the interaction.&#x20;
  * Open or close of a dropdown&#x20;
  * Tab switches
  * Slider events&#x20;
* Custom triggers.  Custom code-triggered events. &#x20;
* Breakpoint change triggers.&#x20;
* Keyboard triggers.&#x20;
* Mutation Observer triggers. &#x20;
* Custom triggers. &#x20;
* Other triggers. &#x20;

## SA5 Triggers&#x20;

### Types of Triggers

Broadly, there are two types of SA5 Triggers...&#x20;

* **Element Triggers.**  An element-specific Trigger that is tied to user-interaction with a specific element.  Clicking an element, changing a tab, scrolling an element into view are examples.&#x20;
* **Page Triggers.** These are Triggers that occur in the context of the page, but are not tied to any specific element. Scrolling a page to 50% of its length, a timer trigger, or an exit intent action are examples.  We generally configure these using a special SA5 script Trigger block.&#x20;





The sub-pages in this section contain specific trigger events.&#x20;

Make certain to ready the About page for an understanding of&#x20;



A Trigger invokes an Event which results in Actions.&#x20;

| Trigger                                                                                 | Applies to                    | Notes                                                                                                     |
| --------------------------------------------------------------------------------------- | ----------------------------- | --------------------------------------------------------------------------------------------------------- |
| <ul><li>An interaction occurring, reaching a certain point in the interaction</li></ul> |                               | Triggered by affecting a specific element, and a mutation observer is watching that element for chagnes.  |
| Click                                                                                   | Any element                   | Also touch                                                                                                |
| Mousover on an element                                                                  | Any element                   | Only works on devices with a pointer                                                                      |
| Scroll into view                                                                        | Any element                   |                                                                                                           |
| Focus                                                                                   | Any focusable element         |                                                                                                           |
| Blur                                                                                    |                               |                                                                                                           |
| Change                                                                                  | Input elements                |                                                                                                           |
| Scroll to                                                                               |                               |                                                                                                           |
| Video played                                                                            | Video elements                |                                                                                                           |
| Video paused                                                                            |                               |                                                                                                           |
| Video at %                                                                              |                               |                                                                                                           |
| Link Click                                                                              |                               |                                                                                                           |
| Hash change, like nav to `#hash`                                                        | hashchange event              | wfu-trigger-hashchange                                                                                    |
| Load w/ Hash                                                                            | load event, with the hash set | wfu-trigger-hashload                                                                                      |
| Hash                                                                                    | load or change                | wfu-trigger-hash                                                                                          |



Triggers









## Element-Level Triggers&#x20;

### All Elements



<table><thead><tr><th width="130">Type</th><th width="197">Trigger</th><th>Detail</th><th>Notes</th><th></th></tr></thead><tbody><tr><td>Any</td><td><a href="click-triggers.md">Click</a></td><td></td><td>wfu-trigger-click </td><td>wfu-action-click </td></tr><tr><td>Any</td><td><a href="dynamic-interaction-trigger-links.md">Link click</a></td><td></td><td>Used in <code>##event</code> constructions </td><td></td></tr><tr><td>Any</td><td>Scrolled into view</td><td></td><td>wfu-trigger-scrollintoview</td><td></td></tr><tr><td>Any</td><td>Hover </td><td></td><td>wfu-trigger-hover</td><td></td></tr><tr><td>Any</td><td>Interaction trigger</td><td></td><td>wfu-trigger-ix</td><td></td></tr><tr><td>Dropdown</td><td>Opened</td><td></td><td>wfu-trigger-opened</td><td>wfu-action-open </td></tr><tr><td>Dropdown</td><td>Closed</td><td></td><td>wfu-trigger-closed</td><td>wfu-action-close </td></tr><tr><td>Tab</td><td>Changed</td><td></td><td></td><td></td></tr><tr><td>Form</td><td>Submit Attempt</td><td></td><td>wfu-trigger-submit </td><td></td></tr><tr><td>Form</td><td>Submit Success</td><td></td><td>wfu-trigger-submit-success </td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>ECom</td><td>Cart Opened</td><td></td><td>wfu-trigger-open </td><td>wfu-action-open </td></tr><tr><td>ECom</td><td>Cart Closed</td><td></td><td>wfu-trigger-close </td><td>wfu-action-close </td></tr><tr><td>ECom</td><td>Item Added</td><td></td><td>wfu-trigger-add-item </td><td></td></tr><tr><td>ECom</td><td>Item Removed</td><td></td><td>wfu-trigger-remove-item </td><td></td></tr></tbody></table>



### Video Elements



<table><thead><tr><th width="130">Type</th><th width="197">Trigger</th><th>Detail</th><th>Notes</th><th></th></tr></thead><tbody><tr><td>Any</td><td><a href="click-triggers.md">Click</a></td><td></td><td>wfu-trigger-click </td><td>wfu-action-click </td></tr><tr><td>Any</td><td><a href="dynamic-interaction-trigger-links.md">Link click</a></td><td></td><td>Used in <code>##event</code> constructions </td><td></td></tr><tr><td>Any</td><td>Scrolled into view</td><td></td><td>wfu-trigger-scrollintoview</td><td></td></tr><tr><td>Any</td><td>Hover </td><td></td><td>wfu-trigger-hover</td><td></td></tr><tr><td>Any</td><td>Interaction trigger</td><td></td><td>wfu-trigger-ix</td><td></td></tr><tr><td>Video</td><td>Video Played</td><td></td><td>wfu-trigger-play</td><td>wfu-action-play </td></tr><tr><td>Video</td><td>Video Paused</td><td></td><td>wfu-trigger-pause</td><td>wfu-action-pause </td></tr><tr><td>Video</td><td>Video Ended</td><td></td><td>wfu-trigger-finished</td><td></td></tr><tr><td>Video</td><td>Video Progression %</td><td></td><td>wfu-trigger-seek</td><td>wfu-action-seek </td></tr><tr><td>Dropdown</td><td>Opened</td><td></td><td>wfu-trigger-opened</td><td>wfu-action-open </td></tr><tr><td>Dropdown</td><td>Closed</td><td></td><td>wfu-trigger-closed</td><td>wfu-action-close </td></tr><tr><td>Tab</td><td>Changed</td><td></td><td></td><td></td></tr><tr><td>Form</td><td>Submit Attempt</td><td></td><td>wfu-trigger-submit </td><td></td></tr><tr><td>Form</td><td>Submit Success</td><td></td><td>wfu-trigger-submit-success </td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>ECom</td><td>Cart Opened</td><td></td><td>wfu-trigger-open </td><td>wfu-action-open </td></tr><tr><td>ECom</td><td>Cart Closed</td><td></td><td>wfu-trigger-close </td><td>wfu-action-close </td></tr><tr><td>ECom</td><td>Item Added</td><td></td><td>wfu-trigger-add-item </td><td></td></tr><tr><td>ECom</td><td>Item Removed</td><td></td><td>wfu-trigger-remove-item </td><td></td></tr></tbody></table>











### Dropdown Elements&#x20;



<table><thead><tr><th width="130">Type</th><th width="197">Trigger</th><th>Detail</th><th>Notes</th><th></th></tr></thead><tbody><tr><td>Any</td><td><a href="click-triggers.md">Click</a></td><td></td><td>wfu-trigger-click </td><td>wfu-action-click </td></tr><tr><td>Any</td><td><a href="dynamic-interaction-trigger-links.md">Link click</a></td><td></td><td>Used in <code>##event</code> constructions </td><td></td></tr><tr><td>Any</td><td>Scrolled into view</td><td></td><td>wfu-trigger-scrollintoview</td><td></td></tr><tr><td>Any</td><td>Hover </td><td></td><td>wfu-trigger-hover</td><td></td></tr><tr><td>Any</td><td>Interaction trigger</td><td></td><td>wfu-trigger-ix</td><td></td></tr><tr><td>Video</td><td>Video Played</td><td></td><td>wfu-trigger-play</td><td>wfu-action-play </td></tr><tr><td>Video</td><td>Video Paused</td><td></td><td>wfu-trigger-pause</td><td>wfu-action-pause </td></tr><tr><td>Video</td><td>Video Ended</td><td></td><td>wfu-trigger-finished</td><td></td></tr><tr><td>Video</td><td>Video Progression %</td><td></td><td>wfu-trigger-seek</td><td>wfu-action-seek </td></tr><tr><td>Dropdown</td><td>Opened</td><td></td><td>wfu-trigger-opened</td><td>wfu-action-open </td></tr><tr><td>Dropdown</td><td>Closed</td><td></td><td>wfu-trigger-closed</td><td>wfu-action-close </td></tr><tr><td>Tab</td><td>Changed</td><td></td><td></td><td></td></tr><tr><td>Form</td><td>Submit Attempt</td><td></td><td>wfu-trigger-submit </td><td></td></tr><tr><td>Form</td><td>Submit Success</td><td></td><td>wfu-trigger-submit-success </td><td></td></tr></tbody></table>





### Webflow Element Triggers&#x20;

| Trigger      | Detail |                          |
| ------------ | ------ | ------------------------ |
| Cart Opened  |        | wfu-trigger-open         |
| Cart Closed  |        | wfu-trigger-close        |
| Item Added   |        | wfu-trigger-add-item     |
| Item Removed |        | wfu-trigger-remove-item  |









### Form Triggers&#x20;

| Trigger        | Detail |                     |
| -------------- | ------ | ------------------- |
| Submit Attempt |        | wfu-trigger-submit  |
| Submit Success |        | wfu-submit-success  |



### ECom Triggers&#x20;

| Trigger      | Detail |                          |
| ------------ | ------ | ------------------------ |
| Cart Opened  |        | wfu-trigger-open         |
| Cart Closed  |        | wfu-trigger-close        |
| Item Added   |        | wfu-trigger-add-item     |
| Item Removed |        | wfu-trigger-remove-item  |









## Page-Level Triggers&#x20;

### User Activity&#x20;

| Trigger            | Detail              | Notes                      |
| ------------------ | ------------------- | -------------------------- |
| Page scrolled to % | % amount to trigger | wfu-trigger-scrollpercent  |
| Exit intent        |                     | wfu-trigger-exitintent     |
| Rageclick          |                     | wfu-trigger-rageclick      |
| Inactivity         | Inactivity timer    | wfu-trigger-inactivity     |
| Activity           |                     | wfu-trigger-activity       |



### Breakpoint Triggers&#x20;

| Trigger            | Detail        | Notes                           |
| ------------------ | ------------- | ------------------------------- |
| Breakpoint Left    | Breakpoint(s) | wfu-trigger-breakpoint-left     |
| Breakpoint Entered | Breakpoint(s) | wfu-trigger-breakpoint-entered  |



### System Triggers&#x20;

| Trigger                 | Detail                                              | Notes              |
| ----------------------- | --------------------------------------------------- | ------------------ |
| Timer                   | Timer duration                                      | wfu-trigger-timer  |
| On Load                 |                                                     |                    |
| Reactive Trigger Truthy | Formula evals to true ( and was previously false )  |                    |
| Reactive Trigger Falsy  | Formula evals to false ( and was previously true )  |                    |





### SA5 Modal Triggers&#x20;

Opened&#x20;

Closed&#x20;





{% hint style="info" %}
Triggers from modal invocation should be placed here.&#x20;
{% endhint %}











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





