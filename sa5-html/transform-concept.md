# Transform (concept)

## Use cases

* Modify attributes such as hrefs by combining static and dynamic CMS content
* Solve the lack of CMS attribute binding on ECommerce lists&#x20;

## Example

Position within a collection list item, to target relative items such as a wrapper link.

Here we're using closest with a CSS selector;&#x20;

```html
<script type="sa5:transform:attr"
   target="closest"
   selector="'a'"
   attr="href"
   val="/browse?category=EMBED-FIELD"
   ></script>
```



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





