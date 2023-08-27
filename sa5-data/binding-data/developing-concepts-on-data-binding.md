# Developing Concepts on Data-Binding



`{{`` `**`DSD`**` ``|`` `**`default`**` ``}}`&#x20;



Sorting?&#x20;

Arbitrary mix of static and dynamic

List binding

Object binding&#x20;

## Element type support

To test;

* Numbers
* Dates
* Radio buttons&#x20;





### Modes

* All text content
* Attributes e.g. for URL links

### Future

* How to bind in-text links&#x20;
* How to set defaults&#x20;
* Cascading binds, first match preference, e.g. query then localstorage, then cookie... `|`&#x20;
  * Or wfu-bind, then wfu-bind-2, etc.&#x20;
* Bind, then apply custom attributes like x-value -> \{{ \}}&#x20;
* Sk-loaders&#x20;
* Saving values from a form
  * Outward binding &#x20;
* May not work alongside FS Powerful Rich Text due to \{{ \}} constructions&#x20;
* Handlebars logic&#x20;
* Conditional vis&#x20;
* Binding to tables
* Date-formatting and numeric formatting&#x20;





## Compact DSD references&#x20;

\++

.. .

assumed 3 parts



best practices when binding things\
in a collection list => set context on item
-------------------------------------------

can override on sub-items

on a collection-page can st on body if you like

But {}

..

wfu-bind=+id

element, and binding find nearest parent for context

## Ways to Use your Data <a href="#ways-to-use-your-data" id="ways-to-use-your-data"></a>

Besides [data-binding](https://wfu.sygnal.com/docs/datasources/datasource/databinding), you can use this data in other ways.

#### Collection List Item Count <a href="#collection-list-item-count" id="collection-list-item-count"></a>

Want to display the number of items in a collection?

1. Setup that collection as a data source using the instructions above. In this example, we’ll give the data source a `wfu-data` id of `blogposts`. Any unique datasource name will work (see above).
2. Create an element on your page where you want to display the count. In this example, we’ll give it an ID of `myCounter`
3. Paste the following code into your page’s **Before `</body>` tag** section.

{% code overflow="wrap" %}
```html
<script type="module">
import { loadAllDataSources } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/datasources/webflow-collectionlist-data.min.js';
$(function () {

    // Create database
    var db = loadAllDataSources();

    // Count items
    $("#myCounter").text(db.data.get("blogposts").length);
});
</script>
```
{% endcode %}

### &#x20;<a href="#how-it-works" id="how-it-works"></a>

\








