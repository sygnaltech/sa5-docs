---
description: Future plans for SA5 dynamic attributes
---

# Future



## Transforms

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



