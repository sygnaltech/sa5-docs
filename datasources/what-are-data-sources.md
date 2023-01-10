# What are Data Sources?

SA makes your data programmatically accessible by preparing JSON **data sources** and a **database** for your scripts to use.

These concepts are very simple;

* A **data source** is a JSON document, typically in the form of a table, list, or dictionary.
* A **database** is a JavaScript `map`, which provides a key-value store for the data sources to reside in.

### How are Data Sources built? <a href="#how-are-data-sources-built" id="how-are-data-sources-built"></a>

In SA 3, Data Sources can be created from three primary sources;

1. A Webflow Collection List
2. A remote JSON source, such as an API endpoint
3. A remote CSV source, such as an Google Sheet

Data Sources underly SA’s data-binding capabilities, but you can use them for other purposes as well.

\
