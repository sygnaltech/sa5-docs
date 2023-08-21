---
description: Filtering any element or Collection List using custom logic.
---

# Advanced Element Filtering ❺

Webflow has a powerful conditional visibility feature, however it falls short when you have complex or dynamic rules.&#x20;

SA5's advanced filtering allows you to filter any element using a simple JavaScript expression or evaluation function.

## Use Cases

Here are a few ways you could use it;&#x20;

* Display certain elements only between certain hours of the day, certain days of the week, months or seasons of the year, etc.&#x20;
* Show employees who have a birthday today, or this month.&#x20;

## Demonstration <a href="#usage-notes" id="usage-notes"></a>

{% embed url="https://webflow-smart-elements.webflow.io/filter" %}
Demo
{% endembed %}

{% embed url="https://webflow.com/made-in-webflow/website/webflow-tabs-hacks" %}
Cloneable
{% endembed %}

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

The basic approach is to attach the filter attribute to the elements you want to conditionally display, and then add simple JavaScript logic that is evaluated.&#x20;

Elements will be displayed If the evaluation returns `true`.

### `wfu-filter-match` attribute

Specify a **CSS selector** to match. If the element matches the selector, the element will be displayed. This is most powerful when paired with Webflow's CMS-bound custom attributes, and an evaluation string.&#x20;

For example, suppose your CMS items have a numeric field indicating the day of week. In JavaScript convention, 0 is Sunday, 1 is Monday, through to 6 is Saturday.&#x20;

If you store that number in a CMS field and then bind it to a custom attribute, you can easily create a custom attribute on your Collection Item of e.g. `weekday` = `2`&#x20;

You can then use the SA5's match filter attribute with a [CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_selectors) and a [JavaScript template literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template\_literals), create a match filter like this;&#x20;

```
wfu-filter-match = [weekday='${new Date().getDay()}']
```

This indicates that the element should be displayed IF the weekday attribute is equal to today's weekday number, according the the visitor's local system clock.&#x20;

{% hint style="info" %}
The constructions can be complex as they involve 3 combined syntaxes;&#x20;

* [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_selectors), which are very powerful. In this example, our selector takes the form `[weekday='2']` which matches all elements that have the `weekday` attribute, with the value `2`.&#x20;
* [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template\_literals), the `${` ... `}` part, which allows us to embed evaluated JS content such as today's weekday.
* The [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) expression, in this case `new Date().getDay()` which returns [today's weekday number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date/getDay) 0 - 6. &#x20;
{% endhint %}

{% hint style="info" %}
This feature is useful in very compact situations where your filter-match expression is concise. If it gets long or complex, use `wfu-filter-func` instead.&#x20;
{% endhint %}

### `wfu-filter-eval` attribute <a href="#wfu-filter-attribute" id="wfu-filter-attribute"></a>

Specify a formula for evaluation. If it evaluates to true, the element will be displayed.

```
wfu-filter-eval = new Date().getHours() >= 12
```

Best used for short and simple expressions.

### `wfu-filter-func` attribute <a href="#wfu-filter-func-attribute" id="wfu-filter-func-attribute"></a>

Use `wfu-filter-func` to call a function you define, and to pass in the element as an HTML element. From there, you can perform any checks or calculations you want and then return `true` if you’d like the element to display, or `false` if you want to hide it.

```
wfu-filter-func = isBirthday
```

And then define a function by that name, e.g.;&#x20;

```html
<script>
  function isBirthday(item) {
    
    var today = new Date();
    var date = new Date($(item).find("data").attr("date")); 

    console.log(today);
    console.log(`${today.getMonth()} ${date.getMonth()}`);
    console.log(`${today.getDate()} ${date.getDate()}`);
    
    // Check to see if birthday is THIS MONTH 
    if (
      (today.getMonth() == date.getMonth())
//      && (today.getDate() == date.getDate())
    )
      return true;
   
    return false;
  }
</script>
```

Here's another example that filters based on an in-text match;

```html
<script>
window.filterText = function(e) {
    return e.textContent.toLowerCase().includes("blog"); 
}
</script>
```

Make sure to give it a single parameter, as it will be passed the element you are evaluating in the filter. The evaluation function you create must be top level, so it will be referenced from the `window` object. &#x20;

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### STEP 2 - Apply `wfu-filter` or `wfu-filter-func` to the elements you want to filter <a href="#step-2---apply-wfu-filter-or-wfu-filter-func-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-filter-or-wfu-filter-func-to-the-elements-you-want-to-filter"></a>

See above for details.

\
