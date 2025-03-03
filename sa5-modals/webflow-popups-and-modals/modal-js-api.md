# Modal JS API



The JS API is primarily configured through SA5's Modal [Controller](../../overview/sa5-core/controllers.md). &#x20;

This is exposed dorectly through SA5 Core's controllers;&#x20;

```
window.sa5.controllers.modals
```





## Use Cases&#x20;

These are some useful setups

### Gated Modals&#x20;

Use a form modal as a "gate" for content access.

* User must fill in the form to proceed&#x20;
* When the user has passed the gate they see the content&#x20;
* They do not need to re-pass the gate&#x20;

<img src="../../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">

{% hint style="success" %}
You can use cookies, sessionStorage or localStorage to keep the gate "open" for subsequent visits.&#x20;
{% endhint %}











## Display a Modal

`display(modalName: string, force: boolean)` show the item &#x20;

* `modalName` is the name of the modal as defined by the `wfu-modal` attribute. &#x20;
* `force` = `true`, will display the modal even when it is marked as suppressed in cookies.&#x20;

Example; &#x20;

```javascript
sa5.controllers.modals.display("modal1", true);  
```



## Close all Modals&#x20;

`closeAll()`&#x20;

Example; &#x20;

```javascript
sa5.controllers.modals.closeAll();   
```



















Close on submit&#x20;

wfu-modal-trigger-close-formsubmit=""&#x20;









## Future



Link IFRAME to Modal automatic

Pre-defined modal default

v. Modal template&#x20;



* Pre-defined modals
* Modals
* Modal Templates&#x20;



|                   | Content Source                                                |   |
| ----------------- | ------------------------------------------------------------- | - |
| pre-defined modal | <ul><li>Element-sourced</li><li>URL IFRAME-sourced </li></ul> |   |
| modal             | Explicit                                                      |   |
| modal template    |                                                               |   |















