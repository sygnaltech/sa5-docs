---
description: Stuff we're considering.
---

# Developing Concepts | Collection List Data Sources

Off-page binding

De-pagination&#x20;

Loading and caching dynamically &#x20;

### How are Data Sources built? <a href="#how-are-data-sources-built" id="how-are-data-sources-built"></a>

Data Sources can be created from three primary sources;

1. A Webflow Collection List
2. A remote JSON source, such as a public API endpoint
3. A remote CSV source, such as a Google Sheet

Data Sources enable Sygnal Attributes data-binding capabilities, but you can use them for other purposes as well.



## Alternate formats

wfu-data-format `json` | `default`

wfu-data-format special `::`&#x20;

{% code overflow="wrap" %}
```html
<script type="wfu-data-item" wfu-data-version="1" wfu-data-dsn="..." wfu-data-item-id="...">
name::...
slug::...
myfield::... 
::name: 
</script>
```
{% endcode %}

Then htmldecode values

Can fix multilines?

If not, prefix

`::`







Lists

You can then use that source in several ways;

* Data-bind to a form SELECT or INPUT control.
* Display an HTML table in redesign
* Display a list
* Display the count of items in redesign



