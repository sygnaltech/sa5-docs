# Gated Events 🧪





Some Events might have pre-requisites before they can fire.&#x20;

* User is logged in to MemberStack&#x20;
* User is in a specific User Group&#x20;
*

## Use Cases

### Form-Gate Navigation



### Form-Gate a Modal&#x20;

* Check localStorage
* If gate not passed
  * Display a form modal
  * On successful submit, set the localStorage cookie
  * On fail, exit
* Perform original event&#x20;
  * Display Modal&#x20;



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























