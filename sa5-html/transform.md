---
description: Automatically modify elements and attributes in your Webflow hosted page.
---

# Transform ❺🧪

Note that dynamic attributes would likely be moved here;

x-attribute is a transform / overwrite&#x20;

xe-element type?&#x20;

xx-element = change element type?&#x20;

ww-wrap = create element wrapper?&#x20;

## Use cases

* Modify attributes such as hrefs by combining static and dynamic CMS content
* Solve the lack of CMS attribute binding on ECommerce lists&#x20;
* Wrap collection lists / nested collection lists in a link by transforming a wrapper DIV

## Concept

* Sequential series of transforms, applied in order, e.g.
  * Create element
  * Add attribute
  * Add second attribute



## Example

Position within a collection list item, to target relative items such as a wrapper link.

Here we're using closest with a CSS selector;&#x20;



```html
<script type="sa5:transform:hson">
[]
selector: div.foo
target: closest
transform: elem
type: a
[]
// replace attribute
selector: a
target: closest
transform: attr
name: href
val: /browse?category=EMBED-FIELD
[]
</script>
```



```html
<script type="sa5:transform:attr"
   target="closest"
   selector="'a'"
   attr="href"
   val="/browse?category=EMBED-FIELD"
   ></script>
```

Use sa5 data format;&#x20;



Add;

* querystring encoding, compat with FS filter&#x20;
* append rather then replace

```html
<script type="sa5:transform:attr"
   target="closest"
   selector="'a'"
   transform="append"
   attr="href"   
   val="EMBED-FIELD"
   encode="querystring" 
   ></script>
```



script type

`sa5:transform:attr` -&#x20;

`target` = closest | ?

selector = CSS selector string used with closest

transform = **`replace`** | `append` | `prepend`

attr = attribute to transform

val = value to use in the transform

encode = none | querystring | url

## Notes&#x20;

Runtime diagnostics are important here.&#x20;



