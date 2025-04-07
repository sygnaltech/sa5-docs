---
description: A simple alert message, primarily for testing
---

# Alert Action





## Usage Notes&#x20;

This Action requires an SA5 config block



```html
<script type="application/sa+json" handler="action.alert" event="alert1">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1",
  "message": "test" 
}
</script>
```



### `message` = ( _plain-text_ )&#x20;

Plain-text message to display in the alert. &#x20;

If you want a multi-line message, you can use the `\n` linefeed sequence in your string.&#x20;

## Future&#x20;



