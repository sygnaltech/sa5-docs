---
description: >-
  Add advanced filtering for CMS Collection List items and static elements on
  your Webflow page, using custom attributes and a lo-code JavaScript filter
  function.
---

# Advanced Element Filtering

Webflow has a powerful conditional visibility feature, however sometimes it falls short when you have complex rules.

WFU’s advanced filtering feature allows you to expand on this. Choose which elements you want to be visible depending on simple javascript expression or a javascript function.

* Display certain elements only between certain hours of the day, certain days of the week, seasonally, etc.
* Show collection list items based on the time of day.
* Show employees who have a birthday today, or this month.

All of this and much more can be done by simply attaching WFU’s filtering attributes to any element. WFU will evaluate the expression or the function, and display your element if these return `true`.

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-filter` attribute <a href="#wfu-filter-attribute" id="wfu-filter-attribute"></a>

Use `wfu-filter` with a specific formula to suppress the current node.

```
wfu-filter = new Date().getHours() >= 12
```

Best used for short and simple expressions.

#### `wfu-filter-func` attribute <a href="#wfu-filter-func-attribute" id="wfu-filter-func-attribute"></a>

Use `wfu-filter-func` to call a function you define, and to pass in the element as a jQuery object. From there, you can perform any checks or calculations you want and then return `true` if you’d like the element to display, or `false` if you want to hide it.

```
wfu-filter-func = isBirthday
```

And then define a function by that name, e.g.;

```
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

Make sure to give it a single parameter, as it will be passed the element you are evaluating in the filter.

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

Add this CSS script to the HEAD of your site or page.

{% code overflow="wrap" %}
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/dist/css/webflow-html.min.css">
```
{% endcode %}

Add this JS reference to the BODY of your site or page.

{% code overflow="wrap" %}
```html
<script type="module" src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/nocode/webflow-html.min.js"></script>
```
{% endcode %}

#### STEP 2 - Apply `wfu-filter` or `wfu-filter-func` to the elements you want to filter <a href="#step-2---apply-wfu-filter-or-wfu-filter-func-to-the-elements-you-want-to-filter" id="step-2---apply-wfu-filter-or-wfu-filter-func-to-the-elements-you-want-to-filter"></a>

See above for details.

\
