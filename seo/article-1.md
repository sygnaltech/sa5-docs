---
description: Developing Concepts in SEO Tools
---

# SA5 Data

{% hint style="danger" %}
**EXPERIMENTAL ALPHA** ⑤

DO NOT USE this in production code, as it may be removed. We'll see if this approach works. Testing with Google is in progress.&#x20;
{% endhint %}

Sygnal Structured Data is a special \<script> code block format that is designed to easily capture CMS and static data, and encode it in a JavaScript object.&#x20;

This makes it easy to work with in our client side code and create data sources, drive business logic, or to create JSON-LD.&#x20;

## How Does it Work? <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

Here's a very simple example of what SA5 Data looks like.&#x20;

```html
<script type="sygnal/sa5-data">
name: John Doe
slug: john-doe
brief: Software Engineer
</script>
```

This would be parsed as the JavaScript object;&#x20;

```json
{
  "name": "John Doe",
  "slug": "john-doe",
  "brief": "Software Engineer"
}
```

### Nested Objects

Objects can be nested by specifying the object key on one line, and indenting the nested object beneath it;&#x20;

```html
<script type="sygnal/sa5-data">
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

Which is parsed as;&#x20;

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

## Multiline Content

There is an edge case problem here, which is that in Webflow a CMS text field can be set to multiline, and can contain line breaks. To resolve this unambiguously, wrap Webflow's embedded variable in angle brackets `<` `>`

Objects can be nested by specifying the object key on one line, and indenting the nested object beneath it;&#x20;

```html
<script type="sygnal/sa5-data">
name: The Catcher in the Rye
author: J.D. Salinger
description: <In "The Catcher in the Rye," the protagonist, Holden Caulfield, 
recounts his experiences in New York City after being expelled 
from an elite prep school.> 
</script>
```

Which is parsed as;&#x20;

{% code overflow="wrap" %}
```json
{
  "name": "The Catcher in the Rye",
  "author": "J.D. Salinger",
  "description": "In \"The Catcher in the Rye,\" the protagonist, Holden Caulfield,\nrecounts his experiences in New York City after being expelled\nfrom an elite prep school."
}
```
{% endcode %}

{% hint style="success" %}
The use of angle brackets was chosen because Webflow HTML encodes all values it embeds, which means that angle brackets cannot exist in the embedded content itself.&#x20;
{% endhint %}

{% hint style="info" %}
Also use angle brackets if whitespace characters at the start or end of your field content are an essential part of your data.&#x20;
{% endhint %}

## Technical Guide

**SA5 Data** is a custom notation designed to represent structured data in a human-readable format. It is designed specifically to work with Webflow's Custom Code areas and HTML Embeds, and to work with Webflow's HTML-encoded CMS field embeds.&#x20;

This syntax combines elements of traditional data representation formats like JSON, YAML and HCL, and simplifies them for ease of use. SA5 Data is particularly suitable for configuration, data representation, and other scenarios where clear, concise data structures are desired.

Design features;

* Is very easy to work with in Webflow's HTML Embed editor
* It reliably handles Webflow's innate HTML encoding in embedded CMS fields
* It handes line breaks in multiline embed content
* It is easily translated directly to JavaScript objects&#x20;

{% hint style="info" %}
Sygnal designed **SA5 Data** because other approaches like raw JSON embeds created too many risks for broken, unparseable data structures. SA5 Data safely transports HTML Encoded CMS data from Webflow's Collection lists into JavaScript objects with zero risk of data loss, damage, or broken scripts. &#x20;
{% endhint %}

### Basic Rules <a href="#display-captions-in-webflows-lightboxes" id="display-captions-in-webflows-lightboxes"></a>

**Script Tag:**

* Every SSD block starts with a `<script type="sygnal/`sa5-data`">` tag and ends with a `</script>` tag.

**Key-Value Pairs**:

* Represent data as `key: value` pairs.
* Each pair should be on a new line.

**Strings**:

* Strings don't need to be enclosed in quotes. However if an embedded CMS field might contain line breaks, or essential whitespace at the start or end of the field, wrap it in angle brackets `<` `>` to ensure the whitespace and line breaks are correctly interpreted.&#x20;

**Indentation**:

* Use consistent indentation (preferably spaces) to represent nested structures. The level of indentation indicates the depth of nesting.

**Nesting**:

* Nested structures are indicated by indentation.
* For each nested level, increase the indentation consistently (e.g., by two or four spaces).

**No Commas or Brackets**:

* Unlike JSON, SSD doesn't use commas to separate key-value pairs or brackets to denote objects.

## Technical Notes

In the resulting JavaScript object-

* Webflow's HTML encoded fields are decoded
* Line breaks are encoded as `\n`&#x20;

## Future

As multiline string delimiters, `<` `>` are concise and unambiguous, however we are also considering the use of `"""`, ` ``` ` or `\\\` delimiters to make them more visible.&#x20;

{% hint style="info" %}
We expect that the need for multiline strings support is relatively low.&#x20;
{% endhint %}







