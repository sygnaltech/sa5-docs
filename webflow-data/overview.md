---
description: All about SA5's Data Source & Data-Binding capabilities
---

# Data Sources & Data-Binding ❺

**SA5's Data Source & Data Binding features allow you to creatively integrate data into your Webflow sites.**&#x20;

SA5's Data features have two facets-&#x20;

* **Data Sources** refer to the ability to assemble, store, and retrieve data from Collection Lists, remote sources, the querystring, webStorage, cookies, and more. The data is collected and organized into a Datastore.&#x20;
* **Data Binding** uses these sources to pull data into your page, text element, rich text templates, form fields, and more. It lets you easily display data from these sources using simple markup.&#x20;

{% hint style="success" %}
The **Data Source** & **Data Binding** portions of Sygnal Attributes comprise probably the largest and most complex part of our libraries. They're used by themselves, but are also relied on by our other libraries. We'll be migrating and adding new capabilities as we go.  &#x20;
{% endhint %}

## Use Cases

The features here are meant to be very flexible, but here are a few common use cases we see often;&#x20;

* Populate form fields from querystring params ( see [demo](https://data-binding.webflow.io/query?code=ID6079\&name=Trial+User+1\&color=blue\&accept=true) )
* Populate form fields from webStorage or cookies, as part of a referral tracking system ( see [demo](https://data-binding.webflow.io/webstorage) )
* Populate form fields with current user data, such as the user's email & name
* Perform "mad libs" style text replacements in rich text content, mixed from Collection List fields and other sources ( see [demo](https://data-binding.webflow.io/cms) )&#x20;

In combination, these can be used to move data easily through your site, and to pass information back to your server in hidden fields as users submit forms.&#x20;

### Features Coming Soon

We'll be rebuilding and adding these features soon;&#x20;

* Pulling external data from Google Sheets and Google Docs
* Pulling external data from custom public ( unsecured ) APIs&#x20;
* Support for custom datasource registrations, such as adding your own objects for databinding purposes&#x20;
* Display the count of items in a datasource

## Key Points

SA5 Data Sources & Data-Binding are;&#x20;

* **Inbound-only.** Our data & data-binding features are one-way. They're designed to integrate information into your site from various sources - but not to update external data stores. If you are looking for round-trip capabilities, it's likely you need an application platform like Wized + Xano.&#x20;
* **Versatile.** Mix and match static and dynamic data at will.&#x20;
* **Extensible.** Add your own data sources.&#x20;

Data Sources include;

* Collection-lists, which are prepared to allow&#x20;
* Arbitrary, static data-sets
* Query string params
* LocalStorage items
* SessionStorage items
* Cookies

Data Binding can be applied to;

* Any text element&#x20;
* Rich text elements, to `{{ expand }}` macro content&#x20;
* Form input fields, specifically
  * Text fields, to set the current text input
  * Textarea fields, to set the current text input
  * Checkboxes, to set the checked/unchecked state
  * Select fields, to select the current item&#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Install this code in **before HEAD**, site-wide or on the specific pages you want the script to affect.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Data --> 
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.23/dist/css/webflow-data.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.23/dist/nocode/webflow-data.js"></script> 
```
{% endcode %}

### STEP 2 - Setup any custom data sources you want <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

Currently this primarily refers to Collection List based data sources.&#x20;

{% content-ref url="data-sources/collection-list-data-source.md" %}
[collection-list-data-source.md](data-sources/collection-list-data-source.md)
{% endcontent-ref %}

### STEP 3 - Setup your data-binding attributes <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>

Apply your data-binding attributes to the elements you want, and create the templates you want. The specifics depend on the elemnts you are binding, and the data sources you are using.

See the [Binding Data](binding-data/) section for details.&#x20;

Here are some popular data sources you can bind to-

* Query string params
* Url & url parts
* Collection list data
* User Info&#x20;
* Cookies & Web Storage



\
