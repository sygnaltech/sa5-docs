---
description: Creatively merge data into your Webflow sites
---

# Usage Notes

SA5's Data features have two facets-&#x20;

* **Data Sources** refer to the ability to assemble, store, and retrieve data from Collection Lists, remote sources, the querystring, webStorage, cookies, and more. The data is collected and organized into a Datastore.&#x20;
* **Data-Bound Elements** uses these sources to pull data into your page, text element, rich text templates, form fields, and more. It lets you easily display data from these sources using simple markup.&#x20;

## Use Cases

The features here are meant to be very flexible, but here are a few common use cases we see often;&#x20;

* Populate form fields from querystring params ( see [demo](https://data-binding.webflow.io/query?code=ID6079\&name=Trial+User+1\&color=blue\&accept=true) )
* Populate form fields to include the current URL or path ( see [demo](https://data-binding.webflow.io/url) )
* Populate form fields from webStorage or cookies, as part of a referral tracking system ( see [demo](https://data-binding.webflow.io/webstorage) )
* Populate form fields with current user data, such as the user's email & name
* Perform "mad libs" style text replacements in rich text content, mixed from Collection List fields and other sources ( see [demo](https://data-binding.webflow.io/cms) )&#x20;

{% hint style="info" %}
In combination, these can be used to move data easily through your site, and to pass information back to your server in hidden fields as users submit forms.&#x20;
{% endhint %}

## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library  <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply `wfu-bind` to Desired Elements <a href="#step-2---apply-wfu-query-param-to-desired-elements" id="step-2---apply-wfu-query-param-to-desired-elements"></a>

Where you place the element and the value you use depend entirely on the element you want to bind and the data source.&#x20;

{% hint style="success" %}
For example, if you want the `name` querystring value to automatically intialize a form input, you would add the `wfu-bind=?name` attribute to your form input element.
{% endhint %}

## Usage Notes&#x20;

See [Data Sources](data-sources/) to learn about the many possible data sources.&#x20;

See [Data Binding](binding-data/) to learn about;

* The data binding syntax and how to connect a data source to an element&#x20;
* The effect the attribute has on different element types. &#x20;



\
