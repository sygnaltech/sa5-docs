---
description: Get fancier with your attribute replacements.
---

# Prefix, Postfix, and Formatted Attributes 🧪

{% hint style="info" %}
Feature under consideration.&#x20;
{% endhint %}

The `x:my-attr` syntax allows for a full replacement of an existing attribute, and solves two main limitations;

* Reserved attributes that you cannot create in the Webflow Designer&#x20;
* Attributes which do not support CMS / component property data-binding&#x20;

However what if you want to modify an existing attribute, or create a composite attribute value from a blend of CMS-sourced and static content?

## Prefix, Postfix, and Format

Sygnal is considering the addition of 3 variations to the `x:` attribute processor;

* `x:pre:(attr)` - prefixes the attribute with a new value, either static or data-bound
* `x:post:(attr)` - postfixes ( appends ) the attribute with a new value, either static or data-bound
* `x:format:(attr)` - creates a new attribute from a formatting string, that can combine several atributes and several pieces of static text into one resulting attribute value.&#x20;

### Format String&#x20;



## Using the `x:` attributes together

We'll use example of a `src` attribute here;&#x20;

There are _three_ general Scenarios we want to support;

* A `src` attribute already exists, and we want to replace it
* A `src` attribute already exists, and we want to modify it
* A `src` does not exist, and we want to create it

### Processing Rules

Here's how the `x:` attributes will be applied to compose a new value;&#x20;

1. `src` attribute is retrieved, if it exists

Attribute replacements occur;&#x20;

1. `x:src` attribute overwrites that, if it exists
2. `x:format:src` attribute overwrites that, if it exists

Attribute modifiers are applied;&#x20;

1. `x:pre:src` prefixes the result
2. `x:post:src` postfixes the result

The final attribute value is then applied.&#x20;



## Use Cases

Styling;

* Append a class to your class list
* Append a style to your style attribute, from the CMS

```
<div style="color: red; color: blue;">
    This text will be blue.
</div>

```

{% hint style="info" %}
CSS properties are applied in the order they appear in the `style` attribute. When the same property is specified multiple times, the browser will apply the last value it encounters, effectively overriding any previous values for that property.
{% endhint %}

**Format:** `x:format:style="{background-style}; {margin-style}; {padding-style}"`

Format: x:format:src="{x:pre:src}/{path}{x:post:src}"

Format: x:format:class="{base-class} {status-class} {modifier-class}"

Format: x:format:style="{background-style}; {margin-style}; {padding-style}"

See Examples.&#x20;



## Examples

When thinking through the use cases for the `x:format:attrname` functionality, it's helpful to consider the types of scenarios where you might want to amalgamate different pieces of information into a single attribute value. Here are some common use cases where such a feature could be particularly useful:

#### 1. **Dynamic URL Construction**

* **Use Case:** You might want to construct URLs dynamically based on multiple attributes or static text.
* **Example:** Constructing an image URL that includes a CDN prefix, a file path, and versioning information.
* **Output:** `https://cdn.example.com/images/photo.jpg?v=123`
* **Format:** `x:format:src="{x:pre:src}/{path}{x:post:src}"`

#### 2. **Class Name Aggregation**

* **Use Case:** Combine multiple class names into a single `class` attribute.
* **Example:** Aggregating base class names with conditionally added ones.
* **Output:** `btn btn-primary active`
* **Format:** `x:format:class="{base-class} {status-class} {modifier-class}"`

{% hint style="info" %}
`x:pre` and `x:post` will behave specially with the `class` attribute and ensure a space delimiter between the prefixed/postfixed content and the original class list.&#x20;
{% endhint %}

#### 3. **Data Attributes Construction**

* **Use Case:** Create a complex `data-*` attribute by combining several other data attributes or values.
* **Example:** Combining user ID, session ID, and a specific data type into a single `data-user-info` attribute.
* **Output:** `12345-67890-typeA`
* **Format:** `x:format:data-user-info="{data-user-id}-{data-session-id}-{data-type}"`

#### 4. **ARIA Attribute Construction**

* **Use Case:** Dynamically generate ARIA labels or IDs by amalgamating content from other attributes.
* **Example:** Constructing an `aria-labelledby` attribute based on dynamic elements.
* **Output:** `label1 label2`
* **Format:** `x:format:aria-labelledby="{label-id1} {label-id2}"`

#### 5. **SEO-Friendly Meta Tag Generation**

* **Use Case:** Generate dynamic meta tag content like `description` or `og:title` based on page-specific data.
* **Example:** Creating a meta description that includes the title and summary.
* **Output:** `Learn more about our product, which is designed for efficiency and ease of use.`
* **Format:** `x:format:content="{page-title} - {page-summary}"`

#### 6. **Dynamic Inline Styles**

* **Use Case:** Combine multiple inline style properties into a single `style` attribute.
* **Example:** Merging dynamic background color, margin, and padding into one `style` attribute.
* **Output:** `background-color: red; margin: 10px; padding: 5px;`
* **Format:** `x:format:style="{background-style}; {margin-style}; {padding-style}"`

#### 7. **Complex Data Serialization**

* **Use Case:** Serialize complex data into a single string that might be passed as a value in an attribute.
* **Example:** Combining a user’s preferences into a serialized string for a `value` attribute.
* **Output:** `dark-mode=true&font-size=large`
* **Format:** `x:format:value="{theme}&{font-size}"`

#### 8. **Dynamic Event Handler Attachment**

* **Use Case:** Construct JavaScript function calls dynamically by amalgamating function names, arguments, or other strings.
* **Example:** Building an `onclick` handler that includes a dynamic function name and parameters.
* **Output:** `handleClick('item1', 'active')`
* **Format:** `x:format:onclick="{function-name}('{param1}', '{param2}')"`

#### 9. **Breadcrumb Navigation Construction**

* **Use Case:** Generate breadcrumb navigation paths by combining URL segments.
* **Example:** Building a breadcrumb that includes the base URL and multiple path segments.
* **Output:** `home > category > product`
* **Format:** `x:format:breadcrumbs="{home} > {category} > {product}"`

#### 10. **Content-Based Image `alt` Text**

* **Use Case:** Construct descriptive `alt` text for images based on different dynamic content.
* **Example:** Combining product name, color, and category for an image’s `alt` text.
* **Output:** `Red T-Shirt in Men's Clothing`
* **Format:** `x:format:alt="{product-name} in {category}"`

#### Considerations for Designing the `x:format` Attribute:

* **Flexibility:** The format string should allow for dynamic inclusion and ordering of attributes and static text.
* **Default Values:** Consider how to handle cases where an attribute referenced in the format string doesn't exist. You might want to allow default values or handle it gracefully (e.g., leaving it blank).
* **Escaping Special Characters:** If the format string includes special characters that might interfere with parsing, there should be a way to escape these characters.

####















