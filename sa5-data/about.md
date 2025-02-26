---
description: About the SA5 Data & Data-Binding Library
---

# 🔍 About SA5's Data Lib

**SA5 Data** is a versatile framework that allows you to connect pieces of data to elements in your webpage.&#x20;

It supports simple no-code data-binding like;

* Initialize a form input from a querystring param&#x20;
* Populate an option element from a collection list&#x20;
* Capture the current page URL, path, or UTM params into hidden form fields as part of your form submission &#x20;

## Goals

Make data sources nocode accessible in Webflow page designs including;&#x20;

* CMS data&#x20;
* Querystring data
* URL, path, and hash data&#x20;

Bind these easily to;&#x20;

* Element text content
* Form elements&#x20;
* Form hidden fields for data capture &#x20;

{% hint style="info" %}
**Inbound-only.** Our data & data-binding features are one-way. They're designed to integrate information into your site from various sources - but not to update external data stores. If you are looking for round-trip capabilities, it's likely you need an application platform like Wized + Xano.&#x20;
{% endhint %}

## Concepts&#x20;

SA5's Data features have two facets-&#x20;

* **Data Sources** refer to the ability to assemble, store, and retrieve data from Collection Lists, remote sources, the querystring, webStorage, cookies, and more. The data is collected and organized into a Datastore.&#x20;
* **Data-Bound Elements** uses these sources to pull data into your page, text element, rich text templates, form fields, and more. It lets you easily display data from these sources using simple markup.&#x20;

Data Sources include;

* Collection-lists, which are prepared to allow&#x20;
* Arbitrary, static data-sets
* Query string params
* The current URL & URL parts
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
  * Select fields, to select the current item &#x20;

{% hint style="success" %}
The **Data Source** & **Data Binding** portions of Sygnal Attributes comprise probably the largest and most complex part of this library. They're used by themselves, but are also relied on by our other libraries. We'll be migrating and adding new capabilities as we go.  &#x20;
{% endhint %}

## Capabilities&#x20;

Here are some of the things SA5 Data can do;&#x20;

* Populate form fields from querystring params ( see [demo](https://data-binding.webflow.io/query?code=ID6079\&name=Trial+User+1\&color=blue\&accept=true) )
* Populate form fields to include the current URL or path ( see [demo](https://data-binding.webflow.io/url) )
* Populate form fields from webStorage or cookies, as part of a referral tracking system ( see [demo](https://data-binding.webflow.io/webstorage) )
* Populate form fields with current user data, such as the user's email & name
* Perform "mad libs" style text replacements in rich text content, mixed from Collection List fields and other sources ( see [demo](https://data-binding.webflow.io/cms) )&#x20;

## Use Cases

Some common use cases we see often;&#x20;

* Initialize form fields with data from query string params
* Track what page or collection item a form is submitted from
* Capture referral tracking codes from cookies, or webStorage, when a user signs up for a Membership &#x20;
* Display stored data like the currently logged in user's name or email&#x20;
* Expand template `{{ macros }}` in rich text to create dynamic content.&#x20;
* Extract CMS data and use it to perform special calculations or views, like a running total on a balance sheet&#x20;

In combination, these can be used to move data easily through your site, and to pass information back to your server in hidden fields as users submit forms.&#x20;

