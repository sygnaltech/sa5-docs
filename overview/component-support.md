# Component Support 🧪

Webflow Components are great, but have quite a few limitations that can make them very difficult to work with in more functional setups;

## Key Limitations

* HTML Embeds within a component cannot +Add Field any content from the component properties.&#x20;
* Custom Attributes on elements within a component can only data-bind to "Attribute" type properties.
  * These must be created directly from the attribute-binding&#x20;
  * No binding to e.g. an Image url, or plain text &#x20;
* Limited property types&#x20;
  * No general URL type, for e.g. specifying a video or file download&#x20;
    * Plain text can work but does not validate the field
  * No option-list setups &#x20;
* Attribute content cannot be automatically exposed as e.g. CSS vars or JS vars for use in custom styling code



CMS



Custom Attributes can only bind to a special custom attribute type.&#x20;





Text element - text property

Rich text element - rich text property&#x20;

Div - text property











[https://www.sygnal.com/lessons/component-data-binding](https://www.sygnal.com/lessons/component-data-binding)





## Conditional Visibility

Leverage the current set of property capabilities

Conceptual

\`wfu-if-set\` = ( value )

`wfu-if-true` = ( truthy value )&#x20;

wfu-if-hide-method = remove | hide&#x20;







wfu-switch&#x20;

wfu-switch-case = x





















### How Webflow Elements Bind to Component Properties&#x20;

[https://docs.google.com/document/d/1D5lfPycDO9G-Y0-1yFtYiz6EbKhbRzsjvSZSAGU0IDE/edit?tab=t.0#heading=h.o112x0xag8a1](https://docs.google.com/document/d/1D5lfPycDO9G-Y0-1yFtYiz6EbKhbRzsjvSZSAGU0IDE/edit?tab=t.0#heading=h.o112x0xag8a1)



### How Component Properties Bind to CMS Fields

Within a collection list or collection page.&#x20;

[https://docs.google.com/document/d/1D5lfPycDO9G-Y0-1yFtYiz6EbKhbRzsjvSZSAGU0IDE/edit?tab=t.0#heading=h.e7y6xt8gwe9q](https://docs.google.com/document/d/1D5lfPycDO9G-Y0-1yFtYiz6EbKhbRzsjvSZSAGU0IDE/edit?tab=t.0#heading=h.e7y6xt8gwe9q)









## Rethinking Embeds&#x20;

As of 2025-02-08 Embeds do not support the dynamic integration of data from component properties.  However, it's possible to bind a custom attribute to aproperty,&#x20;

|                     |                                                                                                                          |   |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------ | - |
| Attribute property  | Add a propertyBind it to the                                                                                             |   |
| Text property       | Add a text property. Bind it to a text element within the component.  T                                                  |   |
| Rich text property  |                                                                                                                          |   |
| Image property      | Add an image property.  Bind it to an image element within the component ( can be hidden ).  Use script to retrieve it.  |   |
| Visibility property |                                                                                                                          |   |





## Referencing Data

To do this we first want to establish a standard for referencing data simply and flexibly from other elements within the Webflow Component's generated HTML.&#x20;

There are t

Component n





This technique can also be adjusted to the target the parent element's attribute or immediate siblings. &#x20;

| Target Element                   | Attribute                                                       | InnerText      | InnerHTML     |
| -------------------------------- | --------------------------------------------------------------- | -------------- | ------------- |
|                                  | Here `attr` is an example attribute name we want to reference.  |                |               |
| Current element attribute        | `{{#attr}}`                                                     |                |               |
| Parent element attribute         | `{{^#attr}}`                                                    |                |               |
| Prev sibling element attribute   | `{{<#attr}}`                                                    |                |               |
| Next sibling element attribute   | `{{>#attr}}`                                                    |                |               |
| Current element innerText        |                                                                 |                |               |
| Specific named element           | `{{name.#attr}}`                                                | `{{name.$}}`   | `{{name.%}}`  |
|                                  |                                                                 |                |               |

{% hint style="info" %}
Theoretically, we'd want to populate attributes first, then embeds, to allow some advanced changing.&#x20;
{% endhint %}



## Referencing Data from an Attribute &#x20;

To populate a custom attribute with Property values, we want

To do this we'll leverage SA5's existing spec for Dynamic Attributes.  &#x20;



Under consideration

```
x:attr:= 
xx:attr=  
x::attr= 

```



```
x:attr = {{#attr}} 
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





## Referencing Data from an Embed&#x20;



This technique can also be adjusted to the target the parent element's attribute or immediate siblings. &#x20;

| Target Element                   | Attribute                                                       | InnerText      | InnerHTML     |
| -------------------------------- | --------------------------------------------------------------- | -------------- | ------------- |
|                                  | Here `attr` is an example attribute name we want to reference.  |                |               |
| Current element attribute        | `{{#attr}}`                                                     |                |               |
| Parent element attribute         | `{{^#attr}}`                                                    |                |               |
| Prev sibling element attribute   | `{{<#attr}}`                                                    |                |               |
| Next sibling element attribute   | `{{>#attr}}`                                                    |                |               |
| Current element innerText        |                                                                 |                |               |
| Specific named element           | `{{name.#attr}}`                                                | `{{name.$}}`   | `{{name.%}}`  |
|                                  |                                                                 |                |               |



### Attribute Property      &#x20;

{% hint style="info" %}
As of 2025-02-08 attribute properties need to be created from the custom attribute binding directly.  Select an element, add a custom attribute, and choose the option to bind it to a component property.  You will be given an option to create a new one.&#x20;
{% endhint %}

1. Bind the attribute property directly to the Embed element itelf.  Any unique attribute name is fine, for example `my-attr`&#x20;
2. Within the embed, reference it using that attribute name, e.g.;     &#x20;

```
{{#my-attr}}
```

You can position it anywhere, and use text adjacent to it, for example;

```html
<style>
.my-class {
  color: #{{#hex-color}};
}
</style>
```

This cosntruction will pull the exact contents of the attribute named `hex-color` from the Embed element, and integrate it into the text precisely.&#x20;

{% hint style="info" %}
We're using the distinctive `{{...}}` construction because Webflow styles these specially in Embeds.  For example;&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### Parent & Sibling Attributes  &#x20;

This technique can also be adjusted to the target the parent element's attribute or immediate siblings. &#x20;

| Target Element                   | Attribute        | InnerText | InnerHTML  |
| -------------------------------- | ---------------- | --------- | ---------- |
| Current element attribute        | `{{#my-attr}}`   |           |            |
| Parent element attribute         | `{{^#my-attr}}`  |           |            |
| Prev sibling element attribute   | `{{<#my-attr}}`  |           |            |
| Next sibling element attribute   | `{{>#my-attr}}`  |           |            |
| Current element innerText        |                  |           |            |











## Image Property&#x20;

1. Place an image element immediately adjecent to and prior to the Embed &#x20;
2. Bind it to your image property&#x20;
3. In the embed, target the sibling's source attribute, e.g.&#x20;

```html
<a href="{{<#src}}" target="_blank">Open this image in a new tab</a> 
```





## Named

The component itself MUST have an attribute;

This identifies the outer bound of the component cleanly, so that variables can be scoped within it.&#x20;

```
wfu-component-name="foo" 
```

Within that



```
<img src="..." wfu-component-value=""    
```







Visibility Property

? Check for element existance &#x20;







