---
description: Concepts & Terms You Need to Know in SA5
---

# Concepts & Terminology

Here are some useful concepts and terms to understand if you want to access the full range of capabilities in SA5 Data.&#x20;

## Data Sources&#x20;

### Simple v. Complex Data Sources

* A **Simple Data Source** returns a single value.&#x20;
* A **Complex Data Source** returns a structure.&#x20;
  * e.g. a JSON-LD source&#x20;
  * e.g. a Collection List source&#x20;

### Implicit v. Explicit Data Sources&#x20;

* An **Implicit Data Source** is one which is available automatically with no special definition or setup.
  * e.g. query string, URL parts, and cookies are all implicit data sources in SA5&#x20;
* An **Explicit Data Source** requires special setup before it can be accessed&#x20;

## Data Binding&#x20;

### Simple v. Complex Data Binding&#x20;

1. **Simple Data Binding ( 1:1 ).** Refers to simple situations in which a _single data item_ is bound to a _single, simple element_ such as a text element, a checkbox, or a form input element.  These are all characterized by 1:1 bindings.&#x20;
2. **Complex Data Binding ( n:1, 1:n, n:n ).** Refers to complex binding situations that involve _Collection List data sources_, bound to _complex elements_ ( tabs, sliders, select options ) or _elements groups_. &#x20;

## Data Paths &#x20;

[Data Paths](./#data-paths) describe specifically what you are binding to the data bound element.&#x20;

As an example, let's say that we want to do the following;&#x20;

> I want to initialize a form input field with the `name` value from the URL query string.&#x20;

{% hint style="success" %}
Since the [query string](../data-sources/url-query-params.md) is a Simple Data Source in SA5, there is no special setup required.&#x20;
{% endhint %}

To achieve this, we can simply add the following custom attribute on the Form Input element;

```
wfu-bind = $query.name
```

Here `$query.name`is the Data Path. It identifies the data we are binding.&#x20;

There are two parts, which are separated by the period (`.`) delimiter;

* `$query` is the Data Source Type&#x20;
* `name` is the Data Source Name&#x20;

### Abbreviated Data Paths&#x20;

Many commonly-used Data Source Types can be _abbreviated_.  In this example, the Query String Data Source Type can be replaced with a question mark `?`.&#x20;

This allows the attribute to be written even more efficiently as-&#x20;

```
wfu-bind = ?name
```

## Using Data Paths w/ Complex Data Sources&#x20;

SA5 data paths are designed for much more complex uses as well, such as navigating tabular and hierarchical data structures.&#x20;

{% hint style="warning" %}
This will be covered in special courses but you can find some introduction in the [Data Paths](data-paths.md) documentation.&#x20;
{% endhint %}











use a simple, implicit data source such as a&#x20;

