---
description: Trigger on URL hash
---

# Url Hash Trigger 🧪

## Goals

Fires when page has loaded and it has the specified #hash&#x20;

Fires when change&#x20;

## Use Cases

* Hash specified on URL;
  * Select specific tab
  * Scroll to section and select specific tab&#x20;
  * Display modal &#x20;
* Hash changed after load, e.g. menu hash nav&#x20;











## Configuration &#x20;

This Trigger uses an SA5 configuration block.&#x20;

```html
<script type="application/sa+json" handler="trigger.hash" event="timer1">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  "hash": "myhash", 
  "triggerOnLoad": "yes", 
  "triggerOnChange": "yes",
  "triggerTimes": "1" 
}
</script> 
```



### hash = ( hash to trigger on )





### triggerOnLoad = ( truthy )





### triggerOnChange ( truthy )





### triggerTimes = ( trigger # of times )&#x20;

**Optional.**  Default = 1.&#x20;

On a page load, indicates the number of times this trigger can fire.  &#x20;





## Future

trigger on hash patterns?&#x20;





