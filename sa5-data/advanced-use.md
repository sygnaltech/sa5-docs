---
description: Some Tips for more advanced use
---

# Advanced Use



## Grouping & Group Counts

## Example

Scenario;

> You have a CMS collection of Locations, which each have a State. You want to show a list of States, with the count of Locations in each.&#x20;

Let's suppose you have setup this SA5 Data source.

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

Once loaded, the data it will exist as a JavaScript Map in SA5's Datastore;

```javascript
ds.store.locations.data
```

You can transform that Map into a new map which contains Groups and counts, like this;

```javascript
// Get count of locations in each state
let result = new Map();
ds.store.locations.data.forEach(({ state }) => {
    result.set(state, (result.get(state) || 0) + 1); // increment state count
});
```

Now you can use your result Map however you like.&#x20;



