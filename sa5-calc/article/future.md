---
description: Future ideas for SA5 Calc
---

# Future

Progression;

* Very simple calcs ( SUM, COUNT, etc. )&#x20;
  * Single-pass
  * < 100 items as data source ( or multiple collection lists )&#x20;
* More complex calcs ( STD, AVG, etc. )&#x20;
* More complex sourcing
  * Other SA5 data sources&#x20;
  * FS Load&#x20;
* Grouping and rollups&#x20;
  * Arbitrary groupings
    * Multiple tiers possible
* Crosstabs, matrices, etc. &#x20;

## Progressive Data Source Definition ( DSD )&#x20;

Define a source using SA5 Data standards, or else a new arbitrary standard which is based on e.g. CSS Queries and Attributes.&#x20;

Concept;&#x20;

```html
<sa5-data-source
  name="price"
  selector=".item[data-price]"
  attr="data-price"
  ></sa5-data-source> 
```

Or;

* source from internal content
* source from internal secondary selector&#x20;

Transform;

```html
<sa5-data-source
  name="price-group"
  transform="group"
  data-source="price"
  selector=".item[data-price]"
  attr="data-price"
  >
  {
    ["group name 1", "lt", 1000],
    ["group name 2", "between", 1001, 1000],
  }
  </sa5-data-source> 
```

## Grouping Concepts

Allow a single item to match multiple groups. This gives flexibility and puts the definition rules on the user.

* lt, lte
* gt, gte
* between - > >= < <=&#x20;

Auto calculate count

Auto calculate sum&#x20;

Consider referencing grouped elements as their own data source for other purposes&#x20;

### Challenges

Consider range grouping approaches - between, > >= < <=&#x20;
