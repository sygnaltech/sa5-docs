---
description: Concepts & Terms You Need to Know in SA5
---

# Concepts & Terminology

{% hint style="info" %}
There are a lot of new things happening here, so terminology is stabilizing as we vector words a specific paradigm.&#x20;
{% endhint %}

## Datastore

The central SA5 object used for storing and retrieving data. Each piece of data loaded is catalogued within this object.&#x20;

_In general, all interactions with this object are automatically handled by the data-source and data-binding scripts. However you may interact with it if you are using custom code._&#x20;

## Database ( or Data Table, or Data Object-Set )

Is a named collection of data stored in the database.&#x20;

Currently, it typically contains an array of records, such as the contents built from a Webflow Collection List.

{% hint style="info" %}
In the future, this will likely support custom object datastores, such as the cached results of an API query. &#x20;
{% endhint %}

### Data Row ( or Data Object )&#x20;

### Data Item&#x20;

An individual item.&#x20;

## Data Source

A **data source** is a more general name for a source of data.

### Static v. Dynamic Data Sources&#x20;

Sometimes that source is dynamic, and referenced on request. Other times it is pre-loaded, and then retrieved from that cache. Databases are a good example of a static source.&#x20;

* A Webflow Collection List
* A remote JSON source, such as a public API endpoint
* A remote CSV source, such as a Google Sheet

### Data Source Type

*

Data sources are typed, for example;&#x20;

* Collection list
* 3rd party public API
* Static CSV file&#x20;
* Static JSON file
* A remote JSON source, such as a public API endpoint
* A remote CSV source, such as a Google Sheet
* User data
* Local storage data
* Cookies
* Session storage data
* Query string data
* A remote database using a connection string&#x20;

### Data Source Name ( DSN )

Some Data Sources require a name to reference them, since you can have several of them.

In some places you'll see the abbreviation DSN used in attributes and docs. This refers to the unique name of a data source, which is used to locate the database within the datastore.&#x20;

## Data Source Descriptor ( DSD )

A single string which identifies the specific data you want. DSD's are typically used in data-binding, to identify the data we want bound.&#x20;

At a minimum, a DSD typically includes a **Data Source Type** and a **Data Source Name**.&#x20;

For example;&#x20;

`$cookie.my-cookie`

In more complex Data Sources, additional specifiers are needed, for example;&#x20;

`$db.my-db.my-record.my-field`

* `$db` indicates that the Data Source Type is a database. SA5 will resolve this by doing a lookup in the Datastore.
* `my-db` is the Data Source Name, which will be registered in the Datastore. For a CMS data source this would typically be the CMS collection slug, or similar.
* `my-record` is a unique record ID, for Keyed Data Sources. For a CMS data source this would typically be the CMS item slug. &#x20;

{% hint style="info" %}
Informally, the portion of the DSD following the Type & DSN is referred to as the Data Item Name.&#x20;
{% endhint %}

{% hint style="info" %}
Currently, DSD's always identify a single point value, which can be bound to a text item, input field, `{{ macro }}` expansion, etc. However in the future, it may also be used to retrieve objects or object-sets.&#x20;
{% endhint %}

Examples;

<table><thead><tr><th width="196.33333333333331"></th><th width="170">Data Source Type</th><th></th></tr></thead><tbody><tr><td>$user.name</td><td>User object</td><td>Name value</td></tr><tr><td>$user.data.custom-url</td><td>User object</td><td><p></p><p>Custom user </p></td></tr><tr><td>@name</td><td>User object</td><td></td></tr><tr><td>$cookie.foo</td><td>Cookie</td><td>The cookie named <code>foo</code></td></tr><tr><td>$local.bar</td><td>Local storage</td><td></td></tr><tr><td>$session.bat</td><td>Session storage</td><td></td></tr><tr><td>$query.foo</td><td>Query string </td><td></td></tr><tr><td>$db.my-db.my-record.my-field</td><td>Database</td><td></td></tr></tbody></table>

