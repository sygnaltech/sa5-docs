# Gated Events 🧪

Some Events might have pre-requisites before they can fire.&#x20;

* User is logged in to MemberStack&#x20;
* User is in a specific User Group&#x20;
* User has accepted a Gating modal or something similar&#x20;

## Use Cases&#x20;

* Over 21 gating before a site can be accessed &#x20;
* Birthdate gating before a site can be accessed&#x20;
* Collect user data before a modal is shown&#x20;

## Technical Notes&#x20;

### Custom gates

Custom gates perform a special test every time&#x20;

### State gates&#x20;

Require a specific action be perfomed or test be passed once. Once the gate is opened, the open state is stored generally in localStorage.&#x20;

Once opened, it does not need to be re-opened&#x20;

Opening a gate can be done by an EventGateHandler in a number of ways;&#x20;

* Check to see if the user is&#x20;



When the gate is open, the event fires normally.&#x20;

When the gate is closed;&#x20;

* A modal is presented
  * The user satisfies the gating requirements, e.g. submit a form, click a button&#x20;
* The URL is followed, including target&#x20;
* The gate is opened&#x20;

## Gate State Management&#x20;

### Check Gate&#x20;

Determine if the gate is opened;&#x20;

* Default is to check localStorage&#x20;
* But can also be sessionStorage
* Or cookies&#x20;
* Can be any custom thing as well, e.g.&#x20;

### Open Gate

Opens the gate;&#x20;

* localStorage, sessionStorage, or cookies  &#x20;

### Close Gate&#x20;

Closes the gate;&#x20;



## Implementation Notes

Defined as a block&#x20;

```html
<script sa5-event="name">
{
   gate-type: modal
   modal-gate-type: view
   gate-state: localstorage 
}
</script> 
```



* EventGateHandlerBase&#x20;
  * EventGateModalHandler&#x20;
    * EventGateModalViewHandler&#x20;
    * EventGateModalButtonHandler&#x20;
    * EventGateModalFormHandler&#x20;
  * EventGateMemberstackHandler&#x20;
* EventGateStateHandlerBase&#x20;
  * EventGateStateLocalStorageHandler&#x20;
  * EventGateStateSessionStorageHandler&#x20;
  * EventGateStateCookieHandler&#x20;

EventGateLocalStorageHandlerBase&#x20;

EventGateLocalStorageHandlerBase

## Concept&#x20;

wfu-event-gate = function

Must return true&#x20;

Pass in Event, so it can be fired&#x20;





## Gate Types &#x20;

Defined as a block&#x20;

```
<script sa5-event="name">
{
   gate-type: modal
   modal-gate-type: view
   
}
</script> 
```



### Modal Gates&#x20;

1. An event fires&#x20;
2. Modal type gate is gate-checked&#x20;
3. If fails pass;&#x20;
   1. Display modal&#x20;
4. Success pass;&#x20;
   1. Fire event&#x20;

| Modal Gate Type | Test | Success | Fail  |
| --------------- | ---- | ------- | ----- |
| view            |      |         |       |
| button          |      |         |       |
| form            |      |         |       |



### Eval Gate&#x20;

1\.























