---
description: Defines a timer as a trigger.
---

# Timer Trigger

Create a timer as a trigger.  You can specify both the time to the first trigger event, and an optional recurring trigger event as well.&#x20;

```html
<script type="application/sa+json" handler="trigger.timer" event="timer1">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  "timer": "60", 
  "timerRepeat": "120",
}
</script>
```





## Usage Notes

### Script Configuration

These are the settings of the script element.&#x20;

### type  = application/sa+json

**Required.**  Identifies the script block as an SA5 configuration block, formatted as JSON.&#x20;

### handler = trigger.timer

**Required.**  Identifies that this is a timer trigger.&#x20;

### event  = ( _event name_ )

**Required.**  The event to trigger.&#x20;

### JSON Configuration&#x20;

### timer = ( _seconds_ )

**Required.**  Indicates the number of seconds before the timer will fire.&#x20;

### timerRepeat = ( _seconds_ )&#x20;

**Optional.**  If specified, the timer will repeat after the first firing every timerRepeat



| timer | timerRepeat   |                                                                                              |
| ----- | ------------- | -------------------------------------------------------------------------------------------- |
| 60    | Not specified | Timer fires once, 60 seconds after page load.                                                |
| 0     | 120           | Timer fires immediately after page load, and then fires again every 120 seconds afterwards.  |
|       |               |                                                                                              |











