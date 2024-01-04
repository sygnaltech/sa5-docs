---
description: Get details of the current URL
---

# URL Part Data Source

## Use Cases

* Grab the current path of the page, and push it into a hidden field in your contact form so that you can track which page ( or collection page ) the form was submitted from.&#x20;

## Options & Examples

{% hint style="info" %}
Examples here use the following URL for reference;\
`https://example.com:8080/path/to/resource?query=value#section2`
{% endhint %}

<table><thead><tr><th width="192.33333333333331">Data Path</th><th width="310">Description</th><th>Example</th></tr></thead><tbody><tr><td><code>$url.href</code></td><td>The entire URL</td><td><code>https://example.com:8080/path/to/resource?query=value#section2</code></td></tr><tr><td><code>$url.origin</code></td><td>The origin of the URL, combining the protocol, domain, and port</td><td><code>https://example.com:8080</code></td></tr><tr><td><code>$url.pathname</code></td><td>The path section of the URL, which comes after the domain and before the query string</td><td><code>/path/to/resource</code></td></tr><tr><td><code>$url.search</code></td><td><p>The entire query portion of the URL, including the leading question mark.</p><p><em>See</em> <a href="url-query-params.md"><em>Query Params</em></a> <em>to get individual params.</em></p></td><td><code>?query=value</code></td></tr><tr><td><code>$url.protocol</code></td><td>The protocol of the URL</td><td><code>https:</code></td></tr><tr><td><code>$url.host</code></td><td>Combines the hostname and the port ( if a port is specified )</td><td><code>example.com:8080</code></td></tr><tr><td><code>$url.hostname</code></td><td>The domain name or IP address part of the URL</td><td><code>example.com</code></td></tr><tr><td><code>$url.port</code></td><td>The port number of the URL, if specified</td><td><code>8080</code></td></tr></tbody></table>

## Technical Notes

{% embed url="https://developer.mozilla.org/en-US/docs/Web/API/URL" %}

