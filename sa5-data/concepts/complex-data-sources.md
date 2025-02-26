# Complex Data Sources





Simple Binding does not require any special terminology as the data-binding target element is easy to identify, and the data source is easy to specify.&#x20;



The most popular simple-binding use cases are e.g. the binding of a querystring parameter to a form input element.&#x20;

{% hint style="success" %}
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
* Static JSON file&#x20;
* JSON-LD&#x20;
* EXIF data&#x20;
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

##





