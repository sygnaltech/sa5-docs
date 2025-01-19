---
description: Style Webflow's nested lists within rich text blocks
---

# Nested Lists ❺

{% hint style="info" %}
All of the code given here will be pasted directly into a `<style>` block within an Embed on the page containing your rich text block.&#x20;

This allows you to customize it to your specific needs, and for it to work while you're in the designer.&#x20;
{% endhint %}

## Ordered List Styling

### Basic Styling 1. A. a.&#x20;

Suppose you want a basic ordered list, where the first level is decimal, the second is uppercased letters and the third is lowercase letters.&#x20;

This code will perform this to all ordered lists on your page.&#x20;

```html
<style>
ol[role="list"] {
  list-style-type: decimal;
}
ol[role="list"] > li > ol[role="list"] {
  list-style-type: upper-alpha;
}
ol[role="list"] > li > ol[role="list"] > li > ol[role="list"] {
  list-style-type: lower-alpha;
}
</style>
```



### Technical Styling&#x20;

Technical styling is a bit different, it's a sequence of numbers like `2.1.14` that indicidates a specific level of your list.  We can achieve that in pure CSS as well using CSS counters.&#x20;

Give your rich text element the class `hierarchical-list`. This can be a global class, an in addition to other classes on your list. &#x20;

My code here;

* Will apply technical numbering to all ordered lists within your rich text element
* Will restart for each one
* Handles 3 levels only- you can make it deeper by continuing the same pattern
* Doesn’t apply any level-specific styling, but you can
* Works in the designer at design time, if the `<style>` chunk is in an embed rather than the before-/head custom code area.



```html
<style>
.hierarchical-list > ol {
  counter-reset: level1;
}
.hierarchical-list ol {
  padding-left: 1.5em;
}
.hierarchical-list li {
  display: block;
  list-style: none;
}
.hierarchical-list > ol > li {
  counter-increment: level1;
}
.hierarchical-list > ol > li::before {
  content: counter(level1) ". ";
  font-weight: bold;
}
.hierarchical-list ol > li > ol {
  counter-reset: level2;
}
.hierarchical-list ol > li > ol > li {
  counter-increment: level2;
}
.hierarchical-list ol > li > ol > li::before {
  content: counter(level1) "." counter(level2) ". ";
}
.hierarchical-list ol > li > ol > li > ol {
  counter-reset: level3;
}
.hierarchical-list ol > li > ol > li > ol > li {
  counter-increment: level3;
}
.hierarchical-list ol > li > ol > li > ol > li::before {
  content: counter(level1) "." counter(level2) "." counter(level3) ". ";
}
</style>
```



{% embed url="https://codepen.io/memetican/pen/ByBVGOQ/c71ab402fbba73a0c1e1e2fb50821e93" %}











































\
