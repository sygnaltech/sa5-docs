# Breakpoints

Webflow offers 7 [breakpoints](https://help.webflow.com/hc/en-us/articles/33961300305811-Breakpoints-overview#01JDAHFPAZZAB1RDDCC69D8YVG).&#x20;

| Breakpoint Name  | Abbr | Minimum Width | Maximum Width |
| ---------------- | ---- | ------------- | ------------- |
| XX-Large         | 1920 | 1920px        | ∞             |
| X-Large          | 1440 | 1440px        | 1919px        |
| Large            | 1280 | 1280px        | 1439px        |
| Desktop (base)   | D    | 992px         | 1279px        |
| Tablet           | T    | 768px         | 991px         |
| Mobile Landscape | L    | 480px         | 767px         |
| Mobile Portrait  | P    | -             | 479px         |

Goals;&#x20;

* Allow some SA5 attributes to be enabled only on certain breakpoints&#x20;
* Allow some SA5 attributes to be configured differently on different breakpoints&#x20;
  * Utilize Webflow's natural "override from desktop" behavior here if possible&#x20;

## SA5 & Breakpoints&#x20;

Some of SA5's attribute settings are breakpoint-aware, meaning that their configuration can be changed for specific breakpoints.&#x20;

* In simple cases, we simply want to be able to switch on or off the attribute's behavior at specific breakpoints.&#x20;
* In more complex cases, we may have breakpoint-specific configurations.&#x20;

This leads to 3 classes of attributes;&#x20;

| Attribute type                                    | Responsive enable/disable? | Responsive config? |
| ------------------------------------------------- | -------------------------- | ------------------ |
| <p>Standard attributes <br>( Non-responsive )</p> | -                          | -                  |
| Simple Responsive attributes                      | Yes                        | -                  |
| Complex Responsive attributes                     | Yes                        | Yes                |



## Simple-Responsive Attributes

A Simple Reponsive attribute can be switched on or off using a special modifier;

`*:bp` = ( breakpoints list )   &#x20;

{% hint style="info" %}
e.g. we might have `sa-layout:bp` = `d+`  &#x20;
{% endhint %}

The breakpoints list is a comma-separated list, defining the breakpoints which should be supported.

* Breakpoints can be listed in any order &#x20;
* They must be comma-separated
* They are case-insensitive - D and d are identical&#x20;
* They can be range-expanded using `+` and `-` modifiers&#x20;
  * `+` meaning _this breakpoint and larger_ &#x20;
  * `-` meaning _this breakpoint and smaller_ &#x20;

Examples;

<table><thead><tr><th width="152"></th><th>1920</th><th>1440</th><th>1280</th><th>Desktop</th><th>Tablet</th><th>Landscape</th><th>Portrait</th></tr></thead><tbody><tr><td><code>d+</code></td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>-</td><td>-</td><td>-</td></tr><tr><td><code>d-</code></td><td>-</td><td>-</td><td>-</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td><code>l-</code></td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td><td>Yes</td><td>Yes</td></tr><tr><td><code>1440+,t,p</code></td><td>Yes</td><td>Yes</td><td>-</td><td>-</td><td>Yes</td><td>-</td><td>Yes</td></tr></tbody></table>

Notes;

* Overlapping specifications are fine, but not recommended
  * e.g. `1280+,1920` is redundant, but will be processed fine&#x20;



## Complex-Responsive Attributes

{% hint style="danger" %}
Still under specification&#x20;
{% endhint %}



On these attributes, that's achieved by adding a special suffix to the custom attribute name.  For example, an attribute named `sa-attr` could have these suffixes.&#x20;



{% hint style="info" %}
These attributes are applied in a cascading fashion in the same way that breakpoints work within Webflow directly.  However, if you have overlapping configs, they will be applied in the order specified with the last one taking precedence.&#x20;
{% endhint %}







Ideas;

:bp - specify breakpoints this attribute applies on&#x20;







sa-layout

sa-layout-target

sa-layout-pos = 5

sa-layout-pos:T = 4

sa-layout-pos:L = 3





Layout-sensitive elements

Re-execute on breakpoint changes&#x20;



## Configuration Blocks









\``wfu-grid-equalheightrows:bp` = ( breakpoints )&#x20;







### Combined Config Block&#x20;

With breakpoint-specific sub-objects&#x20;

```html
<script type="application/sa5+json" name="foo">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": "",
  "1280": {
    "type": "contact",
    "item": ""  
  } 
}
</script>
```



### Responsive Config Blocks





```html
<script type="application/sa5+json" name="foo" bp="1280+">
{
  "@context": "https://attr.sygnal.com",
  "@type": "ConversionEvent",
  "@version": "0.1",
  "url": "https://conversion-tracker-url.com", 
  "transactionIdType": "query", 
  "transactionId": "transactionId",
  "type": "contact",
  "item": "" 
}
</script>
```









## Technical Notes

SA6 might add core attribute foundations, e.g.&#x20;

* Default attribute
* Configurable attribute ( can have a config block )&#x20;
* Responsive attribute
* Responsive configurable attribute&#x20;







