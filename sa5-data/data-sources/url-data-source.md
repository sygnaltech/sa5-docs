---
description: Get details of the current URL
---

# Url Data Source



<table><thead><tr><th width="175.33333333333331">Data Path</th><th width="321">Description</th><th>Example</th></tr></thead><tbody><tr><td>$url.href</td><td>The entire URL</td><td>https://example.com:8080/path/to/resource?query=value#section2</td></tr><tr><td>$url.origin</td><td>The origin of the URL, combining the protocol, domain, and port</td><td>https://example.com:8080</td></tr><tr><td>$url.pathname</td><td>The path section of the URL, which comes after the domain and before the query string</td><td>/path/to/resource</td></tr><tr><td>$url.search</td><td>The query portion of the URL, including the leading question mark</td><td>?query=value</td></tr><tr><td>$url.protocol</td><td>The protocol of the URL, including the :</td><td>https:</td></tr><tr><td>$url.host</td><td>Combines the hostname and the port ( if a port is specified )</td><td>example.com:8080</td></tr><tr><td>$url.hostname</td><td>The domain name or IP address part of the URL</td><td>example.com</td></tr><tr><td>$url.port</td><td>The port number of the URL, if specified</td><td>8080</td></tr></tbody></table>

## Use Cases

* Store the current URL, or current path in a form to identify the specific page it was submitted from.&#x20;

## Technical Notes

{% embed url="https://developer.mozilla.org/en-US/docs/Web/API/URL" %}

