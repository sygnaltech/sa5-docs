# Sort locales in the order you choose



* Match internal map?
*



```javascript
// Some code
// Get the parent element
const parentElement = document.getElementById('id-for-michael');

// Get all divs within the parent element that have the attribute data-wf-locale-display-name
const divs = parentElement.querySelectorAll('div[data-wf-locale-display-name]');

// Create a mapping of display names to their respective divs
const divMap = {};
divs.forEach(div => {
  const displayName = div.getAttribute('data-wf-locale-display-name');
  divMap[displayName] = div;
});

// Define the desired order
const order = ['Chinese', 'Spanish', 'English'];

// Create a new array in the desired order
const sortedDivs = order.map(displayName => divMap[displayName]);

// Remove existing divs from the DOM
divs.forEach(div => div.remove());

// Append divs in the new order to the parent element
sortedDivs.forEach(div => parentElement.appendChild(div));
```



{% hint style="info" %}
**CREDIT** - Ida from Webflow support, for the approach idea.
{% endhint %}

