---
description: Developing Concepts in SEO Tools
---

# Developing Concepts

{% hint style="danger" %}
**EXPERIMENTAL ALPHA** ⑤

DO NOT USE this in production code, as it may be removed. We'll see if this approach works. Testing with Google is in progress.&#x20;
{% endhint %}

## SA5 JSON <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Goals;

* Eliminate HTML encoding issues introduced by Webflow's HTML-centric field embeds
* Support full object and sub-object creation, to maximize JSON-LD support&#x20;
* No more commas

Problems;

* CRLF in multiline?

### Syntax Rules & Examples

Similarities to YAML or Python.&#x20;

* Each key-value pair is represented in the format `key: value`.
* Nested objects start on a new line with their keys, and their contents are indented for clarity.



foo: \\\\\multiline\\\\\\

{% hint style="warning" %}
The one potential problem here is text fields which are multiline, and which contain line-breaks. In Webflow's output this may cause a line break and disrupt the structure of the object.&#x20;
{% endhint %}

```html
<script type="sa5/json">
@context: http://schema.org
@type: Person
name: John Doe
jobTitle: Software Engineer
address:
    @type: PostalAddress
    streetAddress: 123 Main St
    addressLocality: Springfield
    addressRegion: IL
    postalCode: 12345
    addressCountry: US
</script>
```

Resolves to;

```json
{
  "@context": "http://schema.org",
  "@type": "Person",
  "name": "John Doe",
  "jobTitle": "Software Engineer",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "Springfield",
    "addressRegion": "IL",
    "postalCode": "12345",
    "addressCountry": "US"
  }
}
```
