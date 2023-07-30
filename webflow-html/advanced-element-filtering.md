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

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

The basic approach is to attach the filter attribute to the elements you want to conditionally display, and then add simple JavaScript logic that is evaluated.&#x20;

Elements will be displayed If the evaluation returns `true`.

### `wfu-filter` attribute <a href="#wfu-filter-attribute" id="wfu-filter-attribute"></a>

Use `wfu-filter` with a specific formula to suppress the current node.

```
wfu-filter = new Date().getHours() >= 12
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

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.8/dist/css/webflow-html.css">
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.8/dist/nocode/webflow-html.js"></script>
```
{% endcode %}

### STEP 2 - Apply `wfu-filter` or `wfu-filter-func` to the elements you want to filter <a href="#step-2---apply-wfu-filter-or-wfu-filter-func-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-filter-or-wfu-filter-func-to-the-elements-you-want-to-filter"></a>

See above for details.

\
