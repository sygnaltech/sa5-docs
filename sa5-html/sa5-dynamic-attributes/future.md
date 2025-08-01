---
description: Future plans for SA5 dynamic attributes
---

# Future

## Smart options

* Force overwrite
* Overwrite only if non-blank ( coalesce )&#x20;

## Multiple Suffixes &#x20;

### Prefix & postfix&#x20;

`:post` - Add as a suffix.

`:pre` - Add as a prefix.&#x20;

### Data-binding&#x20;

`:bind` - Indicates the value will be pulled from a datasource&#x20;

### Localization

Applies this dynamic attribute rule only when the locale matches.&#x20;

`:locale(en)` -&#x20;

`:locale(en-gb)` -&#x20;

{% hint style="info" %}
Locale is always lowercased for matching.&#x20;
{% endhint %}

### Transform&#x20;

`:transform(lower)` - Lowercase  &#x20;

`:transform(upper)` - Uppercase &#x20;

## Binding to SA5 Simple Data Sources&#x20;

```
x:attr:bind = ?query
```

? Use cases ??&#x20;

## Transformer Functions     &#x20;

Combine information from several sources and set it as a dynamic attribute value.&#x20;

* Other attributes on this element
* Other attributes on other elements&#x20;
* Static text&#x20;

```
x:attr:transform = {{#abc}}def{{#ghi}}
```







This technique can also be adjusted to the target the parent element's attribute or immediate siblings. &#x20;

| Target Element                   | Attribute                                                       | InnerText      | InnerHTML     |
| -------------------------------- | --------------------------------------------------------------- | -------------- | ------------- |
|                                  | Here `attr` is an example attribute name we want to reference.  |                |               |
| Current element attribute        | `{x:myval=#attr}}`                                              |                |               |
| Parent element attribute         | `{{^#attr}}`                                                    |                |               |
| Prev sibling element attribute   | `{{<#attr}}`                                                    |                |               |
| Next sibling element attribute   | `{{>#attr}}`                                                    |                |               |
| Current element innerText        |                                                                 |                |               |
| Specific named element           | `{{name.#attr}}`                                                | `{{name.$}}`   | `{{name.%}}`  |
|                                  |                                                                 |                |               |





## Examples&#x20;



```
<div abc="123" ghi="456">789</div>
```



|                        | Interpreted As                                                                       | Resulting Value |
| ---------------------- | ------------------------------------------------------------------------------------ | --------------- |
| `12{{#abc}}`           | <ul><li>String "12"</li><li>Attribute abc value</li></ul>                            | `12123`         |
|                        |                                                                                      |                 |
|                        |                                                                                      |                 |
| `{{#abc}}def{{#ghi}}`  | <ul><li>Attribute abc value</li><li>String def</li><li>Attribute ghi value</li></ul> | `123def456`     |
|                        |                                                                                      |                 |











## Removing Attributes After processing

Default false, but can enable this as a lib config option.&#x20;

## Prefix and Postfix

`x:(attr):pre` = ( value )&#x20;

`x:(attr):post` = ( value )





Future;&#x20;



`x:(attr):format` = ( value )















```
<img 
  x:src="image.jpg" 
  
  
  x:src:pre="https://cdn.example.com/" 
  x:src:post="?version=123">
  
  
  
  x:src:start
  x:src:end
  
  x:src:before
  x:src:after
  
  
  
  
```

Would result in;

```
<img src="https://cdn.example.com/img.jpg?version=123"> 
```





```
<img 
    src="image.jpg" 
    x:src:pre="https://cdn.example.com/" 
    x:src:post="?version=123"  
/>
```



Future;&#x20;



```
<img 
    src="image.jpg" 
    x:src:pre="https://cdn.example.com/" 
    x:src:post="?version=123" 
    x:src:format="{x:pre:src}{src}{x:post:src}" 
    x:src:transform="funcName" 
/>
```



Calls a JS function on window.funcName, and passes the element.  The function returns a value, which is then applied to the attribute. &#x20;





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

















