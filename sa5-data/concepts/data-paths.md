---
description: How to Identify the Exact Data you want to bind
---

# Data Paths

A Data Path is a string which identifies the specific data you want. Data paths are central to data-binding, to identify the data we want bound.&#x20;

You can think of it like a physical mailing address, or a URL.&#x20;

## Examples&#x20;

### Simple Data Paths&#x20;

A simple data path typically consists of a Data Source Type and a Data Source Name.&#x20;

e.g.;  &#x20;

<table><thead><tr><th width="196.33333333333331">Data Path </th><th width="170">Data Source Type</th><th>Value Source </th></tr></thead><tbody><tr><td><code>$query.foo</code> </td><td>Query string </td><td>The value of the query string param named <code>foo</code> </td></tr><tr><td><code>$cookie.foo</code> </td><td>Cookie</td><td>The value of the cookie named <code>foo</code></td></tr><tr><td><code>$local.bar</code> </td><td>Local storage</td><td>The value of the localStorage string with key <code>bar</code> </td></tr><tr><td><code>$session.bat</code> </td><td>Session storage</td><td>The value of the sessionStorage string with key <code>bat</code> </td></tr></tbody></table>

### Complex Data Paths&#x20;

Complex Data Paths involve referencing arrays ( typically collection lists ) or values within an object. &#x20;

e.g.; &#x20;

<table><thead><tr><th width="196.33333333333331">Data Path </th><th width="170">Data Source Type</th><th>Value Source </th></tr></thead><tbody><tr><td><code>$user.name</code> </td><td>User object</td><td>The User's name</td></tr><tr><td><code>$user.data.custom-url</code> </td><td>User object</td><td>The User's custom attribute named <code>custom-url</code> </td></tr><tr><td><code>$db.my-db.my-record.my-field</code> </td><td>Database</td><td>Describes a more complex referencing within an SA5 Data "Database". </td></tr></tbody></table>

### Database Data Paths&#x20;

{% hint style="info" %}
SA5's Database concept is being revisited based on use case feedback.
{% endhint %}

SA5 typically structures and references values using a named object array.&#x20;

e.g.&#x20;

```
$db.db-name.object-id...field-name 
```

Here we have;

* `$db` indicates the Data Source Type&#x20;
  * `db-name` is the Data Source Name, indicating which database, by name&#x20;
    * `object-id` is the specific named object, within the array.  In an SA5 Database constructed from a Collection List, this is typically the slug of the item.&#x20;
      * _( optional path )_ within a complex object, you may need a path to navigate to the item&#x20;
        * `field-name` the name of the item you wish to bind to&#x20;



{% hint style="info" %}
Currently, Data Paths always identify a single point value, which can be bound to a single-value item such as a text element, an input field, a `{{ macro }}` expansion, etc. However in the future, it may also be used to retrieve full objects or even object-sets for list-binding and table-binding operations. &#x20;
{% endhint %}







