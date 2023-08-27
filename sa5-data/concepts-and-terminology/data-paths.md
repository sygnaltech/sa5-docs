---
description: How to Identify the Exact Data you want to bind
---

# Data Paths

A **data path** is a string which identifies the specific data you want. Data paths are central to data-binding, to identify the data we want bound.&#x20;

You can think of it like a file, or a URL.&#x20;

In it most extensive form, it can have 4 or more segments;&#x20;

`$`**Data Source Type**`.`**Data Source Name**`.`**Object ID**`..`**Field Name**

At a minimum, a data path typically includes a **Data Source Type** and a **Field Name**.&#x20;

e.g.; `$cookie.my-cookie`

In more complex Data Sources, additional segments are needed, for example;&#x20;

`$db.my-db.my-object.my-field`

In this example;

* `$db` indicates that the Data Source Type is a database. SA5 will resolve this by doing a lookup in the Datastore.
* `my-db` is the Data Source Name, which will be registered in the Datastore. For a CMS data source this would typically be the CMS collection slug, or similar.
* `my-record` is a unique object ID, for Keyed Data Sources. You can think of this as a database record. For a CMS data source this would typically be the CMS item slug. &#x20;
* `my-field` is the field on that object that we want, e.g. a CMS item field.

{% hint style="info" %}
Currently, Data Paths always identify a single point value, which can be bound to a single-value item such as a text element, an input field, a `{{ macro }}` expansion, etc. However in the future, it may also be used to retrieve full objects or even object-sets for list-binding and table-binding operations. &#x20;
{% endhint %}

Examples;

<table><thead><tr><th width="196.33333333333331"></th><th width="170">Data Source Type</th><th></th></tr></thead><tbody><tr><td>$user.name</td><td>User object</td><td>Name value</td></tr><tr><td>$user.data.custom-url</td><td>User object</td><td><p></p><p>Custom user </p></td></tr><tr><td>@name</td><td>User object</td><td></td></tr><tr><td>$cookie.foo</td><td>Cookie</td><td>The cookie named <code>foo</code></td></tr><tr><td>$local.bar</td><td>Local storage</td><td></td></tr><tr><td>$session.bat</td><td>Session storage</td><td></td></tr><tr><td>$query.foo</td><td>Query string </td><td></td></tr><tr><td>$db.my-db.my-record.my-field</td><td>Database</td><td></td></tr></tbody></table>





