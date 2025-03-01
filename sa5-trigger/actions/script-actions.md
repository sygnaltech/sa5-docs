---
description: Invoke a script as an SA5 Action.
---

# Script Actions 🧪



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
    { "action": "class-remove", "data": "class1" }     
  ]
}
</script>
```



This Action requires an SA5 config block

```html
<script type="application/sa+json" handler="action.script" event="alert1">
function test1() {
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
