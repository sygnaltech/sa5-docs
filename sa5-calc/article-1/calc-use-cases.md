# Calc Use Cases



## Count the Items in a Collection List

Preparation;

* Setup your Collection List
* Create the element where you want the Collection List count to appear&#x20;

Attributes;&#x20;

Choose a unique name for the items you're counting, we'll use `test1` for this example.&#x20;

On the element that will display the count; &#x20;

* Add the `wfu-calc` = `count` attribute&#x20;
* Add `wfu-calc-source` =  `test1` attribute &#x20;

On the collection list; &#x20;

* Place `wfu-calc-field` = `test1` directly on the Collection List Item element. &#x20;

{% hint style="success" %}
If you have more than 100 items to count, you can use multiple collection lists each ranged to show 100 items from your collection.  Assign the same `wfu-calc-field` = `test1` to each and they will all be counted together.&#x20;
{% endhint %}

## Sum the Values within a Collection List&#x20;

Preparation;

* Setup your Collection List
  * Within the Collection List, place your element which contains the value you are wanting to sum&#x20;
* Create the element where you want the Collection List sum to appear&#x20;

Attributes;&#x20;

Choose a unique name for the items you're counting, we'll use `test2` for this example.&#x20;

On the element that will display the count;&#x20;

* Add the `wfu-calc` = `sum` attribute&#x20;
* Add `wfu-calc-source` =  `test2` attribute &#x20;

On the element _within your collection list_ that contains the value to be summed;&#x20;

* Place `wfu-calc-field` = `test2` directly on the Collection List Item element. &#x20;

{% hint style="success" %}
If you have more than 100 items to count, you can use multiple collection lists each ranged to show 100 items from your collection.  Assign the same `wfu-calc-field` = `test2` to your data within each and they will all be counted together. &#x20;
{% endhint %}





