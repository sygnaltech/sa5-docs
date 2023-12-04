---
description: Transform your Webflow Page content in unique ways
---

# Hyperflow Transform

{% hint style="info" %}
**These are 100% internal R\&D.**\
No public product is available, but if you need these features, contact us for details on how we can implement them for you.&#x20;
{% endhint %}

## x-attributes



NoIndex

```
<meta name="robots" content="noindex" />
```

A "noindex" HTTP response header

```
X-Robots-Tag: noindex
```



## HTML Decode chunks

To support a kind of HTML Embed field in the CMS.&#x20;











## Configuration concept

### General v. Specific

Site wide, with page-level overrides

### Sequence

Transforms MAY occur in the specific, described sequence.&#x20;





## Configuration examples

The config will likely use YAML to minimize syntax requrirements;&#x20;

This convention follows the format for Media Types where `type/subtype+suffix` signifies that the content is a subtype that follows the serialization format of the suffix (in this case, JSON).



Type: sygnal/

### Type: `sygnal/proxy+json`

Changing to sygnal/hyperflow+json

More verbose, but also more familiar to many web developers.&#x20;

```html
<script type="sygnal/proxy+json">
[
  {
    "sitemap": {
      "lastUpdated": "2023-11-06"
    }
  },
  {
    "conditional": "remove"
  },
  {
    "nofollow": "external"
  }
]
</script>
```



### Type: `sygnal/proxy+yaml`

Changing to sygnal/hyperflow+yaml

```html
<script type="sygnal/proxy+yaml">
- sitemap:
    lastUpdated: "2023-11-06"
- conditional: remove
- nofollow: external
</script>
```

## Important YAML notes

Arrays and objects.

The hyphen (`-`) in YAML is used to denote elements of a sequence, which is YAML's way to represent arrays or lists. If you're defining a sequence of items, each new item in the list is prefixed with a hyphen and space.

```
// Some code
- item1
- item2
- item3

```

In the context of the YAML you're discussing, the hyphens are used to create an array of objects:

```
// Some code
- sitemap:
    lastUpdated: "2023-11-06"
- conditional: remove
- nofollow: external

```

Each hyphen indicates a new object in the list. Without the hyphens, the YAML would represent a single object with multiple properties, not an array. If you were to remove the hyphens and still want to keep the structure as an array of objects, you would need to adjust the syntax accordingly, which would not be valid YAML for an array.

However, if your goal is to have a single object with multiple properties, you would format your YAML like this (without hyphens):

Double quotes

In YAML, quotes are optional for strings unless the string:

1. Contains characters that can be misinterpreted as YAML syntax, such as `:`, `{`, `}`, `[`, `]`, `,`, `&`, `*`, `#`, `?`, `|`, `-`, `<`, `>`, `=`, `!`, `%`, `@`, ` and `` `.
2. Starts with a character that could be misinterpreted as a non-string scalar, such as a digit, or the characters `-`, `?`, or `:`.
3. Contains leading or trailing spaces, or line breaks, which you want to be part of the string.

For instance:

```
// Some code
- date: 2023-11-06     # No quotes needed
- title: "Hello: World" # Quotes needed because of the colon
- path: /path/with spaces/ # Quotes needed because of the spaces

```

The quotes around the date are not strictly necessary according to YAML syntax rules. I included them because dates can sometimes be interpreted as other types, such as integers or dates, depending on the parser's capabilities and settings. To ensure that the value is treated as a string, it can be helpful to enclose it in quotes. However, in this specific case, even without the quotes, most parsers would interpret `2023-11-06` correctly as a date in YAML.

In other cases, you might include quotes to signal that the data should definitely be interpreted as a string:&#x20;

```yaml
- number: "1234" # Without quotes, this would be interpreted as an integer.
- boolean: "true" # Without quotes, this would be interpreted as a boolean.
```



```javascript
// Some code
const yaml = require('js-yaml');
const fs = require('fs');

try {
  // Load the YAML file
  const doc = yaml.load(fs.readFileSync('path/to/your/file.yaml', 'utf8'));
  
  // Convert to an array of JSON objects if not already
  const jsonArray = Array.isArray(doc) ? doc : [doc];
  
  // Log the JSON array
  console.log(jsonArray);

  // If you need the JSON as strings, you can stringify the array
  const jsonString = JSON.stringify(jsonArray, null, 2);
  console.log(jsonString);
  
} catch (e) {
  console.log(e);
}
```

## Debugging

Output to config

Server-side config log









