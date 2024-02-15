---
description: Reset your IX2 Interactions after SA5 HTML completes its changes.
---

# Webflow Interactions



Webflow.js automatically initializes interactions on page load, and binds the trigger events to the elements on your page.&#x20;

If that runs before SA5 HTML makes page changes ( sorting, and layout, primarily ), then you may need to re-bind Interactions afterwards.

That is done with this line of code;

```javascript
Webflow.require('ix2').init();
```

In most cases, you will need a slight delay before performing that initialization;

```javascript
<script>
    Webflow.push(function() {
        setTimeout(function() {
            Webflow.require('ix2').init();
        }, 2000); // Delay of 2 seconds (2000 milliseconds)
    });
</script>
```

{% hint style="info" %}
In the future we may build this option directly into SA5.
{% endhint %}
