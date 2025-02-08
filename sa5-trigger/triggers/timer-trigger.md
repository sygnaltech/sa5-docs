# Timer Trigger

Defines a timer as a trigger.&#x20;







```html
<script type="application/sa+json" handler="Trigger.Timer">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  "timer": "60", 
  "timerRepeat": "120",
  "event": "my-event" 
}
</script>
```





## Usage Notes

### `event`  = ( event name )

**Required.**&#x20;

The event to trigger.&#x20;

### `timer` = ( sec )

**Required.** &#x20;

Indicates the number of seconds before the timer will fire.&#x20;

### `timerRepeat` = ( sec )&#x20;

**Optional.** &#x20;

If specified, the timer will repeat after the first firing every timerRepeat



| timer | timerRepeat   |                                                                                              |
| ----- | ------------- | -------------------------------------------------------------------------------------------- |
| 60    | Not specified | Timer fires once, 60 seconds after page load.                                                |
| 0     | 120           | Timer fires immediately after page load, and then fires again every 120 seconds afterwards.  |
|       |               |                                                                                              |











