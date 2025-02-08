# Component Support





## Embeds

As of 2025-02-08 Embeds do not support the dynamic integration of data from component properties.  However, it's possible to bind a custom attribute to a property

|                     |                              |   |
| ------------------- | ---------------------------- | - |
| Attribute property  | Add a propertyBind it to the |   |
| Text property       |                              |   |
| Rich text property  |                              |   |
| Image property      | Add an adj                   |   |
| Visibility property |                              |   |



## Attribute Property      &#x20;

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

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Parent & Sibling Attributes  &#x20;

This technique can also be adjusted to the target the parent element's attribute or immediate siblings. &#x20;

|                                  |                  |   |
| -------------------------------- | ---------------- | - |
| Current element attribute        | `{{#my-attr}}`   |   |
| Parent element attribute         | `{{^#my-attr}}`  |   |
| Prev sibling element attribute   | `{{<#my-attr}}`  |   |
| Next sibling element attribute   | `{{>#my-attr}}`  |   |



## Image Property&#x20;

1. Place an image element immediately adjecent to and prior to the Embed &#x20;
2. Bind it to your image property&#x20;
3. In the embed, target the sibling's source attribute, e.g.&#x20;

```html
<a href="{{<#src}}" target="_blank">Open this image in a new tab</a> 
```





Visibility Property

? Check for element existance &#x20;







