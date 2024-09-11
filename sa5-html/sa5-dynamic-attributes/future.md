---
description: Future plans for SA5 dynamic attributes
---

# Future

## Smart options

* Force overwrite
* Overwrite only if non-blank

## Change to `x:` prefix

Currently we prefix attributes with `x-` however this convention is already used in Alpine JS.  While this is unlikely to create conflicts, we'd like to avoid the possibility of confusion as well.

## Removing Attributes After processing

Default false, but can enable this as a lib config option.&#x20;

## Prefix and Postfix

`x:pre:(name)` = ( value )&#x20;

`x:post:(name)` = ( value )

`x:format:(name)` = ( value )



`x:pre:(attribute)` = ( value )

`x:post:(attribute)` = ( value )

```
<img 
  x:src="image.jpg" 
  x:pre:src="https://cdn.example.com/" 
  x:post:src="?version=123">
```

Would result in;

```
<img src="https://cdn.example.com/img.jpg?version=123"> 
```





```
<img 
    src="image.jpg" 
    x:pre:src="https://cdn.example.com/" 
    x:post:src="?version=123" 
    x:format:src="{x:pre:src}{src}{x:post:src}" 
/>

```

Use cases;

* In a CMS-bound link, append `#hash` or `?query=foo` data.&#x20;
* Append classes to your class list without overwriting them

```
<div class="foo" x:post:class="bar"></div>
```

Result;

```
<div class="foo bar"></div>
```

Use cases;







## Smart Attributes

[Learn more](smart-attributes.md).

## \<script> based transforms

Generate an attribute from a specially-typed script block within it, with the purpose being to;

* Easily mix static text and dynamic attributes
* Support larger strings, e.g. JSON chunks
* Resolve attribute content limitations in Webflow
  * Inability to include double-quotes `"` in content&#x20;
* Resolve attribute name limitations in Webflow

Targeting can be parent, prev sibling or next sibling, or a target element(?) with an SA5 identifier

[https://discourse.webflow.com/t/embed-cal-com-pop-up-via-element-click/277487/3](https://discourse.webflow.com/t/embed-cal-com-pop-up-via-element-click/277487/3)

Supporting JSON chunks in the designer

`&quot;` `/x0022`&#x20;

Ideally design this so that it can also support Hyperflow processing.&#x20;



## Transforms

[Learn more](../transform.md)

Dynamic Attributes are likely to become a facet of a larger SA5 concept we'll call DOM Transforms. Transforms allow for broad changes to happen, and have a specific instructional paradigm;

* What to target, relative to the transform's position- useful for collection lists.
* What kind of transformation to do.&#x20;
* The data needed for the transformation

For example

`sa5:transform:attr`&#x20;

* Targeting
  * `target`&#x20;
  * `selector`
  * `attr`
* Transform&#x20;
  * `transform = append | replace | prepend, etc`   &#x20;
* Data
  * `val = (value)`&#x20;
    * Typically a field embed. This would be HTML encoded&#x20;
  * `decode` = html | none
  * `encode`

We're looking at adding&#x20;



```
// Some code
<script type="sa5:transform:attr"
   target="closest"
   selector="'a'"
   transform="append"
   attr="href"   
   val="{{wf {&quot;path&quot;:&quot;name&quot;,&quot;type&quot;:&quot;PlainText&quot;\} }}"
   encode="querystring" 
   ></script>
```



