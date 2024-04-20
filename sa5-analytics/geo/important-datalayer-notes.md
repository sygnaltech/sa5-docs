# Important dataLayer Notes



## How SA5 supports this

In our `sa5/gtm-data` construction, you should set all of the properties in the object.

`null` values will be converted to `undefined`&#x20;

e.g.

```
<script type="sa5/gtm-data">
{
  "event": "banner_interaction",
  "event_category": "System",
  "event_label": "Offer",
  "banner_name": "sticky",
  "interaction_type": "click",
  "position": "sticky-top",
  "variant": null
}
</script>
```

### Future

Set a default base object, and override it. We merge them

```
<script type="sa5/gtm-data-proto" event="banner_interaction">
{
  "event": "banner_interaction",
  "event_category": "System",
  "event_label": "Offer",
  "banner_name": null,
  "interaction_type": null,
  "position": null,
  "variant": null
}
</script>
```



```
const prototypeElement = document.querySelector('script[type="sa5/gtm-data-prototype"]');
const prototypeData = JSON.parse(prototypeElement.textContent || '{}');

// Convert nulls to undefined
Object.keys(prototypeData).forEach(key => {
  if (prototypeData[key] === null) {
    prototypeData[key] = undefined;
  }
});

// Assume actualData is obtained similarly from an 'sa5/gtm-data' script
// Merge actualData into prototypeData
const mergedData = { ...prototypeData, ...actualData };

// Use mergedData as needed

```



## How GTM's dataLayer Works

When you push an object to the dataLayer, GTM doesn't reset or clear previous state between pushes. Instead, properties persist in the dataLayer's state until explicitly overridden or removed. This behavior ensures that data remains available across different events for tags, triggers, and variables to utilize without needing to repush the same information continually.

#### The Situation with Alpha, Beta, and Gamma

When you push an object containing `alpha`, `beta`, and `gamma` properties to the dataLayer and then subsequently push another object with just `alpha` and `beta`, the `gamma` property remains in the dataLayer's current state. This is why you're seeing `gamma` being preserved and appearing as part of the second event, even though you didn't include it in the second push.

#### How to Prevent Unwanted Properties from Persisting

To prevent properties like `gamma` from persisting beyond their intended event, you have a couple of approaches:

1. **Explicitly Set Unwanted Properties to `undefined` or `null`**: By explicitly setting properties you want to "remove" to `undefined` or `null` in subsequent pushes, you can ensure they don't carry over undesirably.











