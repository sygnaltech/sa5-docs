---
description: Invoke a script as an SA5 Action.
---

# Script Actions 🧪

IMPORTANT: Differentiate;

* "Sequence" action specifications from
* JS actions that run a function&#x20;

Goals;





Use cases;&#x20;

* Start a video after an interaction has completed
* Display a pop-up in the middle of an interaction sequence&#x20;

Technical notes



### sa-action-script = ( ... ) &#x20;



This Action requires an SA5 config block

```html
<script type="application/sa+json" handler="action.script" event="alert1">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  "script": [
    { "action": "class-add", "data": "class1" }, 
    { "action": "class-remove", "data": "class1" },
    { "action": "scroll-into-view", "behavior": "instant", "block": "start" }      
  ]
}
</script>
```



This Action requires an SA5 config block

```html
<script type="application/sa+json" handler="action.script" event="alert1">
function test1() { 
  sa.events.invoke("test1"); 
}
</script> 
```

This Action requires an SA5 config block; &#x20;



```html
<script type="application/sa+json" handler="action.script" event="alert1">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  "function": "myFunc1"  
}
</script>
```



This Action requires an SA5 config block

```html
<script type="application/sa+json" handler="action.script" event="alert1">
loadCssOnce("https://calendly.com/assets/external/widget.css"); 
loadJsOnce("https://calendly.com/assets/external/widget.js", module?); 

new CSSLoader({
  url: "https://calendly.com/assets/external/widget.css"
}).load();
new CSSLoader({
  url: "https://calendly.com/assets/external/widget.js"
}).load();

Calendly.initPopupWidget({ url: 'https://calendly.com/YOUR_SCHEDULING_LINK' }); 

</script> 
```

This Action requires an SA5 config block; &#x20;







## Actions

Triggers;

* User action
  * Click
  * Scroll
  * Hover
* Variable change ( reactive );&#x20;
  * e.g. x > 1000
* Timer
* Interaction step&#x20;
* Form submit &#x20;
* Alpine.js triggers  &#x20;

Actions;&#x20;

* Click ( other elements )
  * Interaction&#x20;
* Scroll ( other elements )
* Code execution
* Class add/remove&#x20;
* Form submit



Mechanic;&#x20;

* Define triggers
  * e.g. attribute wfu-click = ( name ) &#x20;
*

















[https://codepen.io/memetican/pen/pvzXrKQ/30243a91b6fb117a92b0e5b3b5b69503?editors=1111](https://codepen.io/memetican/pen/pvzXrKQ/30243a91b6fb117a92b0e5b3b5b69503?editors=1111)
