---
description: Binding data from form elements
---

# Form Elements 📝



Elim wfu-query-param

Revisit user binding&#x20;

And cookie binding&#x20;

* inding lists to FORM Dropdown elements, as select options
* Binding lists to FORM Text elements, as autocomplete options



## Link

Linkelement&#x20;

Binds the URL portion ONLY&#x20;





Text&#x20;





RichText

Manual





## Select

Place the wfu-bind attribute on the Select Field element

![](<../../.gitbook/assets/image (3) (1) (1).png>)

{% hint style="info" %}
The value you assign is case-sensitive to e.g. querystring keys. &#x20;
{% endhint %}



## Checkbox

Bind boolean values directly to&#x20;

e.g.

`wfu-bind = ?accept`



Would&#x20;





### Boolean Values

Most values will be evaluated as **true**, with the exception of these specific values which are evaluated as **false**: `false`, `f`, `0`, `no`, `off`, as well as `undefined` or `null`. Falsy values are case-insensitive, so `False` is the same as `false`.&#x20;

![](<../../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png>)



wfu-bind-parser

Define value parsers?

For alternate boolean rules

For international dates, numbers, etc.&#x20;







