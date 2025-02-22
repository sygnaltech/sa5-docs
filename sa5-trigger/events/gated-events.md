# Gated Events





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

























