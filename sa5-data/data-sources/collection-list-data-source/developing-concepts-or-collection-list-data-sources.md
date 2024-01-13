---
description: Stuff we're considering.
---

# Developing Concepts | Collection List Data Sources

## Stuff We're Considering...

* Cross-page sourcing. The ability to designate a "data source page" which contains all of the collection lists data you want, and to have that data loaded for access from any other part of your site.&#x20;
* De-pagination. Automatically absorbing the full content of a Collection List through its pages.&#x20;
* Caching. Both of the above features would benefit from caching so that the datastore does not need to be rebuilt on each page access. Here, we may be able to use the page's published date as an indicator.&#x20;
* Lazy & asynchronous loading.&#x20;
* Load-time permutations. As data is loaded, a webhook to allow for smart modifications of the data before it is stored.&#x20;
  * Lookups and field additions
  * Translation tables
  * Currency conversions
  * Calculations
  * Running balance totals
  * etc.&#x20;

### How are Data Sources built? <a href="#how-are-data-sources-built" id="how-are-data-sources-built"></a>

Data Sources can be created from three primary sources;

1. A Webflow Collection List
2. A remote JSON source, such as a public API endpoint
3. A remote CSV source, such as a Google Sheet

Data Sources enable Sygnal Attributes data-binding capabilities, but you can use them for other purposes as well.

##



## Alternate formats

{% hint style="success" %}
We've recently added [SA5 Data](../../article/) as our standard data source.&#x20;
{% endhint %}





You can then use that source in several ways;

* Data-bind to a form SELECT or INPUT control.
* Display an HTML table in redesign
* Display a list
* Display the count of items in redesign

## Notes

```html
<div class="user" data-user-id="123" data-user-name="Alice"></div>
<div class="user" data-user-id="456" data-user-name="Bob"></div>
```

{% code overflow="wrap" %}
```javascript
// Select all elements with a certain class or query
const userElements = document.querySelectorAll('.user');

// Map over these elements to transform them into an array of objects
const users = Array.from(userElements).map(el => {
    return {
        userId: el.dataset.userId,
        userName: el.dataset.userName
    };
});

console.log(users); // Outputs: [{ userId: "123", userName: "Alice" }, { userId: "456", userName: "Bob" }]

```
{% endcode %}
