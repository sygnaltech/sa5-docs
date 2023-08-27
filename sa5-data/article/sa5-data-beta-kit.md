---
description: Add CMS Data to your Custom Code
---

# SA5 Data BETA Kit

## BETA Announcement

12-Aug-2023 announcement - [https://sygnal-attr.discourse.group/t/video-want-to-access-your-collection-data-in-script-join-the-sa5-data-beta/103](https://sygnal-attr.discourse.group/t/video-want-to-access-your-collection-data-in-script-join-the-sa5-data-beta/103)

{% embed url="https://www.loom.com/share/0a3b234b14414b778ae790c8125e77e6" %}

## Useful Materials

{% embed url="https://cms-data.webflow.io/" %}
Demo
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/cms-data" %}
Cloneable
{% endembed %}

```javascript
// Demo code
window.sa5 = window.sa5 || [];
window.sa5.push(['datastoreLoaded', 
  (ds) => {
    
    console.log("DATASTORE LOADED", ds.store['listings'].data); 
    
    // Initialize total
    let total = 0;
    let items = ds.store['listings'].data;

    // Iterate through the map and sum the price field
    items.forEach(item => {
        total += parseFloat(item.price);
    });

    console.log(total);    

    const element = document.getElementById('portfolio-value');
    if (element) {
        const formatter = new Intl.NumberFormat('en-US', {
            style: 'currency',
            currency: 'USD',
            minimumFractionDigits: 0,
            maximumFractionDigits: 0          
        });
        element.innerText = formatter.format(total);
    }
    
  }]); 
```

{% embed url="https://codepen.io/memetican/pen/dyQBRQx/0723b00d18f020882d74a0013cc4d34f" %}
Custom code utilizing data
{% endembed %}



